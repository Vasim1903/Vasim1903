from selenium import webdriver
from selenium.webdriver.common.by import By
from selenium.webdriver.firefox.service import Service
from selenium.webdriver.support.ui import WebDriverWait
from selenium.webdriver.support import expected_conditions as EC
from selenium.webdriver.firefox.options import Options
import time

# Use provided credentials
email = "vasimhushain.1903@gmail.com"
password = "Vasimslogin@666"
first_name = "Vasim"
last_name = "S"

# Setup Firefox driver
options = Options()
options.add_argument("--width=1024")
options.add_argument("--height=768")
driver = webdriver.Firefox(options=options)

try:
    # Step 1: Open Magento site
    driver.get("https://magento.softwaretestingboard.com/")
    driver.find_element(By.LINK_TEXT, "Create an Account").click()


finally:
    time.sleep(5)
    driver.quit()
