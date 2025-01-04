
---

# **Selenium WebDriver Features with Examples**  

## **1. Launching a Browser**  
```python
from selenium import webdriver
driver = webdriver.Chrome(executable_path="/home/SATHVIK/chromedriver")
driver.get("https://www.google.com")
driver.quit()
```

## **2. Navigating Between Pages**  
```python
from selenium import webdriver
driver = webdriver.Chrome(executable_path="/home/SHIVA/chromedriver")
driver.get("https://www.google.com")
driver.get("https://www.youtube.com")
driver.back()
driver.forward()
driver.quit()
```

## **3. Locating Web Elements**  
```python
from selenium import webdriver
from selenium.webdriver.common.by import By
driver = webdriver.Chrome(executable_path="/home/SATHVIK/chromedriver")
driver.get("https://www.wikipedia.org")
element = driver.find_element(By.ID, "searchInput")
print(element.tag_name)
driver.quit()
```

## **4. Handling Input Fields**  
```python
from selenium import webdriver
from selenium.webdriver.common.by import By
driver = webdriver.Chrome(executable_path="/home/SHIVA/chromedriver")
driver.get("https://www.google.com")
driver.find_element(By.NAME, "q").send_keys("Selenium WebDriver")
driver.quit()
```

## **5. Clicking Buttons**  
```python
from selenium import webdriver
from selenium.webdriver.common.by import By
driver = webdriver.Chrome(executable_path="/home/SATHVIK/chromedriver")
driver.get("https://www.example.com")
driver.find_element(By.ID, "submit").click()
driver.quit()
```

## **6. Handling Dropdowns**  
```python
from selenium import webdriver
from selenium.webdriver.common.by import By
from selenium.webdriver.support.ui import Select
driver = webdriver.Chrome(executable_path="/home/SHIVA/chromedriver")
driver.get("https://www.example.com/dropdown")
dropdown = Select(driver.find_element(By.ID, "dropdown"))
dropdown.select_by_visible_text("Option 1")
driver.quit()
```

## **7. Handling Checkboxes and Radio Buttons**  
```python
from selenium import webdriver
from selenium.webdriver.common.by import By
driver = webdriver.Chrome(executable_path="/home/SATHVIK/chromedriver")
driver.get("https://www.example.com/form")
driver.find_element(By.ID, "checkbox1").click()
driver.find_element(By.ID, "radio1").click()
driver.quit()
```

## **8. Handling Alerts and Pop-ups**  
```python
from selenium import webdriver
from selenium.webdriver.common.alert import Alert
driver = webdriver.Chrome(executable_path="/home/SHIVA/chromedriver")
driver.get("https://www.example.com/alert")
alert = Alert(driver)
alert.accept()
driver.quit()
```

## **9. Uploading a File**  
```python
from selenium import webdriver
from selenium.webdriver.common.by import By
driver = webdriver.Chrome(executable_path="/home/SATHVIK/chromedriver")
driver.get("https://www.example.com/upload")
driver.find_element(By.ID, "file-upload").send_keys("/home/SATHVIK/sample.txt")
driver.quit()
```

## **10. Downloading a File**  
```python
from selenium import webdriver
from selenium.webdriver.chrome.options import Options
options = Options()
options.add_experimental_option("prefs", {"download.default_directory": "/home/SHIVA/Downloads"})
driver = webdriver.Chrome(executable_path="/home/SHIVA/chromedriver", options=options)
driver.get("https://www.example.com/download")
driver.find_element_by_link_text("Download").click()
driver.quit()
```

## **11. Taking Screenshots**  
```python
from selenium import webdriver
driver = webdriver.Chrome(executable_path="/home/SATHVIK/chromedriver")
driver.get("https://www.google.com")
driver.save_screenshot("screenshot.png")
driver.quit()
```

## **12. Scrolling a Webpage**  
```python
from selenium import webdriver
driver = webdriver.Chrome(executable_path="/home/SHIVA/chromedriver")
driver.get("https://www.example.com")
driver.execute_script("window.scrollBy(0,1000)")
driver.quit()
```

## **13. Running in Headless Mode**  
```python
from selenium import webdriver
from selenium.webdriver.chrome.options import Options
options = Options()
options.add_argument("--headless")
driver = webdriver.Chrome(executable_path="/home/SATHVIK/chromedriver", options=options)
driver.get("https://www.example.com")
driver.quit()
```

## **14. Switching Between Multiple Windows**  
```python
from selenium import webdriver
driver = webdriver.Chrome(executable_path="/home/SHIVA/chromedriver")
driver.get("https://www.example.com")
driver.execute_script("window.open('https://www.google.com');")
driver.switch_to.window(driver.window_handles[1])
driver.quit()
```

## **15. Handling Frames & iFrames**  
```python
from selenium import webdriver
from selenium.webdriver.common.by import By
driver = webdriver.Chrome(executable_path="/home/SATHVIK/chromedriver")
driver.get("https://www.example.com/iframe")
driver.switch_to.frame(driver.find_element(By.TAG_NAME, "iframe"))
driver.quit()
```

## **16. Extracting Text from a Webpage**  
```python
from selenium import webdriver
from selenium.webdriver.common.by import By
driver = webdriver.Chrome(executable_path="/home/SHIVA/chromedriver")
driver.get("https://www.example.com")
text = driver.find_element(By.TAG_NAME, "h1").text
print(text)
driver.quit()
```

## **17. Waiting for Elements to Load (Explicit Waits)**  
```python
from selenium import webdriver
from selenium.webdriver.common.by import By
from selenium.webdriver.support.ui import WebDriverWait
from selenium.webdriver.support import expected_conditions as EC
driver = webdriver.Chrome(executable_path="/home/SATHVIK/chromedriver")
driver.get("https://www.example.com")
element = WebDriverWait(driver, 10).until(EC.presence_of_element_located((By.ID, "element-id")))
driver.quit()
```

## **18. Executing JavaScript in Selenium**  
```python
from selenium import webdriver
driver = webdriver.Chrome(executable_path="/home/SHIVA/chromedriver")
driver.get("https://www.example.com")
driver.execute_script("alert('Hello from Selenium!')")
driver.quit()
```

## **19. Running Tests in Parallel with Selenium Grid**  
```python
from selenium import webdriver
from selenium.webdriver.common.desired_capabilities import DesiredCapabilities
driver = webdriver.Remote(
    command_executor='http://localhost:4444/wd/hub',
    desired_capabilities=DesiredCapabilities.CHROME)
driver.get("https://www.google.com")
driver.quit()
```

## **20. Running Selenium with CI/CD (Example with Jenkins URL)**  
```python
from selenium import webdriver
driver = webdriver.Chrome(executable_path="/home/SATHVIK/chromedriver")
driver.get("https://www.jenkins.io")
driver.quit()
```

---
