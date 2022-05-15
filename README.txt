Code to refactor
=================
1) app/Http/Controllers/BookingController.php
2) app/Repository/BookingRepository.php

Code to write tests
=====================
3) App/Helpers/TeHelper.php method willExpireAt
4) App/Repository/UserRepository.php, method createOrUpdate


----------------------------

# Formatting

## BookingController

- Variable should be declared on top of method. Easier to locate them later when working on the method again sometime.

## BookingRepository

- Variables should be declared on top of method
- Method decorators should have proper post doc. In my current company, we do this to identify the type of variable and payload;
- The Code isn't readable and it takes quite some time to make sense of it. Dozens of if statements, why are you using a single array to filter out that many things.
- Why not just use different objects for conditional statements? 
- in_array contains time_complexity of O(n). that will significantly slow down the process.

# Refactoring

## BookingController

- Missing validators in whole code;
- Not sure how they are doing exception handling, I would assume they're handling it through routes.

#logic

## BookingController

- Repository Pattern is being used here, logically, controller looks fine but I would try to limit the number of loops


# Tests