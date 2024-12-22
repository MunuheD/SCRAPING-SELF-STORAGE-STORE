# SCRAPING-SELF-STORAGE-STORE
The project aimed to extract business names and addresses from the Storage Site Directory: https://www.ssauk.com/storage-site-directory.html. 
The project utilizes Selenium for dynamic page loading and BeautifulSoup for HTML parsing. The following steps are executed:

Libraries Imported
time: For introducing delays in the execution.
random: To generate random sleep intervals.
requests: For making HTTP requests.
re: For using regular expressions.
BeautifulSoup: For parsing HTML documents.
selenium: For automating web browser interaction.
webdriver_manager: To manage the installation of the ChromeDriver.
Functions Defined
random_sleep():

Introduces a random sleep duration between 2 to 5 seconds to mimic human browsing behavior.
click_load_more(driver):

Continuously clicks the "Load More" button on the website until it is no longer available. It handles potential exceptions that may arise during the clicking process.
getpagesource():

Sets up the Chrome WebDriver and loads the initial URL. It calls click_load_more() to ensure all content is loaded and returns the complete page source for further processing.
get_store_and_address():

Extracts store names and addresses from the loaded page source and appends them to respective lists.
links():

Finds and collects all relevant links to individual storage sites from the main page.
crawl():

Iterates through the collected links, makes HTTP requests to each link, and extracts contact details and website links. It includes error handling and retries for failed requests.
Data Storage
The scraped data is stored in a Pandas DataFrame and exported to an Excel file named Scraping-ssauk2.xlsx in the specified directory.
Execution
The functions are executed sequentially to perform the web scraping task and output the results in Excel format.
Output
A success message is printed upon successful data download, indicating the location of the saved file.
