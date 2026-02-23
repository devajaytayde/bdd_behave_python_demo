# bdd_behave_python_demo
Follow these basic steps to create framework from scratch
1. Install "**PyCharm**" for Windows
2. Create new Project
3. Create below folder and files
 <img width="576" height="391" alt="image" src="https://github.com/user-attachments/assets/485e311f-b78f-468f-9bdc-352494e8b6af" />



4. Write test cases in login.feature file as per requirement


5. Open terminal prompt and run below command to install behave on the project path
**pip install behave**
   
6. Run below dry run command and get all the required  missing steps to enter in "Steps" --> login.py i.e. a Step Definition file
**behave login.feature**

7. Import basic libraries from "behave" like 'given/then/when' and 'selenium webdriver'
and remove exception/error lines -

                     from behave import when
                     from behave import then
                     from behave import given
                     from behave import *
                     from selenium import webdriver
                     from selenium.webdriver.common.by import By
                     from selenium.webdriver.support.ui import WebDriverWait
                     from selenium.webdriver.support import expected_conditions as EC
                     from behave.api.pending_step import StepNotImplementedError
                     
                     @when('open OrangeHRM home page')
                     def launchbrowswer(context):
                         #context.driver = webdriver.Edge(executable_path="C:\\Users\\AjayTayde\\SDET\\workspace\\library\\edgedriver_win64\\msedgedriver.exe")
                         context.driver = webdriver.Chrome()
                         context.driver.get("https://opensource-demo.orangehrmlive.com/web/index.php/auth/login")
                     
                     @then('Verify logo is present on Home Page')
                     def verifylogo(context):
                         element = WebDriverWait(context.driver, 10).until(EC.element_to_be_clickable((By.XPATH, "//img[@src='/web/images/ohrm_branding.png?v=1763650546848']")))
                         status = context.driver.find_element(By.XPATH,("//img[@src='/web/images/ohrm_branding.png?v=1763650546848']")).is_displayed()
                         assert status is True
                     
                     @then('close the browser')
                     def closebrowser(context):
                         context.driver.close()


8. **Hooks in Behave -**
   
**before_step(context, step), after_step(context, step)** – Executed before and after every step.
**before_scenario(context, scenario), after_scenario(context, scenario) –** Executed before and after every scenario.
**before_scenario(context, feature), after_scenario(context, feature) –** Executed before and after every feature.
**before_all(context), after_all(context) –** Executed before and after the execution of the entire test cycle.







Important links-
https://superfastpython.com/thread-local-data/
https://selenium-python.readthedocs.io/api.html



    
