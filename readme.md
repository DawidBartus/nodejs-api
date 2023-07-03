| Used Technologies                      |
| -------------------------------------- |
| Fundamentals                           |
| - Node.js                              |
| Core Libraries                         |
| - Express                              |
| - fs (File System)                     |
| - dotenv                               |
| Database Handling                      |
| - MongoDB                              |
| - Mongoose                             |
| Data Validation and Security           |
| - Joi                                  |
| - Bcrypt                               |
| File Handling                          |
| - Multer                               |
| - Jimp                                 |
| Authentication and Authorization       |
| - Passport                             |
| - JWT (JSON Web Tokens)                |
| Email Sending                          |
| - Nodemailer                           |
| Tools                                  |
| - Postman                              |
| Helper Libraries                       |
| - UUID (Universally Unique Identifier) |
| - Gravatar                             |

User Registration:
<code>router.post("/users/register", userRegister)</code> </br>
Method: POST </br>
Endpoint: /users/register </br>
Handler: userRegister </br>
Description: Allows users to sign up for an account. Sends an email with a verification token. </br>

User Verification: `router.get("/auth/verify/:verificationToken", userVerification)` </br>
Method: GET </br>
Endpoint: /auth/verify/:verificationToken </br>
Handler: userVerification </br>
Description: Verifies the user's account using the verification token. </br>

Check User Verification: `router.post("/users/verify/", checkIfUserIsVerified)` </br>
Method: POST</br>
Endpoint: /users/verify/ </br>
Handler: checkIfUserIsVerified </br>
Description: Checks if the user's account is verified. If not, sends an email with verification token. </br>

User Login: `router.post("/users/signin", logIn)` </br>
Method: POST </br>
Endpoint: /users/signin </br>
Handler: logIn </br>
Description: Allows users to sign in to their account. Checks if the user's login and password are valid and if the account is verified. </br>

User Details: `router.get("/users/current", auth, getUserDetails)` </br>
Method: GET </br>
Endpoint: /users/current </br>
Middleware: auth </br>
Handler: getUserDetails </br>
Description: Retrieves details of the authenticated user. </br>

User Logout: `router.get("/users/logout", auth, logOutUser)` </br>
Method: GET </br>
Endpoint: /users/logout </br>
Middleware: auth </br>
Handler: logOutUser </br>
Description: Logs out the currently authenticated user </br>

Contacts List: `router.get("/contacts", auth, listContacts)` </br>
Method: GET </br>
Endpoint: /contacts </br>
Middleware: auth </br>
Handler: listContacts </br>
Description: Retrieves the list of user contacts. </br>

Contact by ID: `router.get("/contacts/:contactId", auth, getContactById)` </br>
Method: GET </br>
Endpoint: /contacts/:contactId </br>
Middleware: auth </br>
Handler: getContactById </br>
Description: Retrieves a specific contact by its ID. </br>

Add Contact: `router.post("/contacts", auth, addContact)` </br>
Method: POST </br>
Endpoint: /contacts </br>
Middleware: auth </br>
Handler: addContact </br>
Description: Checks if new contact match the schema and adds it for the authenticated user. </br>

Remove Contact: `router.delete("/contacts/:contactId", auth, removeContact)` </br>
Method: DELETE </br>
Endpoint: /contacts/:contactId </br>
Middleware: auth </br>
Handler: removeContact </br>
Description: Removes a specific contact by its ID. </br>

Update Contact: `router.put("/contacts/:contactId", auth, updateContact)`</br>
Method: PUT </br>  
Endpoint: /contacts/:contactId </br>
Middleware: auth </br>
Handler: updateContact </br>
Description: Updates a specific contact by its ID. </br>

Update Contact Status: `router.patch("/contacts/:contactId/favorite", auth, updateStatusContact)`</br>
Method: PATCH </br>
Endpoint: /contacts/:contactId/favorite </br>
Middleware: auth </br>
Handler: updateStatusContact </br>
Description: Updates the favorite status of a specific contact by its ID. </br>

Upload Avatar: `router.patch("/users/avatars", auth, userUploadAvatar, uploadAvatar)` </br>
Method: PATCH </br>
Endpoint: /users/avatars </br>
Middleware: auth, userUploadAvatar, uploadAvatar </br>
Description: Uploads an avatar image for the authenticated user. </br>

Avatar Preview: `router.get("/avatar/:filename", getAvatar)` </br>
Method: GET </br>
Endpoint: /avatar/:filename </br>
Handler: getAvatar </br>
Description: Retrieves the avatar image by its filename. </br>
