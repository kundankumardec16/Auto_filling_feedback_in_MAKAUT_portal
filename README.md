# Auto_filling_feedback_in_MAKAUT_portal
# This code will be for auto-filling of several feedback data of MAKAUT portal without human intervention if once initiated.

Before running it chrome version installed in the PC should be up-to-date.

To update chrome version: 
  Open Google chrome -> Click on 3 consecutive vertical dots (Just below the close section) under it go to "Help" -> Click "About Google Chrome" -> If it is not up to date Update   it else note the version.
  
Now, 
  
  Step 1 : Download chrome driver from https://chromedriver.chromium.org/
           Note : The downloaded file will be in zip folder so unzip it.
  Step 2 : Copy it's complete address i.e address of recently unzip exe file.
  Step 3 : Paste the path in the code under comment "#Connecting Selenium WebDriver with Chrome WebDriver" like ...
           driver=webdriver.Chrome(executable_path="C:\\Users\\HP\\AppData\\Local\\Temp\\Rar$EXa0.142\\chromedriver.exe")
  Step 4 : In the code enter your roll number and password within the quotes send_keys(""). It is indicated by the comment in the code where roll number should be entered and                password.
  Step 5 : Save it and run.
  
The code written will work only if the website "https://makaut1.ucanapply.com/smartexam/public/" after login has not been changed.


Thank you
