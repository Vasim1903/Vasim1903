from selenium import webdriver
from selenium.webdriver.common.by import By
from selenium.webdriver.firefox.options import Options
import time

options = Options()
options.set_preference("general.useragent.override", 
    "Mozilla/5.0 (iPhone; CPU iPhone OS 13_5 like Mac OS X) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/13.1.1 Mobile/15E148 Safari/604.1")

driver = webdriver.Firefox(options=options)
driver.set_window_size(375, 812)  # iPhone X size

# Account info
first_name = "Vasim hushain"
last_name = "S"
email = "vasimhushain.1903@gmail.com"
password = "Vasim@123"

driver.get("https://magento.softwaretestingboard.com/")
time.sleep(3)

driver.find_element(By.CSS_SELECTOR, "button.action.nav-toggle").click()
time.sleep(1)
driver.find_element(By.LINK_TEXT, "Account").click()
time.sleep(1)
driver.find_element(By.LINK_TEXT, "Create an Account").click()
time.sleep(3)

driver.find_element(By.ID, "firstname").send_keys(first_name)
driver.find_element(By.ID, "lastname").send_keys(last_name)
driver.find_element(By.ID, "email_address").send_keys(email)
driver.find_element(By.ID, "password").send_keys(password)
driver.find_element(By.ID, "password-confirmation").send_keys(password)

driver.find_element(By.CSS_SELECTOR, "button.submit.primary").click()
time.sleep(5)

driver.find_element(By.CSS_SELECTOR, "button.action.nav-toggle").click()
time.sleep(1)
driver.find_element(By.LINK_TEXT, "Account").click()
time.sleep(1)
driver.find_element(By.LINK_TEXT, "Sign Out").click()
time.sleep(5)

driver.find_element(By.CSS_SELECTOR, "button.action.nav-toggle").click()
time.sleep(1)
driver.find_element(By.LINK_TEXT, "Account").click()
time.sleep(1)
driver.find_element(By.LINK_TEXT, "Sign In").click()
time.sleep(3)

driver.find_element(By.ID, "email").send_keys(email)
driver.find_element(By.ID, "pass").send_keys(password)
driver.find_element(By.ID, "send2").click()
time.sleep(5)

welcome = driver.find_element(By.CSS_SELECTOR, "div.panel.header span.logged-in").text
d-in").text

driver.quit()
