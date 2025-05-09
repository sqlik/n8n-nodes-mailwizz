# Installation and Configuration

[English](#english) | [Polski](#polski)

<a name="english"></a>
## English

This guide will walk you through the process of installing and configuring the Mailwizz node for n8n.

### Installation

#### In Cloudron Environment

If you're running n8n in a Cloudron environment, you'll need to add the node to the environment variables:

1. **Access the Cloudron File Manager**
   - Log into your Cloudron dashboard
   - Select your n8n application
   - Click on "Files" to access the file manager

2. **Edit the Environment Variables File**
   - Navigate to the `/app/data/env.sh` file
   - Add or modify the following lines:
   ```bash
   # Add n8n-nodes-mailwizz to the list of modules
   export EXTRA_NODE_MODULES="n8n-nodes-mailwizz@1.0.0"
   
   # Add mailwizz to the list of allowed external modules
   export NODE_FUNCTION_ALLOW_EXTERNAL="n8n-nodes-mailwizz"
   ```
   - If you already have other modules in these variables, add the new ones with spaces between them

3. **Restart n8n**
   - Return to the Cloudron dashboard
   - Select your n8n application
   - Click on the menu ("...") and select "Restart"

#### In Standard n8n Environment

If you're running n8n in a standard environment:

1. **Install the Node**
   - Run the following command in your n8n installation directory:
   ```bash
   npm install n8n-nodes-mailwizz
   ```

2. **Restart n8n**
   - If running as a service:
   ```bash
   sudo systemctl restart n8n
   ```
   - If running manually, stop the current process and start it again

### Configuration

Once the node is installed, you need to set up your Mailwizz API credentials:

1. **Add Mailwizz Credentials**
   - In n8n, go to the "Credentials" tab
   - Click "Add Credential"
   - Select "Mailwizz API"
   - Fill in the details:
     - **API Key**: Your Mailwizz API key (see [How to Find Your Mailwizz API Key](api-key-info.md))
     - **API URL**: The URL to your Mailwizz API (e.g., https://your-domain.com/api)
   - Click "Save"

2. **Verify Installation**
   - Create a new workflow
   - Click "+" to add a new node
   - Search for "Mailwizz" - it should appear in the list
   - If it doesn't appear, try refreshing the page or restarting n8n again

### Using the Node

The Mailwizz node can be used for various operations:

1. **Create Campaign**
   - Resource: Campaign
   - Operation: Create
   - Configure the campaign parameters, including name, type, from details, etc.
   - Optionally use category mapping to determine lists and segments based on WordPress post categories

2. **Get Lists**
   - Resource: List
   - Operation: Get All / Get
   - Retrieve all lists or a specific list from Mailwizz

3. **Get Templates**
   - Resource: Template
   - Operation: Get All / Get
   - Retrieve all templates or a specific template from Mailwizz

For a complete example workflow, see [Example Workflow](workflow-example.md).

### Troubleshooting

If you encounter issues with the Mailwizz node:

1. **Node Not Appearing**
   - Ensure the installation was successful
   - Check that n8n was restarted properly
   - Verify environment variables (for Cloudron)

2. **Connection Errors**
   - Verify your API key is correct
   - Ensure your API URL is correct and ends with `/api`
   - Check that your Mailwizz API is accessible

3. **Runtime Errors**
   - Verify the parameters you're passing to the node
   - Check the error message in the n8n execution logs
   - Ensure your Mailwizz instance has the required permissions

---

<a name="polski"></a>
## Polski

Ten przewodnik przeprowadzi Cię przez proces instalacji i konfiguracji node'a Mailwizz dla n8n.

### Instalacja

#### W Środowisku Cloudron

Jeśli używasz n8n w środowisku Cloudron, musisz dodać node do zmiennych środowiskowych:

1. **Dostęp do Menedżera Plików Cloudron**
   - Zaloguj się do panelu Cloudron
   - Wybierz aplikację n8n
   - Kliknij "Files", aby uzyskać dostęp do menedżera plików

2. **Edycja Pliku Zmiennych Środowiskowych**
   - Przejdź do pliku `/app/data/env.sh`
   - Dodaj lub zmodyfikuj następujące linie:
   ```bash
   # Dodaj n8n-nodes-mailwizz do listy modułów
   export EXTRA_NODE_MODULES="n8n-nodes-mailwizz@1.0.0"
   
   # Dodaj mailwizz do listy dozwolonych zewnętrznych modułów
   export NODE_FUNCTION_ALLOW_EXTERNAL="n8n-nodes-mailwizz"
   ```
   - Jeśli masz już inne moduły w tych zmiennych, dodaj nowe, oddzielając je spacjami

3. **Restart n8n**
   - Wróć do panelu Cloudron
   - Wybierz aplikację n8n
   - Kliknij menu ("...") i wybierz "Restart"

#### W Standardowym Środowisku n8n

Jeśli używasz n8n w standardowym środowisku:

1. **Instalacja Node'a**
   - Uruchom następującą komendę w katalogu instalacyjnym n8n:
   ```bash
   npm install n8n-nodes-mailwizz
   ```

2. **Restart n8n**
   - Jeśli uruchomiony jako usługa:
   ```bash
   sudo systemctl restart n8n
   ```
   - Jeśli uruchomiony ręcznie, zatrzymaj bieżący proces i uruchom go ponownie

### Konfiguracja

Po zainstalowaniu node'a, musisz skonfigurować dane uwierzytelniające do API Mailwizz:

1. **Dodawanie Poświadczeń Mailwizz**
   - W n8n przejdź do zakładki "Credentials"
   - Kliknij "Add Credential"
   - Wybierz "Mailwizz API"
   - Uzupełnij dane:
     - **API Key**: Twój klucz API Mailwizz (zobacz [Jak Znaleźć Klucz API Mailwizz](api-key-info.md))
     - **API URL**: URL do Twojego API Mailwizz (np. https://twoja-domena.com/api)
   - Kliknij "Save"

2. **Weryfikacja Instalacji**
   - Utwórz nowy workflow
   - Kliknij "+", aby dodać nowy node
   - Wyszukaj "Mailwizz" - powinien pojawić się na liście
   - Jeśli nie pojawia się, spróbuj odświeżyć stronę lub zrestartować n8n ponownie

### Używanie Node'a

Node Mailwizz może być używany do różnych operacji:

1. **Tworzenie Kampanii**
   - Zasób: Campaign
   - Operacja: Create
   - Skonfiguruj parametry kampanii, w tym nazwę, typ, dane nadawcy itp.
   - Opcjonalnie użyj mapowania kategorii, aby określić listy i segmenty na podstawie kategorii wpisu WordPress

2. **Pobieranie List**
   - Zasób: List
   - Operacja: Get All / Get
   - Pobierz wszystkie listy lub konkretną listę z Mailwizz

3. **Pobieranie Szablonów**
   - Zasób: Template
   - Operacja: Get All / Get
   - Pobierz wszystkie szablony lub konkretny szablon z Mailwizz

Pełny przykładowy przepływ pracy znajdziesz w [Przykładowym Przepływie Pracy](workflow-example.md).

### Rozwiązywanie Problemów

Jeśli napotkasz problemy z node'em Mailwizz:

1. **Node Nie Pojawia Się**
   - Upewnij się, że instalacja zakończyła się pomyślnie
   - Sprawdź, czy n8n zostało poprawnie zrestartowane
   - Sprawdź zmienne środowiskowe (dla Cloudron)

2. **Błędy Połączenia**
   - Sprawdź, czy Twój klucz API jest poprawny
   - Upewnij się, że URL API jest poprawny i kończy się na `/api`
   - Sprawdź, czy Twoje API Mailwizz jest dostępne

3. **Błędy Wykonania**
   - Sprawdź parametry, które przekazujesz do node'a
   - Sprawdź komunikat o błędzie w logach wykonania n8n
   - Upewnij się, że Twoja instancja Mailwizz ma wymagane uprawnienia
