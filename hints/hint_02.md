One of the unit tests are checking for the results of `retrieveAccount()`, but it starts out returning a `null`
object, which breaks that test. When you pass the test that checks for `null` results, the results test will work.
