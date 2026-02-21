# bdd_behave_python_demo
Follow these basic steps to create framework from scratch
1. Install "PyCharm" for Windows
2. Create new Project
3. Create below folder and files

|
|-Features
|---Steps --> login.py
|---login.feature


4. Write test cases in login.feature file as per requirement


5. Open terminal prompt and run below command to install behave on the project path
pip install behave
   
6. Run below dry run command and get all the required  missing steps to enter in "Steps" --> login.py i.e. a Step Definition file
behave login.feature

7. Import basic libraries from "behave" like 'given/then/when' and 'selenium webdriver'
and remove exception/error lines -

 from behave import when
from behave import then
from behave import given
from behave import *
from selenium import webdriver

from behave.api.pending_step import StepNotImplementedError
@when(u'open OrangeHRM home page')
def launchbrowswer(context):
    raise StepNotImplementedError(u'When open OrangeHRM home page')


@then(u'Verify logo is present on Home Page')
def verifylogo(context):
    raise StepNotImplementedError(u'Then Verify logo is present on Home Page')


@then(u'close the browser')
def closebrowser(context):
    raise StepNotImplementedError(u'Then close the browser')
