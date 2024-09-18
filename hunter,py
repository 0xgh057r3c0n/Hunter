import requests
from termcolor import colored

# Hunter.io API Key
API_KEY = 'YOUR_API_KEY'

# Function to display a colorful banner
def print_banner():
    banner = """
   ⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⢀⣴⣶⣶⣶⣶⣶⣶⣤⡀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⣀⣀⢠⣿⣿⣿⣿⣿⣿⣿⣿⠿⠃⣀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⣾⣿⣿⡀⠻⠿⣿⠿⣿⣿⣿⠏⣰⣿⣿⣷⣄⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⢀⣾⣿⣿⣿⣿⣶⡆⠀⠀⠀⠀⠉⠀⠻⣿⣿⣿⣿⣷⡄⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⢸⣿⣿⣿⣿⣿⡿⠃⠀⠀⠀⠀⠀⠀⠀⠙⠛⣉⣭⣙⢻⣆⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⣴⣶⣤⣉⠛⣛⣉⠁⠀⠀⢀⣤⣴⣦⣤⣀⣶⡆⣾⣿⣿⣿⣯⠛⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⢠⣿⣿⣿⣿⣿⣿⡏⠀⠀⣰⠟⠉⠉⠙⢿⣿⣿⣇⢻⣿⣿⣿⣿⠆⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠈⣿⣿⣿⣿⣿⡟⠀⠀⠀⠁⠀⠀⠀⠀⢸⣿⣿⣿⣦⡙⠿⣿⠟⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠿⢋⣩⣭⣉⠀⠀⠀⠀⠀⠀⠀⠀⠀⠈⣿⣿⣿⣿⣿⣿⡖⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⣰⣿⣿⣿⣿⣷⣄⠀⠀⠀⠀⠀⠀⢠⣴⡾⣿⣿⡛⢋⠉⣠⣄⡀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⣿⣿⣿⠟⣉⣤⣶⣤⣤⡀⠀⠀⣴⣿⠟⠁⣩⣿⣿⣿⣿⣿⣻⣷⣄⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⢻⣿⢇⣾⣿⣿⣿⣿⣿⣿⡆⠺⠿⠋⢀⣾⣿⡿⢫⣾⣿⠟⢮⣝⠿⣷⡄⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠀⠀⠀⠀⢀⣶⣳⣾⣷⡄⠀⠈⢿⢸⣿⣿⣿⡿⣫⣶⣿⣿⣿⣷⣄⢻⡿⢋⣴⣿⣿⠟⣠⣴⡿⠷⣟⣯⣤⣶⡶⣶⣄⡀⠀⣀⣀⣀⠀⠀⠀⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠀⢀⣠⣴⣾⡿⠃⠈⠛⢿⣦⣀⣈⡈⢿⣿⡟⣼⣿⣿⣿⣿⣿⠿⣛⣃⣀⣘⠿⠟⢣⣾⣿⡿⠃⣴⣿⣿⣿⣿⣿⢸⣿⣿⣿⣿⣿⣿⣿⠆⠀⠀⠀⠀⠀
⠀⠀⠀⠀⢀⣾⣼⡿⠋⠉⠀⠀⠀⠀⠀⠘⠿⣸⠧⡄⠻⠁⣿⣿⣿⣿⢏⣴⣿⣿⣿⣿⣿⣷⣄⢻⡟⠋⠀⣼⣿⣿⣿⠋⠉⠵⠿⣿⣿⣿⣿⣿⢋⣷⣿⣦⡀⠀⠀⠀
⠀⠀⠀⠀⣼⣿⠋⠀⢠⣶⣶⣶⣾⣿⣿⣿⣿⣷⡄⣶⣶⣆⣻⣿⣿⢯⣿⣿⣿⣿⣿⣿⣿⣿⣿⣇⠁⣀⣠⣴⣮⢻⠇⠀⣷⡄⠀⠀⠹⣿⣿⣷⣿⣿⣿⣿⣷⣤⡀⠀
⠀⠀⠀⠀⣿⡇⠀⢰⣯⣽⠉⠉⢩⣍⣉⣉⣩⣭⣥⣭⣍⣻⣥⣭⣭⣜⠿⣿⣿⣿⣿⣿⣿⣿⠿⢛⡸⢿⣿⣿⡿⠀⠀⠀⢹⣷⣀⣀⠀⠀⠁⢿⣿⣿⣿⣿⣿⣿⣿⣆
⠀⠀⢀⣼⠿⠃⠀⢸⣿⡇⠀⢸⣿⠻⠟⠿⠿⠿⠿⢿⣿⣿⠋⠛⣻⣭⣴⣶⣄⠉⠛⠿⠟⢫⣾⣿⣿⣆⣀⡈⠀⠀⠀⠀⠀⠉⠛⠉⠀⠀⠀⢘⣿⣿⣿⣿⣿⣿⣿⣿
⣠⡴⠟⠛⠁⠀⠀⢸⣿⡧⠀⣾⣿⡀⠀⢠⣼⡻⣿⣿⣿⣿⣿⣿⠎⣿⠿⠟⠃⣀⣴⣿⣿⠈⣙⡻⠿⠃⢾⣷⠀⠀⠀⠀⠀⠀⠀⠀⠀⣠⣾⣿⣿⣿⣿⣿⣿⣿⣿⠟
⠀⠀⠀⠀⠀⠀⠀⠀⢿⡇⠀⢿⣿⡇⠀⣼⣿⡇⠉⠙⠛⠋⠉⠀⠀⠀⠀⠀⣾⡛⠻⣿⡇⠀⣿⣧⠀⠀⠘⠁⠀⠀⠀⠀⠀⠀⠀⠀⢸⣿⣿⣿⠿⠿⠃⠀⢠⣤⣴⡆
⠀⠀⠀⠀⠀⠀⠀⠀⢸⣿⡇⢸⣿⡇⠀⣿⣿⡇⠀⠀⠀⣠⠾⠛⢿⣿⣷⣿⣿⣿⣧⠹⠃⠀⠈⠋⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⣿⣿⣿⠇⠀⠀⠀⠀⣼⣿⣿⠃
⠀⠀⠀⠀⠀⠀⠀⠀⣠⣿⠇⢸⣶⡅⢐⡿⠏⠀⠀⠀⢀⣴⣿⣷⡌⠿⠿⠿⠿⠿⠟⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⢹⡏⠀⠀⠀⠀⢀⣤⣿⣿⠋⠀
⠀⠀⠀⠀⠀⠀⠀⠜⠋⠀⠀⠀⢻⣧⠘⣿⣦⠀⠀⢠⣿⣿⣿⣿⡇⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠁⠀⠀⠀⢀⣼⣿⠟⠁⠀⠀
⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⢀⣴⡏⠀⠘⢿⣧⠀⢸⣿⣿⣿⣿⣿⣶⡄⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠒⠛⠋⠁⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⡾⠟⠀⠀⠀⢰⣿⠆⢸⣿⣿⣿⣿⢿⣿⣧⣤⣶⣶⣦⣤⣀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⢀⡾⠋⠀⢸⣿⣿⡿⣱⣿⣿⣿⣿⣿⣿⣿⣿⣿⣷⣤⣠⣤⣤⣤⣤⣶⣶⣤⣄⡀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠈⠀⠀⠀⠈⣿⣿⢧⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⠿⠿⠿⣷⡀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠘⢿⠇⢿⣿⣿⣿⣿⣿⣿⣿⣿⡿⢋⣉⠉⠻⠋⠁⠀⠉⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠈⠻⣿⣿⣿⣿⣿⠿⠋⢰⣿⣿⣧⣦⡀⣀⣴⣶⣤⣴⠆⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀
⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠉⠉⠁⠀⠀⠀⠀⠙⠛⠿⠿⠿⠿⠿⠛⠋⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀⠀

    ooooo ooooo ooooo  oooo oooo   oooo ooooooooooo   ooooooo  oooooooooo  
     888   888   888    88   8888o  88  88  888  88 o88    888o 888    888 
     888ooo888   888    88   88 888o88      888         88888o  888oooo88  
     888   888   888    88   88   8888      888     88o    o888 888  88o   
    o888o o888o   888oo88   o88o    88     o888o      88ooo88  o888o  88o8                                                
    
    A Python tool that uses Hunter.io’s API to search and verify emails for a given domain and to easily identify email validity based on score.
    Version: 1.0
    Author: G4UR4V007
    """
    print(colored(banner, 'cyan', attrs=['bold']))

# Function to get emails from Hunter.io based on domain
def get_emails_from_hunter(domain):
    """
    Fetches emails associated with a domain from Hunter.io using the API key.
    """
    url = f"https://api.hunter.io/v2/domain-search?domain={domain}&api_key={API_KEY}"
    
    print(colored(f"\n[*] Fetching emails for domain: {domain}...", 'yellow'))

    try:
        response = requests.get(url)
        
        if response.status_code == 200:
            data = response.json()
            emails = data['data']['emails']
            
            if emails:
                print(colored(f"\n[*] Found {len(emails)} emails for {domain}:", 'green'))
                for email in emails:
                    email_address = email['value']
                    print(colored(f"[*] {email_address} ({email['type']})", 'magenta'))
                    # Verify each email
                    verify_email(email_address)
            else:
                print(colored(f"\n[*] No emails found for domain {domain}.", 'red'))
        else:
            print(colored(f"\n[*] Failed to fetch data. HTTP Status Code: {response.status_code}", 'red'))

    except requests.RequestException as e:
        print(colored(f"\n[*] Error fetching data from Hunter.io: {e}", 'red'))

# Function to verify email using Hunter.io
def verify_email(email):
    """
    Verifies the validity of an email address using Hunter.io's email verification API.
    """
    url = f"https://api.hunter.io/v2/email-verifier?email={email}&api_key={API_KEY}"
    
    print(colored(f"[*] Verifying '{email}'", 'green'))

    try:
        response = requests.get(url)
        
        if response.status_code == 200:
            data = response.json()
            score = data['data']['score']

            if score < 60:
                result = "risky"
                color = 'red'
            elif score < 100:
                result = "valid and active"
                color = 'yellow'
            else:
                result = "valid and highly active"
                color = 'green'
            
            print(colored(f"[*] {email} is {result}", color))
            print(colored(f"[*] Score: {score}", 'blue'))

        else:
            print(colored(f"[*] Failed to verify {email}. HTTP Status Code: {response.status_code}", 'red'))

    except requests.RequestException as e:
        print(colored(f"[*] Error verifying email {email}: {e}", 'red'))

# Main function to run the tool
def main():
    print_banner()

    # User input for domain
    domain_to_check = input(colored("[*] Enter the domain to check for emails (e.g., example.com): ", 'green'))

    # Check emails for the provided domain using Hunter.io
    get_emails_from_hunter(domain_to_check)

# Run the tool
if __name__ == "__main__":
    main()
