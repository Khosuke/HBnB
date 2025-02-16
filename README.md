
# High-level Package diagram :

This is the high-level package diagram that illustrates the three-layer architecture of the application and the communication between these layers via the facade pattern.




Image:
![Package Diagram (1)]()

# Class Diagram :

This is the class diagram for the Business Logic layer, focusing on the User, Place, Review, and Amenity entities, including their attributes, methods, and relationships. And which also includes the relationships between Places and Amenities.

Image:
![Class Diagram (1)]()

# Sequence Diagram: User create an account

This sequence diagram illustrates the user registration process in the HBnB platform. The diagram shows the complete flow from initial user data submission through validation, email verification, password security, and account creation, including error handling for existing email addresses.

Image:
![Sequence Create Account Diagram (1)]()

### Main Success Scenario
1. User submits registration data via POST request
2. API forwards data for validation
3. Business logic validates requirements
4. Database confirms email availability
5. Password is securely hashed
6. User account is created
7. UserID is returned to client

### Alternative Flow
1. **Email Already Exists**
   - Database finds existing email
   - Returns conflict error
   - User receives 409 status code
   - Registration is prevented

2. **Database Error**
   - System cannot access place data
   - Returns 500 status with error information
   - Ensures proper error handling for system failures

# Sequence Diagram : User Post a Review


# Sequence Diagram : User Create a new Place listing



# Sequence Diagram : User Fetching Places

This sequence diagram illustrates the process of fetching a list of places in the HBnB booking system. The diagram demonstrates the interaction flow between the user interface, API layer, business logic, and database when retrieving place listings based on search criteria.

![Sequence User Fetch Places Diagram (1)]()

### Main Success Scenario
1. User sends GET request with search criteria
2. API forwards request to business logic
3. Business logic validates criteria
4. Database query executes with valid criteria
5. Results are formatted and returned to user

### Alternative Flows
1. **Empty Results**
   - Valid search with no matching places
   - Returns 200 status with empty list
   - Allows client to handle zero-result cases gracefully

2. **Invalid Criteria**
   - Search parameters fail validation
   - Returns 400 status with error details
   - Prevents unnecessary database queries

3. **Database Error**
   - System cannot access place data
   - Returns 500 status with error information
   - Ensures proper error handling for system failures
