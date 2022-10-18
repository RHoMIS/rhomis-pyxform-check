# Testing Pyxform on XLSX Survey Files

Can create a virtual environment using:

`python3 -m venv venv`

Can install dependencies using:

`pip install -r requirements.txt` 

or

`pip3 install -r requirements.txt` 


Activate virtual environment with:

`source venv/bin/activate`


## Dependencies

You need to have java installed (make sure to add to PATH)

### Mac users


`brew install openjdk@11`

### Ubuntu

`sudo apt install default-jre`


# Using Pyxform

Basic Usage:

`xls2xform 'PATH_TO_XLSX' 'OUTPUT_PATH'`

Example on valid form:

`xls2xform './test-surveys/valid-survey.xlsx' './xforms/valid-survey.xform'`

Example on valid form:

`xls2xform './test-surveys/invalid-survey.xlsx' './xforms/invalid-survey.xform'`


Example for only outputting error lines:

```
xls2xform './test-surveys/invalid-survey.xlsx' './xforms/invalid-survey.xform' 2>&1 | 
    grep 'pyxform.errors.PyXFormError:' |
    cat
```