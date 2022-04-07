## udf
## sqrt 001 Dataset created on SAS 
## original sas code


```
DATA numbers;
INPUT val1 val2 val3 ;
DATALINES;
4 9 3
;
RUN;

/* type1 */
data testdata;
set numbers;
res = sqrt(val1)
;
run;

```

## original python code
```

python 

def testdata_func(dfSchema, row=None):
    """
    Function which accepts arguments as listed below to ...
    and returns as specified below
    Args:
        dfSchema: dfSchema is ...
        row: row=None is ...
    Returns:
        returns ...
    """
    row['res'] = math.sqrt(pandas.rowGet(dfSchema, row, 'val1', 0))
    return row
numbers = pandas._data_['numbers']
dfSchema = numbers.dtypes
testdata = numbers.apply(lambda row: testdata_func(dfSchema, row), axis=1)
pandas._data_['testdata'] = testdata
pandas.showDF(testdata)

```

## Changed python code

## result
```
val1  val2  val3  res
0   4.0   9.0   3.0  2.0
```

## udf
## sqrt 002 Null
## original sas code


```
data _null_;
x= 4;
result=sqrt(x);
put result=;
run;

```

## original python code
```
x = 4
result = math.sqrt(x)
print(result)

```

## Changed python code

## result
```
2
```
## udf
## sqrt 003 Macro
## original sas code


```
%macro test(a);
data null;
num1 = sqrt(&a);
put num1=;
run;
%mend test;
%test(4)
```

## original python code
```

python 

def test(vars, a):
    """
    Function which accepts arguments as listed below to ...
    and returns as specified below
    Args:
        vars: vars is ...
        a: a is ...
    Returns:
        returns ...
    """
    
    
    num1 = math.sqrt(a)
    return num1
test(vars,4)


```

## Changed python code

## result
```
2
```

# # Problem-1 
what I need to do after conversion SAS codes in Pandas codes ??
--> Go to dev folder and check for .py or .ipnyb files
--> open anyone of these two and run and check the output

# # Problem-3 
cxt (line no. 46)
--> update with cxt = SharedContextPandas()
# # Problem-2
Getting error in last run-cell ?? (NameError: name '_vars_' is not defined)
-->

