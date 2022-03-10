### Creating a Callable Task

Expected time required: 15 min

We are working on a utility for Amazon Music that will allow users to access stats about their listening 
habits while using their account. Fun facts like how many times they have listened to a playlist, or what their top
music genres are. 

The first step in developing this utility is to retrieve their account info from the database `MusicAccountService`.
The class `MusicAccountRetriever` will do this task. It's method `retrieveAccount(String accountID)` uses an
`ExecutorService` and the `Callable` task `ImportAccountTask` to retrieve an `AmazonMusicAccount` from the database. 

To complete this assignment, you must pass all the unit tests. To do so:

- Complete the implementation of `ImportAccountTask` to implement `Callable`.
  - The class declaration must be completed along with properly implementing the `call()` method.
  - It should return a type of `AmazonMusicAccount`. The `MusicAccountService` class has a static method
    `getAccount(String accountID)` which will return an `AmazonMusicAccount` for the associated account. You can use
    this as the return value in `call()`.
  
- Complete the `retrieveAccount(String accountID)` method in `MusicAccountRetriever` to do two things:
  - Submit a new`ImportAccountTask` class to `accountExecutor`.
  - Return the result as a `Future<AmazonMusicAccount>`. 

Verify the tests in the `tst` folder pass.

HINTS:  
* [IntelliJ isn't generating all the imports I need.](hints/hint-01.md)
* [One of the unit tests isn't working?](hints/hint-02.md)
