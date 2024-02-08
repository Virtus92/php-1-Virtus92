# PHP 1 Übung
**Form Exercise**

Aufgabe:  
1. Erstelle ein HTML-Formular mit folgenden Feldern:  
    - Name (Texteingabefeld, Pflichtfeld)  
    - E-Mail (E-Mail-Eingabefeld, Pflichtfeld)  
    - Submit-Button  
2. Erstell eine Datei namens "process.php", um das Formular zu verarbeiten.  
3. Setze zuerst die `action` des Formulars auf "process.php" und die `method`- Eigenschaft auf "post".  
4. In der Datei "process.php" schreibe PHP-Code, um das Formular zu verarbeiten:  
    - Überprüfe die Requestmethode, um herauszufinden, ob es sich um einen POST- oder GET-Request handelt. (Tipp: $_SERVER["REQUEST_METHOD"])  
    - Wenn es ein **POST** Request ist:  
        - Greife auf die Daten im $_POST-Array zu.  
        - Speichere den Namen und die E-Mail in separaten Variablen.
        - Zeige eine Nachricht an, dass die Daten mit der POST-Methode empfangen wurden  
        - Zeige den Namen und die E-Mail auf der Seite an.  
    - Wenn es ein **GET** Request ist:  
        - Greife auf die Daten im $_GET-Array zu.  
        - Speichere den Namen und die E-Mail in separaten Variablen.  
        - Zeige eine Nachricht an, dass die Daten mit der GET-Methode empfangen wurden. 
        - Zeige den Namen und die E-Mail auf der Seite an.  
5. Teste deine Lösung:  
    - Gib einen Namen und E-Mail in das Formular ein.  
    - Klicke auf den Button.  
6. Ändere die `method`-Eigenschaft des Formulars von "post" auf "get".  
7. Teste deine Lösung erneut:  
    - Gib einen Namen und eine E-Mail in das Formular ein.  
    - Klicke auf den Button.  
    - Achte auf die angezeigte Nachricht und die übermittelten Daten.  

Hinweis: Du darfst gerne mit der Aufgabe etwas experimentieren. Das Ziel ist es, Erfahrung im Umgang mit Formulardaten, POST- und GET-Anfragen sowie im Zugriff auf die übermittelten Daten in PHP zu sammeln.
___
**EN:**

Task:  

1. Create an HTML form with the following fields:  
    - Name (text input field, required)  
    - Email (email input field, required)  
    - Submit button  
2. Create a file named "process.php" to handle the form submission.  
3. Set the `action` attribute of the form to "process.php" and the `method` attribute to "post".  
4. In the "process.php" file, write PHP code to handle the form:  
    - Check the request method to determine if it's a POST or GET request. (Hint: $_SERVER["REQUEST_METHOD"])  
    - If it's a **POST** request:  
        - Access the data sent through the $_POST array.  
        - Store the name and email values in separate variables.  
        - Display a message indicating that the data was received using the POST method
        - Display the name and email on the page.  
    - If it's a **GET** request:  
        - Access the data sent through the $_GET array.  
        - Store the name and email values in separate variables.  
        - Display a message indicating that the data was received using the GET method. 
        - Display the name and email on the page.  
5. Test your solution:  
    - Enter a name and email in the form.  
    - Click the Submit button.  
6. Change the `method` attribute of the form from "post" to "get".  
7. Test your solution again:  
    - Enter a name and email in the form.  
    - Click the Submit button.  
    - Observe the displayed message and the submitted data.  

Note: Feel free to explore and experiment beyond this task. The goal is to gain experience in handling form data, working with POST and GET requests, and accessing the submitted data in PHP.  