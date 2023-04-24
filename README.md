# Python-manipulator
# The python program using selenium library and webdriver which would open the browser, open the desired site, then enter each word by word, line by line, line by line # from the specified text document, reaching the last word in the last line would complete this process.

from selenium import webdriver
import time

# Path to your webdriver
driver_path = 'path/to/your/webdriver'

# Create an instance of Chrome webdriver
driver = webdriver.Chrome(driver_path)

# Open the desired website
driver.get('https://www.example.com')

# Path to the text file
text_file_path = 'path/to/your/textfile'

# Read the contents of the text file
with open(text_file_path, 'r') as file:
    # Read line by line
    for line in file:
        # Split line into words
        words = line.split()
        # Enter each word in the input field on the website
        for word in words:
            input_field = driver.find_element_by_id('input_field_id')
            input_field.send_keys(word + ' ')
            time.sleep(0.5) # wait for 0.5 seconds before entering the next word

# Close the browser window
driver.quit()
Make sure to replace path/to/your/webdriver, https://www.example.com, path/to/your/textfile, and input_field_id with the appropriate values for your specific use case.
