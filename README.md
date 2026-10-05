# HCL-Training.05.10

# 1 - suriya search
name - KAMALESHWAR KV
Reg Num - 212223240063

#code
from selenium import webdriver
from selenium.webdriver.common.by import By

driver = webdriver.Chrome()

driver.get("https://www.google.com/")

input("If CAPTCHA appears, complete it manually, then press Enter...")

search = driver.find_element(By.NAME, "q")

search.send_keys("actor surya")

print("Placeholder:", search.get_attribute("placeholder"))
print("Enabled:", search.is_enabled())
print("Displayed:", search.is_displayed())

search.submit()

input("Search completed. Press Enter to close...")

driver.quit()


#screenshot

<img width="1600" height="949" alt="suriya 1" src="https://github.com/user-attachments/assets/c8d38560-6943-4a16-b754-c3a7a28b2497" />







# 2 - product search
name - KAMALESHWAR KV
Reg Num - 212223240063

#code
from selenium import webdriver
from selenium.webdriver.common.by import By

driver = webdriver.Chrome()

driver.get("https://www.saucedemo.com/")

username = driver.find_element(By.ID, "user-name")
password = driver.find_element(By.NAME, "password")
login = driver.find_element(By.ID, "login-button")

username.send_keys("standard_user")
password.send_keys("secret_sauce")

print(username.get_attribute("placeholder"))
print(login.is_enabled())
print(username.is_displayed())

login.click()
input("Press Enter to close the browser...")

driver.quit()


#screenshot

<img width="1600" height="951" alt="product-1" src="https://github.com/user-attachments/assets/52c27ad4-3ebf-4a73-82ee-ee37c68faa5d" />





# 3 - flipkart
name - KAMALESHWAR KV
Reg Num - 212223240063

#code
from selenium import webdriver
from selenium.webdriver.common.by import By
from selenium.webdriver.support.ui import WebDriverWait
from selenium.webdriver.support import expected_conditions as EC

driver = webdriver.Chrome()
driver.maximize_window()

wait = WebDriverWait(driver, 20)

# Open Flipkart
driver.get("https://www.flipkart.com/")

# Click Login
login = wait.until(
    EC.element_to_be_clickable(
        (By.XPATH, '//*[@id="container"]/div/div[1]/div/div/div/div/div/div/div/div/div/div[1]/div/div/div[2]/div/div/div/div/div/header/div[2]/div[2]/div/div/div/div/a/span')
    )
)
login.click()

# Wait for mobile number box
mobile = wait.until(
    EC.visibility_of_element_located(
        (By.XPATH, '//*[@id="1"]')
    )
)

mobile.send_keys("7200285667")

print("Mobile number entered.")

# 5. Click Continue / Request OTP
# --------------------------------
continue_button = wait.until(
    EC.element_to_be_clickable(
        (
            By.XPATH,
            '//*[@id="container"]/div/div[1]/div[2]/div[2]/div/div/div[3]/div/button'
        )
    )
)

continue_button.click()

print("Continue clicked.")
print("OTP has been requested.")


# --------------------------------
# 6. Manually enter OTP
# --------------------------------
otp = input("Enter the OTP received on your mobile: ")


# --------------------------------
# 7. Enter OTP
# --------------------------------
otp_box = wait.until(
    EC.element_to_be_clickable(
        (
            By.XPATH,
            '//*[@id="container"]/div/div[1]/div[2]/div[2]/div/div/div[1]/div/div[2]'
        )
    )
)

otp_box.click()
otp_box.send_keys(otp)


# --------------------------------
# 8. Click Verify
# --------------------------------
verify_button = wait.until(
    EC.element_to_be_clickable(
        (
            By.XPATH,
            '//*[@id="container"]/div/div[1]/div[2]/div[2]/div/div/div[2]'
            
        )
    )
)

verify_button.click()


print("OTP verification submitted.")


# --------------------------------
# 9. Keep browser open
# --------------------------------
input("Press Enter to close...")

driver.quit()


#screenshot
<img width="1600" height="858" alt="flipkart-2" src="https://github.com/user-attachments/assets/81cfae44-9a67-41ef-a063-8afecdbd8b26" />

<img width="1571" height="1007" alt="flipkart-1" src="https://github.com/user-attachments/assets/c606f4d0-318c-4c76-a4fb-f30980873565" />
