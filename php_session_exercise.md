# PHP 1 Übung 2
**Session Exercise**

Ziel: In dieser Übung lernt ihr den grundlegenden Umgang mit PHP-Sessions . Ihr werdet Werte in einem Skript speichern und in einem anderen Skript darauf zugreifen.  
Zur Erinnerung: https://www.w3schools.com/php/php_sessions.asp  

**Aufgabe:**  
1. Erstelle das erste PHP-Skript:  
    - Erstelle eine Datei namens "page1.php".  
    - Starte die Session am Anfang des Skripts mit der Funktion `session_start()`.  
    - Setze im Skript zwei Session-Variablen mit Werten deiner Wahl. Zum Beispiel kannst du `$_SESSION['username']` auf einen Benutzernamen und `$_SESSION['email']` auf eine E-Mail-Adresse setzen.  
    - Gib eine Nachricht aus, die angibt, dass die Werte in der Session gespeichert wurden.  
2. Erstelle das zweite PHP-Skript:  
    - Erstelle eine Datei namens "page2.php".  
    - Starte die Session am Anfang des Skripts mit der Funktion `session_start()`.  
    - Greife im Skript auf die Session-Variablen zu, die in "page1.php" gesetzt wurden (`$_SESSION['username']` und `$_SESSION['email']`) und speichere sie in separaten Variablen.  
    - Gib die Werte der Session-Variablen auf der Seite aus.
3. Teste deine Lösung:  
    - Öffne "page1.php" in einem Browser.  
    - Überprüfe, ob die Nachricht angezeigt wird, die darauf hinweist, dass die Werte in der Session gespeichert wurden.  
    - Navigiere im selben Browser oder einem neuen Tab zu "page2.php".  
    - Überprüfe, ob die in der Session auf "page1.php" gespeicherten Werte korrekt auf "page2.php" angezeigt werden.  
---
**EN:**

**Goal:**   

In this exercise, you will learn the basics of working with PHP sessions. You will store values in one script and access them in another script.  
Little Assistance: https://www.w3schools.com/php/php_sessions.asp  

Instructions:  
1. Create the first PHP script:  
    - Create a file named "page1.php".  
    - Start the session at the beginning of the script using the `session_start()` function
    - Set two session variables in the script with values of your choice. For example, you can set `$_SESSION['username']` to a username and `$_SESSION['email']` to an email address.  
    - Display a message indicating that the values have been stored in the session.  
2. Create the second PHP script:  
    - Create a file named "page2.php".  
    - Start the session at the beginning of the script using the `session_start()` function.  
    - Access the session variables set in "page1.php" (`$_SESSION['username']` and `$_SESSION['email']`) in the script and store them in separate variables.  
    - Display the values of the session variables on the page.  
3. Test your solution:  
- Open "page1.php" in a browser.  
- Check if the message indicating that the values have been stored in the session is displayed.  
- Navigate to "page2.php" in the same browser or a new tab.  
- Verify if the values stored in the session on "page1.php" are correctly displayed on "page2.php".  
