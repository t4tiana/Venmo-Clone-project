# Venmo Clone project 
### [_Source code readily available upon request_]

This **capstone project** was created during Week 8 of 14 of my bootcamp to exhibit my knowledge of backend development for web applications. It demonstrates proficiency of the following concepts and technologies:
- OOP principles
- interfaces
- HTTP / JSON
- ASP.NET
- MVC pattern
- RESTful APIs
- integration testing
- user authentication/JWTs
- DAOs
- SQL Server

## User stories

1. As a user of the system, I need to be able to register myself with a username and password.
   - A new registered user starts with an initial balance of 1,000 T Bucks.
2. As a user of the system, I need to be able to log in using my registered username and password.
   - Logging in returns an Authentication Token. I need to include this token with all my subsequent interactions with the system outside of registering and logging in.
3. As an authenticated user of the system, I need to be able to see my Account Balance.
```
Your current account balance is: $9999.99
```
4. As an authenticated user of the system, I need to be able to *send* a transfer of a specific amount of T Bucks to a registered user.
   - I should be able to choose from a list of users to send T Bucks to.
   - I must not be allowed to send money to myself.
   - A transfer includes the User IDs of the from and to users and the amount of T Bucks.
   - The receiver's account balance is increased by the amount of the transfer.
   - The sender's account balance is decreased by the amount of the transfer.
   - I can't send more T Bucks than I have in my account.
   - I can't send a zero or negative amount.
   - A Sending Transfer has an initial status of *Approved*.
```
Please choose an option: 4
|-------------- Users --------------|
|    Id | Username                  |
|-------+---------------------------|
|  1002 | Bernice                   |
|  1003 | Deandre                   |
|-----------------------------------|
Id of the user you are sending to[0]: 1003
Enter amount to send: 75.74
```
5. As an authenticated user of the system, I need to be able to see transfers I have sent or received.
```
-------------------------------------------
Transfers
ID          From/To                 Amount
-------------------------------------------
23          From: Bernice          $ 903.14
79          To:    Larry           $  12.55
---------
Please enter transfer ID to view details (0 to cancel): "
```
6. As an authenticated user of the system, I need to be able to retrieve the details of any transfer based upon the transfer ID.
```
--------------------------------------------
Transfer Details
--------------------------------------------
 Id: 23
 From: Bernice
 To: Me Myselfandi
 Type: Send
 Status: Approved
 Amount: $903.14
```
7. As an authenticated user of the system, I need to be able to *request* a transfer of a specific amount of T Bucks from another registered user.
   - I should be able to choose from a list of users to request T Bucks from.
   - I must not be allowed to request money from myself.
   - I can't request a zero or negative amount.
   - A transfer includes the User IDs of the from and to users and the amount of T Bucks.
   - A Request Transfer has an initial status of *Pending*.
   - No account balance changes until the request is approved.
   - The transfer request should appear in both users' list of transfers (use case #5).
```
Please choose an option: 5
|-------------- Users --------------|
|    Id | Username                  |
|-------+---------------------------|
|  1002 | Bernice                   |
|  1003 | Deandre                   |
|-----------------------------------|
Id of the user you are requesting from[0]: 1002
Enter amount to request: 39.99
```
8. As an authenticated user of the system, I need to be able to see my *Pending* transfers.
```
-------------------------------------------
Pending Transfers
ID          To                     Amount
-------------------------------------------
88          Bernice                $ 142.56
147         Larry                  $  10.17
---------
Please enter transfer ID to approve/reject (0 to cancel): "
```
9. As an authenticated user of the system, I need to be able to either approve or reject a Request Transfer.
   - I can't "approve" a given Request Transfer for more T Bucks than I have in my account.
   - The Request Transfer status is *Approved* if I approve, or *Rejected* if I reject the request.
   - If the transfer is approved, the requester's account balance is increased by the amount of the request.
   - If the transfer is approved, the requestee's account balance is decreased by the amount of the request.
   - If the transfer is rejected, no account balance changes.
```
1: Approve
2: Reject
0: Don't approve or reject
---------
Please choose an option:
```
