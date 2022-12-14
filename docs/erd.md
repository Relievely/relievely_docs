```mermaid
erDiagram
PERSONA {
        int id PK "Id of the companion"
        string name "Name of the companion"
        string character "Unicode character of the emoji"
    }
USERDATA {
        string name
        json order
        int personaID
    }
USERDATA || -- |{ PERSONA : "References"
```
```mermaid
erDiagram   
    ACTIVITY {
        int id PK "Id of the activity"
        string name "Name of the activity"
        string description "Description of the activity"
        enum category "Category Id of the activity (Guided or Non-Guided)"
    }
    ACTIVITY || -- |{ REMINDERS-ACTIVITY : "Can have"

    ACITVITY-LOG {
        int id PK "Id of the log item"
        int activityID FK "Id of the corresponding activity"
        int timeStart "Start of the activity session"
        int timeEnd "End of the activity session"
    }
    ACITVITY-LOG || -- |{ ACTIVITY : "References to"
    ACITVITY-LOG || -- |{ ACTIVITY-RATING : "Can have"

    ACTIVITY-RATING {
        int id PK "Id of the rating item"
        int logID FK "Id of the corresponding log item"
        bool state "Boolean state if this was good or bad"
    }

    REMINDERS-ACTIVITY {
        int id PK "Id of the reminder"
        string name "Name of the reminder"
        dateTime triggerTime "Time of the reminder to be triggered"
        int referenceID FK "Id for the activity"
    }
```
```mermaid
erDiagram
    GOALS {
        int id PK "Id of the goal"
        string name "Name of the goal"
        date startTime "Time when this goals was created"
        date endTime "Time when this goal should be completed"
        int categoryId FK "Id of the corresponding category"
    }
    GOALS || -- |{ GOALS-CATEGORY : contains
    GOALS-CATEGORY {
        int id PK "Id of the goal category"
        string name "Name of the goal category"
    }
    GOALS || -- |{ REMINDERS-GOALS : "can have multiple"

    REMINDERS-GOALS {
        int id PK "Id of the reminder"
        string name "Name of the reminder"
        dateTime triggerTime "Time of the reminder to be triggered"
        int referenceID FK "Id for the goal it represents"
    }
```
```mermaid
erDiagram
    PROGRESS {
        int id PK "Id of the progress item"
        date time "Time when this item was created"
        enum moodType "Enumeration that has different states of mood"
    }
    NOTES {
        int id PK "Id of the note"
        string content "Content of the note"
        int progressID FK "Id of the corresponding progress item"
    }
    PROGRESS || -- |{ NOTES : "can have"
```
```mermaid
erDiagram
    WIKI {
        int id PK "Id of the information"
        string title "Title of the information"
        string content "Content of the information"
        string excerpt "Short version of the information"
    }
```
