Task Code to refactor
=================

X: My Take on given Code
=================
Note: 
I have touched limited methods for refactoring code in the time I can afford to spend on, 
but I hope this will be enough for you to assess my code ethics.

1.The code at the controller level is ok, as context logic is defined in the repository so it is making sense of 'Thin Controller', although naming conventions are bad.
2.The code at the repository end is messy as it can be shorten to many levels

3. In BookingController naming convention should be followed as
    a). '$this->repository' should be $this->bookingRepository (ref: line:21,29)
    b). '$request->__authenticatedUser->user_type' should be '$request->authenticatedUser->user_type' (ref: line:38)
    c). $this->repository->getAll($request) should be as $this->repository->getAllJobs($request), as it make more sense (ref: line:45)

4. It would be better if request should be validated before processing, either in separate Request class or in method validation
5. Comparison can be shorten by array method as I modified (ref: line:38)
6. It would be better if Role Ids be defined as a constants on User Model instead of in env, as these are context of Model not an environment variables
7. Early returns reduces the code complexity
8. Again on getAllJobs Method in BookingRepository Class, naming conventions should be followed.
9. To me it make code more readable/understandable with using Ternary Operator instead of if-else, where possible
10.hint:custom query scopes can be used to limit the complexity of where clauses.
11. using collection methods makes more sense and cost less computations instead of using raw array methods 

P.S: 
If the context of query , 
whether it is to query records based on signle attribute at a time or with multiple attributes, 
because if it were defined than it could have been made more understandable if defined the context, 
and also 'clone' should be used to avoid query substitution to run it with different where statements.