# Scala-Project-performing-ETL-process-applying-discount-rules-on-CSV-Data
Scala project handling  concession pursuant to some qualifying rules on CSV files 

## Problem Describtion
  - A huge retail chain requires a rule engine that determines whether transactions for orders are eligible for discounts based on a set of qualifying criteria. also computes the appropriate discount automatically based on a set of calculation rules.
  - we faced 6 qualification rules to handle beside:
      * Transactions that didn’t qualify to any discount will have 0% discount. 
      * Transactions that qualified to more than one discount will get the top 2 and get their average. 
      * We need the system to be up and running 24 hours. Raw transactions’ files will be pushed to the following machine (IP: X.X.X.X) on the following path (……/raw_data).
      * We need the calculations to be done automatically once the file is pushed. 
      * After ingesting the raw data and calculating the discount please also calculate the final price and load the result in a database table of your choice. 
      * The raw data needs to be removed from the raw_data directory after successfully  writing the processed data in the database.
      * It is required to log the engine’s events in a log file “rules_engine.log”. Please use the following logging format [TIMESTAMP, LOGLEVEl, MESSAGE]


## Some Technical considerations:
   - In the core functional logic:
       * Use only vals, no vars allowed.
       * No mutable data structures allowed.
       * No loops allowed.
       * No Null values.
       * Make sure all your functions are pure:
            - Output depends solely on input.
            - Input to the function doesn’t get mutated.
            - Has a predictable behavior.
       * The code should be well commented.
       * The code should be clean, easy to read and self-explainable. (remember that one of the objectives of functional programming is having a readable code)


## Logic of Our Solution
 - we had 6 qualifcation rules which is in the file attached , we made 2 functions, 1 to check if the data is qualified, and the other to calcualte the discount incase it's qualified
- made 12 function, 6 for checking, and 6 for calculating discounts.
- declared case class, to assign every check function and calculating discount functions as 1 element in the case class
- made a list of objects of case class, every object has both functions
- made a function to write the log file
- made function to calculate the discount, incase only 1 discount then print it, incase no discounts then print 0, incase more than 1 discount, get highest 2 and calculate average


## Our Greate Team 
  - Mohamed Fathy
  - Sara Salah
  - Islam Younes
