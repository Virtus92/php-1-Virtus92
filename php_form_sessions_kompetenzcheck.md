# PHP 1 Kompetenzcheck

**Mit Formularen Daten versenden/ empfangen, mit Sessions arbeiten**

Das Ziel des Komptenzchecks ist es, den Umgang mit PHP Sessions zu üben. Sessions werden verwendet, um Daten über mehrere Anfragen desselben Benutzers zu speichern und abzurufen. In der Aufgabe erstellst du ein einfaches Anmelde-System unter Verwendung von Sessions.  

**Anforderungen:**
1. Erstelle ein Anmeldeformular:  
    - Erstelle ein HTML-Formular mit Feldern für Benutzername und Passwort.
    - Füge einen Submit-Button hinzu, um das Formular abzusenden.
2. Erstelle eine Datei namens "login.php":  
    - In der Datei "login.php" schreibe PHP-Code, um den Anmeldeprozess zu verarbeiten.  
    - Führe eine grundlegende Validierung durch, um sicherzustellen, dass die Felder nicht leer sind.  
    - Vergleiche den Benutzernamen und das Passwort mit einem vordefinierten Satz von Anmeldeinformationen (vorab festgelegte, statische Werte).  
    - Wenn die Anmeldeinformationen übereinstimmen, speichere den Benutzernamen in einer Session-Variablen ab unter dem Key 'username'.  
    - Leite den Benutzer bei erfolgreicher Anmeldung auf eine "dashboard.php"-Seite um (Weiterleitung mit header() https://www.php.net/manual/en/function.header.php).  
    - Wenn die Anmeldeinformationen nicht übereinstimmen, zeige eine Fehlermeldung an und biete die Möglichkeit, es erneut zu versuchen.  
3. Erstelle eine Datei namens "dashboard.php":  
    - In der Datei "dashboard.php" schreibe PHP-Code, um das Dashboard des Benutzers anzuzeigen.  
    - Starte die Session     
    - Überprüfe, ob die Session-Variable `$_SESSION['username']` gesetzt und nicht leer ist.  
    - Wenn die Session-Variable gesetzt ist, zeige eine Begrüßungsnachricht mit dem Benutzernamen an.  
    - Wenn die Session-Variable nicht gesetzt ist, leite den Benutzer zurück zur Anmeldeseite um. (Weiterleitung mit header() https://www.php.net/manual/en/function.header.php)  
4. Teste deine Lösung:  
    - Öffne die Anmeldeseite in einem Browser.  
    - Gib gültige Anmeldedaten ein und sende das Formular ab.  
    - Überprüfe, ob du auf die Dashboard-Seite umgeleitet wirst und die Begrüßungsnachricht angezeigt wird.  
    - Versuche auf die Dashboard-Seite zuzugreifen, ohne dich anzumelden, und überprüfe, ob du zur Anmeldeseite zurückgeleitet wirst.  
5. Optional: Passe den PHP-Code an, um zusätzliche Funktionen einzubauen:  
    - Implementiere eine Abmeldefunktion, die die Session zerstört und den Benutzer zur Anmeldeseite umleitet.  
    - Speichere zusätzliche Benutzerinformation  
---
**EN:** 

The goal of this competency check is to practice working with PHP sessions. Sessions are used to store and retrieve data across multiple requests from the same user. In this exercise, you will create a simple login system using sessions.  

**Instructions:**

1. Create a login form:  
    - Create an HTML form with fields for username and password.  
    - Add a submit button to submit the form.  
2. Create a file named "login.php":  
    - In the "login.php" file, write PHP code to handle the login process.  
    - Perform basic validation to ensure the fields are not empty.  
    - Compare the username and password with a predefined set of login credentials (predefined, static values).  
    - If the login credentials match, store the username in a session variable with the key 'username'.  
    - Redirect the user to a "dashboard.php" page upon successful login (use the header() function for redirection, https://www.php.net/manual/en/function.header.php).  
    - If the login credentials do not match, display an error message and provide the option to try again.  
3. Create a file named "dashboard.php":  
    - In the "dashboard.php" file, write PHP code to display the user's dashboard.  
    - Start the session.  
    - Check if the session variable `$_SESSION['username']` is set and not empty.  
    - If the session variable is set, display a welcome message with the username.  
    - If the session variable is not set, redirect the user back to the login page (use the header() function for redirection,  https://www.php.net/manual/en/function.header.php ).
4. Test your solution:  
    - Open the login page in a browser.  
    - Enter valid login credentials and submit the form.  
    - Verify if you are redirected to the dashboard page and the welcome message is displayed.  
    - Try accessing the dashboard page without logging in and verify if you are redirected back to the login page.  
5. Optional: Customize the PHP code to add additional features:  
    - Implement a logout function that destroys the session and redirects the user to the login page.  
    - Store additional user information.  