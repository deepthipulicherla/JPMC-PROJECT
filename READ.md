PROBLEM-------------
Implement a small message processing application that satisfies the below requirements for
processing sales notification messages. You should assume that an external company will be sending
you the input messages, but for the purposes of this exercise you are free to define the interfaces.
Processing requirements
 All sales must be recorded
 All messages must be processed
 After every 10th message received your application should log a report detailing the number
of sales of each product and their total value.
 After 50 messages your application should log that it is pausing, stop accepting new
messages and log a report of the adjustments that have been made to each sale type while
the application was running.
Sales and Messages
 A sale has a product type field and a value – you should choose sensible types for these.
 Any number of different product types can be expected. There is no fixed set.
 A message notifying you of a sale could be one of the following types
o Message Type 1 – contains the details of 1 sale E.g apple at 10p
o Message Type 2 – contains the details of a sale and the number of occurrences of
that sale. E.g 20 sales of apples at 10p each.
o Message Type 3 – contains the details of a sale and an adjustment operation to be
applied to all stored sales of this product type. Operations can be add, subtract, or
multiply e.g Add 20p apples would instruct your application to add 20p to each sale
of apples you have recorded.


SOLUTION----------

Generated executable jar "SaleProcessing" 
Steps to run 
-->prerequisite is ensure saleInput.txt is present in the same folder where "SaleProcessing.jar" is present
-->run the command as "java -jar SaleProcessing"
-->Result would come as below

DPULICHE-M-C6R6:SaleProcessing dpuliche$ java -jar SaleProcessing 


10 sales appended to log
*************** Log Report *****************
|SalesMessageProcessor.Product           |Quantity   |Value      |
|cherries          |20         |2.00       |
|bananas           |21         |2.10       |
|apples            |43         |16.90      |
-------------------------------------------
|Total Sales                   |21.00      |
-------------------------------------------
End


10 sales appended to log
*************** Log Report *****************
|SalesMessageProcessor.Product           |Quantity   |Value      |
|oranges           |21         |2.10       |
|watermelons       |1          |0.20       |
|cherries          |21         |2.10       |
|pineapples        |21         |2.10       |
|strawberries      |6          |0.30       |
|bananas           |21         |2.10       |
|apples            |43         |16.90      |
|grapes            |3          |0.45       |
-------------------------------------------
|Total Sales                   |26.25      |
-------------------------------------------
End


10 sales appended to log
*************** Log Report *****************
|SalesMessageProcessor.Product           |Quantity   |Value      |
|oranges           |21         |2.10       |
|watermelons       |26         |5.20       |
|cherries          |21         |2.10       |
|pineapples        |21         |2.52       |
|strawberries      |6          |0.30       |
|bananas           |21         |2.73       |
|apples            |86         |32.00      |
|grapes            |3          |0.45       |
-------------------------------------------
|Total Sales                   |47.40      |
-------------------------------------------
End


10 sales appended to log
*************** Log Report *****************
|SalesMessageProcessor.Product           |Quantity   |Value      |
|oranges           |42         |4.20       |
|watermelons       |26         |5.20       |
|cherries          |42         |4.20       |
|pineapples        |42         |4.62       |
|strawberries      |6          |0.30       |
|bananas           |42         |4.83       |
|apples            |87         |49.30      |
|grapes            |3          |0.45       |
-------------------------------------------
|Total Sales                   |73.10      |
-------------------------------------------
End


10 sales appended to log
*************** Log Report *****************
|SalesMessageProcessor.Product           |Quantity   |Value      |
|oranges           |42         |4.20       |
|watermelons       |26         |5.20       |
|cherries          |62         |4.10       |
|pineapples        |42         |6.72       |
|strawberries      |11         |2.86       |
|bananas           |63         |6.93       |
|apples            |109        |51.50      |
|grapes            |3          |0.45       |
-------------------------------------------
|Total Sales                   |81.96      |
-------------------------------------------
End


Application reached 50 messages and cannot process further. The following are the adjustment records made;

Performed Add 0.20p to 21 apples and price adjusted from 2.10p to 6.30p
Performed Add 0.20p to 42 apples and price adjusted from 8.40p to 16.80p
Performed Add 0.02p to 21 pineapples and price adjusted from 2.10p to 2.52p
Performed Add 0.03p to 21 bananas and price adjusted from 2.10p to 2.73p
Performed Subtract 0.05p to 44 apples and price adjusted from 17.00p to 14.80p
Performed Add 0.20p to 65 apples and price adjusted from 16.90p to 29.90p
Performed Add 0.20p to 86 apples and price adjusted from 32.00p to 49.20p
Performed Multiply 0.20p to 11 strawberries and price adjusted from 0.55p to 2.86p
Performed Add 0.05p to 42 pineapples and price adjusted from 4.62p to 6.72p
Performed Subtract 0.05p to 42 cherries and price adjusted from 4.20p to 2.10p
