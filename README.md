
# Ambulance Pickup Problem

## Packagaes:

`pip install -r requirements.txt`

Or manually install `matplotlib` and `hps-nyu`

## Usage (Python):

Place your logic in `my_solution()` on line 352 and the code should do the rest for you.

If you do not want to mess with the validator file, you are free to follow the approach below (for other languages)
and you should be fine with using another .py file.

NOTE: The readdata() return the list of **objects** and not a dictionary. 
You can use `object.prettify()` to get the dictionary instead.

## For Languages other than python:

**Input:** The data will be in the data.txt file

The given format is:

```angular2html
person(xloc,yloc,rescuetime)
1,1,10
...
...
2,2,20

hospital(numambulance)
1
2
3
```

**Output:** Once you calculate your results, generate a "result.txt" file with the following format

PN is the path of that particular ambulance.
```angular2html
Hospital:x_coordinate,y_coordinate,num_ambulances
...
Hospital:x_coordinate,y_coordinate,num_ambulances

Ambulance: P1: (x_coordinate,y_coordinate) P2: (x_coordinate,y_coordinate) ... PN: (x_coordinate,y_coordinate)  
...
Ambulance: P1: (x_coordinate,y_coordinate) P2: (x_coordinate,y_coordinate) ... PN: (x_coordinate,y_coordinate)
```
You can refer to the "sample_result.txt" to get the idea.

**Validation:** Once done with your code, you can then validate the result using the following:

(Sorry, but you need to learn how to run python file for this)

`python validator.py`

## Plot:

If you wish to disable the graph plot, simply comment the `plot()` on line 382

--------------------------------------------------------------------------
## Previous Readme by Yusuke Shinyama
validator.py

by Yusuke Shinyama (yusuke at cs dot nyu dot edu)

(Python2.3 or higher required to run this program.) -- <The updated git for Fall 2021 uses Python 3.x>


USAGE:

   Give the original data file and the output file to the program:

     $ ./validator.py datafile resultfile

   Or you can feed the result from stdin:

     $ yourprogram datafile | ./validator datafile

   The result file should be like this:

     Ambulance: 1: (45,32), 5: (84,26,95) total: 92
     Ambulance: 1: (45,32), 6: (64,30,74), 11: (56,26,80) total: 53
     Ambulance: 1: (45,32), 42: (29,42,67) total: 54
     Ambulance: 2: (59,68), 8: (68,57,52) total: 42
     Ambulance: 2: (59,68), 14: (66,47,58) total: 58
     ...

   I assumed that every line should begin with a string 'Ambulance' (case ignored).
   Then one hospital and one or two people follow. The last 'total' value is ignored.
   Intermediate blanks and commas are ignored, so 

        ambulance:   2  : ( 59 ,  68 ) , 8 : (  68, 57,52)    foo bar

   is still considered as a valid input.


SAMPLE RUN:

   $ ./validator.py sample_data sample_result
   Reading data: sample_data
   Reading results...
   Rescued: 47: (58,41,85) and 20: (62,50,112) taking 73
   Rescued: 11: (56,26,80) and 6: (64,30,74) taking 53
   Rescued: 5: (84,26,95) taking 92
   Rescued: 44: (82,55,74) taking 74
   Rescued: 25: (82,67,56) taking 50
   Rescued: 19: (64,75,47) and 33: (69,72,37) taking 37
   Rescued: 10: (58,95,108) taking 58
   Rescued: 8: (68,57,52) taking 42
   Rescued: 14: (66,47,58) taking 58
   Rescued: 45: (36,57,55) and 28: (35,57,39) taking 17
   Rescued: 43: (30,50,73) and 42: (29,42,67) taking 39
   Rescued: 39: (38,41,69) taking 26
   Rescued: 34: (24,65,56) taking 54
   Rescued: 9: (39,77,58) taking 56
   Rescued: 46: (25,53,34) taking 28
   Rescued: 3: (17,20,102) taking 100
   Rescued: 18: (18,1,71) and 4: (15,7,78) taking 63
   Rescued: 24: (58,15,87) taking 60
   Rescued: 40: (74,11,96) taking 84
   Rescued: 31: (86,9,116) taking 104
   Total score: 26
