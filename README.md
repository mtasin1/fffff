import subprocess
import random
import string

def generate_password(length):
    characters = string.ascii_letters + string.digits + string.punctuation
    password = ''.join(random.choice(characters) for _ in range(length))
    return password

def connect_to_wifi(ssid, password):
    command = f"nmcli device wifi connect {ssid} password {password}"
    subprocess.run(command, shell=True)

# Generate a random password
password = generate_password(10)

# Replace 'YourWiFiSSID' with the name of your WiFi network
ssid = 'Nejamuddin'

# Connect to WiFi using the generated password
connect_to_wifi(ssid, password)
