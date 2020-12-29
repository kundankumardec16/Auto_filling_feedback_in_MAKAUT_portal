# Auto_filling_feedback_in_MAKAUT_portal
## This project is for auto-form feedback completion within the MAKAUT portal.

  # Installation Steps
  
### Step 1: Git clone this repository
```bash
$ git clone https://github.com/kundankumardec16/Auto_filling_feedback_in_MAKAUT_portal.git
$ cd Auto_filling_feedback_in_MAKAUT_portal
```
  
### Step 2: Pip install requirements
```bash
$ python3 -m pip install selenium
```
  
### Step 3: Download Chromium Driver and copy the file path
Download the Chromium Driver from **https://chromedriver.chromium.org/** (Note: Unzip the file after it's finished downloading).
Copy the FULL PATH of the recently unzipped .exe file.
  
### Step 4: Paste in the Driver file path
Paste the path within the quotations in `Discrete_mathematics_autofill_feedback.py` under the comment "#Connecting Selenium WebDriver with Chrome WebDriver" 
# Example:
`driver=webdriver.Chrome(executable_path="*C:\Users\HP\AppData\Local\Temp\Rar$EXa0.142\chromedriver.exe*")`
  
### Step 5: Enter roll number and password
In the code enter your roll number and password within the quotes `send_keys("")`. It is next to the comment # Enter your roll no/password here
  
### Step 6: Save the file and run 
```bash
$ python3 Discrete_mathematics_autofill_feedback.py
```

**NOTES:**
*Ensure your version of Google Chrome is up to date. You can update it here:* **chrome://settings/help**
*The code written will only work if the website* **"https://makaut1.ucanapply.com/smartexam/public/"** *after login has not been changed.*
