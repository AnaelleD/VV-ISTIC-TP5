## Page Object Model

The image below shows the poll page of the [Simba Organizer](https://github.com/barais/doodlestudent/) application discussed in classes.

![Simba Organizer Poll page](simba-poll-page.png)

Write in this document the interface of a page object class for this page.

## Answer

Voici le code de l'interface, également disponible dans le dossier code dans simbaPageObject:

```java
package com.vv.tp5;

import java.util.List;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;

public interface SimbaPageObject {

    // immutable data structures
    public final String title, place;
    public final int creationTimer;
    public final boolean hasMeal;

    public final List<String> availabilities; // String -> date + horaires
    public final Map<String, List<Integer>> participations; // String nom -> index dans avails
    public final Map<String, String> comments; // commentaire -> auteur

    public SimbaPageObject typeName(String name);

    public SimbaPageObject typeEmail(String email);

    public SimbaPageObject toggleHasAgenda();

    public SimbaPageObject toggleMealPreferences();

    public SimbaPageObject toggleView();

    public SimbaPageObject selectAvailabilities(String... dispos);

    public SimbaPageObject typeAuthor(String auteur);

    public SimbaPageObject typeComment(String comment);

    public SimbaPageObject submitComment();

    public List<WebElement> errors();

}
```
