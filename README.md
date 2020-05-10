# Auto_filling_feedback_in_MAKAUT_portal
# This code will be for auto filling of a several feedback data of MAKAUT portal without human intervention if once initiated.

from selenium import webdriver
from selenium.webdriver.support.ui import Select
import time

#Topics covered till 02-May-2020

topics={
    'Graph Isomorphism':'2020-03-18 101',
    'Mapping & Cardinality':'2020-03-20 101',
    'Logic':'2020-03-21 101',
    'Cut Sets':'2020-03-23 102',
    'Rings & Fields (part-I)':'2020-03-25 102',
    'Rings & Subrings (part-II)':'2020-03-27 102',
    'Modulo':'2020-03-30 103',
    'Counting':'2020-03-31 103',
    'Rings & Subrings (REV)':'2020-04-02 103',
    'Rings & Subrings (REV)':'2020-04-03 103',
    'Permutation Group & subring problems':'2020-04-07 104',
    'Permutation Group':'2020-04-09 104',
    'Permutation Group':'2020-04-10 104',
    'Planar & Dual Graph':'2020-04-16 105',
    'Planar & Dual Graph':'2020-04-17 105',
    'Planar Q&A':'2020-04-21 106',
    'Proof-types, list colouring intro':'2020-04-23 106',
    '(misc.) mapping: inverse, composition; diagonal argument; NASC; Boolean Ring':'2020-04-24 106'
    }

#Connecting Selenium WebDriver with Chrome WebDriver
driver=webdriver.Chrome(executable_path="C:\\Users\\HP\\AppData\\Local\\Temp\\Rar$EXa0.142\\chromedriver.exe")
driver.maximize_window()

#Login

driver.get('https://makaut1.ucanapply.com/smartexam/public/')
driver.implicitly_wait(10)
driver.find_element_by_class_name("databox-right").click()
driver.find_element_by_id("username").send_keys("")    # Enter your roll no. here
driver.find_element_by_id("password").send_keys("")    # Enter your password here
driver.find_element_by_link_text("Submit").click()

#Filling up form

for data in topics:
    #Selection of Weekly Activity link and clicking
    driver.find_element_by_link_text("Weekly Activity Report").click()
    #week
    Select(driver.find_element_by_id("week")).select_by_value(topics[data][-3:])
    #semester
    Select(driver.find_element_by_id("SEMCODE")).select_by_visible_text('Fourth Semester ( 4th Sem)')
    #course
    driver.find_element_by_css_selector("[data-id='COURSECD']").click()
    driver.find_element_by_link_text("Bachelor of Technology in Computer Science & Engineering ( 001)").click()
    #subject
    driver.find_element_by_css_selector("[data-id='SUBJECTCODE']").click()
    driver.find_element_by_link_text("Discrete Mathematics-PCC-CS401-4407").click()
    #topics
    driver.find_element_by_id("topic_covered").send_keys(data)
    #platform used
    driver.find_element_by_id("platform_used").send_keys("Google Classroom, Whatsapp and Zoom")
    #teacher
    Select(driver.find_element_by_id("class_taken_by")).select_by_visible_text("ARUP DASGUPTA( Basic Engineering Science )")
    #date and time
    driver.execute_script("document.getElementById('date_tme').removeAttribute('readonly', 0);")
    driver.find_element_by_id("date_tme").send_keys(topics[data][:-4]+" 21:00")
    #record lecture
    driver.find_element_by_id("record_lecture_upload_link").send_keys("N\A")
    #duration
    driver.find_element_by_id("duration_in_min").send_keys("60 Minutes")
    #Post class interaction note
    driver.find_element_by_id("post_class_interraction_note").send_keys("Yes given")
    #Assignments received
    driver.find_element_by_id("assignment_received").send_keys("Yes assignments were received")
    #Assignment submitted
    driver.find_element_by_id("assignment_submitted").send_keys("Yes, before due date and due time.")
    #Test attended if any
    driver.find_element_by_id("test_attended_if_any").send_keys("Yes, some in the form of quiz on Google Classroom")
    #Daily self activity
    driver.find_element_by_id("daily_self_acitvity").send_keys("Done assignments thoroughly.")
    #Remark
    driver.find_element_by_id("remark").send_keys("Satisfied")
    driver.find_element_by_id("btnSubmit").click()
    driver.find_element_by_link_text("Dashboard").click()
    
driver.execute_script("window.alert('Submission Complete');")
driver.quit()
