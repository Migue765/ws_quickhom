from selenium import webdriver
from selenium.webdriver import ActionChains
from selenium.webdriver.common.by import By
from selenium.webdriver.support import expected_conditions as EC
from selenium.webdriver.support.ui import  WebDriverWait
from selenium.webdriver.chrome.service import Service
from webdriver_manager.chrome import ChromeDriverManager
import time
from bs4 import BeautifulSoup
from selenium.webdriver.common.keys import Keys
import json
# Configuraciones de webDriver
options = webdriver.ChromeOptions()

### Opción para abrir en ventana completa o ventana flotante (Variar según sea necesario)
# options.add_argument('--start-maximized')
options.add_argument('--start-size=250,250')
options.add_argument('--disable-extensions')
options.add_argument('--kiosk-printing')
# Creo el objeto driver para que se abra la vanta
driver = webdriver.Edge(options=options, service=Service(ChromeDriverManager().install()))
# Posiciono la ventan en la esquina superio izquierda
driver.set_window_position(0, 0)


# Voy a la pagina de computrabajo para login
driver.get('https://fincaraiz.com.co/')
time.sleep(3)


#Doy clic a iniciar seción
WebDriverWait(driver,1)\
    .until(EC.element_to_be_clickable((By.XPATH,'/html/body/div[2]/div/div[3]/div/div[2]/div[1]/div[1]/div[1]/div/div/div')))\
    .click()
print("Hago click en la entrada de texto")
time.sleep(2)


#Ingreso el corre
# Ingreso correo electronico
print("introduciendo texto")
WebDriverWait(driver, 1)\
    .until(EC.element_to_be_clickable((By.XPATH, '/html/body/div[2]/div/div[3]/div/div[2]/div[1]/div[1]/div[1]/div/div/div/input')))\
    .send_keys('Bogotá, Bogotá, d.c.')
time.sleep(5)

print("damos enter")
# Ingreso contraseña
WebDriverWait(driver, 1)\
    .until(EC.element_to_be_clickable((By.XPATH, '/html/body/div[2]/div[1]/div[3]/div/div[2]/div[1]/div[1]/button')))\
    .click()
time.sleep(5)

soup = BeautifulSoup(driver.page_source, "html.parser")
print(soup)