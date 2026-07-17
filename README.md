# Smartphone Addiction Analysis

Is there a direct correlation between the amount of notifications someone gets per day and their self reported smartphone addiction level?


## Authors

- [@BugBananaLiver](https://www.github.com/BugBananaLiver)

## Sources

**Smartphone_Usage_And_Addiction** 
*Kaggle -https://www.kaggle.com/datasets/zahranusratt/smartphone-usage-and-addiction-analysis-dataset*


**Sleep_mobile_stress_dataset**
*Kaggle -https://www.kaggle.com/datasets/jayjoshi37/sleep-screen-time-and-stress-analysis*
 


## Content

The datasets come from different studies and do not contain the same participants. Rather than joining individuals across datasets,  this project integrates both datasets into a single relational database and compares patterns in smartphone use, stress, addiction, and sleep across the two populations. 



## Entity Relationship Diagram (ERD)

```mermaid
erDiagram

    USERS_D1 {
        TEXT user_id PK
        INTEGER age
        TEXT gender
    }

    BEHAVIOR_D1 {
        TEXT user_id FK
        INTEGER notifications_per_day
        INTEGER app_opens_per_day
        TEXT stress_level
        TEXT addiction_level
        TEXT addicted_label
    }

    HOURS_D1 {
        TEXT user_id FK
        REAL daily_screen_time_hours
        REAL social_media_hours
        REAL gaming_hours
        REAL work_study_hours
        REAL sleep_hours
        REAL weekend_screen_time
    }

    USERS_D2 {
        TEXT user_id PK
        INTEGER age
        TEXT gender
        TEXT occupation
    }

    WELLBEING_D2 {
        TEXT user_id FK
        REAL sleep_quality_score
        REAL stress_level
        INTEGER caffeine_intake_cups
        INTEGER physical_activity_minutes
        INTEGER notifications_received_per_day
        REAL mental_fatigue_score
        TEXT stress_level_rank
        TEXT screen_time_category
    }

    HOURS_D2 {
        TEXT user_id FK
        REAL daily_screen_time_hours
        INTEGER phone_usage_before_sleep_minutes
        REAL sleep_duration_hours
    }

    USERS_D1 ||--|| BEHAVIOR_D1 : contains
    USERS_D1 ||--|| HOURS_D1 : tracks

    USERS_D2 ||--|| WELLBEING_D2 : contains
    USERS_D2 ||--|| HOURS_D2 : tracks
```


## FAQ

#### Is the DataSet synthetic or organic?

    The DataSet was synthetically created to represent phone usage. This is not organic data.

#### How many hours went into the creation of this project?

    As of May 17 2026, roughly 34 hours have gone into this project.

    As of July 8 2026, roughly 51 hours have gone into this project.

    As of July 13 2026, roughly 62 hours have gone into this project.
