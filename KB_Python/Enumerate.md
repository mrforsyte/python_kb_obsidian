# Enumerate function break down
In order to solve simple problems we can get by using _for_ loops and _in range_ function.
For example we need to present a list, ordered one with four seasons.
Example:  
1. Spring;
2. Summer
3. Fall
4. Winter

To do this we can use aforemention we can use **in range** function 
```py
seasons = ["Spring","Winter","Autumn","Summer"] 
   for count in range(len(seasons)):
  print(count+1, seasons[count])
```
or we can utilize _for_ loop and the code will look like this:
```py
seasons = ['Spring','Summer',"Fall","Winter"]
counter = 0
for season in seasons:
    counter+=1
    print(counter,season)
```
However, there are some ___problems___ with solutions above:
*  make additional variable;
*  incrementing count as additional work;
*  incrementing count in print;

## Enumerate _finally!_
1. Iterating with _enumerate()_
2. Using _enumerate()_
3. Understanding _enumerate()_
4. Building  **my_enum()**
5. Working with **my_enum()**

Example:
```py
#enumerate function

seasons = ["Spring","Summer","Fall","Winter"]

for count, season in enumerate(seasons, start=1):
    print(count,season)

```
***Advantages***:
*  Clean and consice;
*  Self-contained;
*  No accessing variables


## Understanding _enumerate()_
it's built-in function - no importing required, available from standard Python library. Requires object that supports iteration