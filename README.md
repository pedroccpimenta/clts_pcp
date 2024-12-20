# clts_pcp

This module allows to measure time lapses through several points in your python script and get a table by the end of the script.
The table is gotten in both ASCII and HTML - the HTML version is prepared mainly to be sent through email.

## Usage

### Import the module
```
import clts_pcp
```

### Set the context
to set the title of the table (context):

```
clts.setcontext('Testing lts v2')
```

and collect an initial timestamp:

```
tstart=clts.getts()
```

### colect elapsed times

Elapsed time from the ```start```
```
#(... step 1 )
clts.elapt["step 1 (successful)."]=clts.deltat(tstart)
t1=clts.getts()
```


Elapsed time from the ```start```
```
#(... step 2 )
clts.elapt["step 2 (successful)."]=clts.deltat(tstart)

```

or elapsed time from any previous timestamp:

```
clts.elapt["step 1-2 (successful)."]=clts.deltat(t1)
```

### get the table


```
clts.listtimes()
```

| Task(s) by Testing lts v2                                                                | watch time (secs) |  proc time (secs) |
|------------------------------------------------------------------------------------------|------------------|-------------------|
| step 1 (successful).                                                                     |              2.20 |              0.00 |
| step 2 (successful).                                                                     |              5.30 |              0.00 |
| step 1-2 (successful).                                                                   |              3.10 |              0.00 |


In the case you want the html version of the table, use:

```
toemail = clts.listtimes()
```

and use the ```toemail``` as the body of the email.


PCP, December 2024




You can use [GitHub-flavored Markdown](https://guides.github.com/features/mastering-markdown/) to write your content.