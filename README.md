# ⚽ World Cup Database

A relational database project built with **PostgreSQL**, **SQL**, and **Bash scripting** to manage and analyze World Cup match data.

---

## Project Overview

This project stores and analyzes World Cup data including:

- Teams  
- Matches  
- Goals  
- Tournament rounds  
- Champions by year  

The database is normalized and uses primary and foreign keys to ensure relational integrity.

---

## Technologies Used

- PostgreSQL  
- SQL  
- Bash  

---

## Database Structure

### `teams`
- `team_id` (Primary Key)  
- `name` (Unique)

### `games`
- `game_id` (Primary Key)  
- `year`  
- `round`  
- `winner_id` (Foreign Key → teams.team_id)  
- `opponent_id` (Foreign Key → teams.team_id)  
- `winner_goals`  
- `opponent_goals`  

---

## Data Import

The Bash import script:

- Truncates existing data  
- Reads from `games.csv`  
- Inserts unique teams  
- Inserts games with proper foreign key relationships  
- Supports test mode (`worldcuptest`)  

Run:

```bash
./insert_data.sh
```

Test mode:

```bash
./insert_data.sh test
```

---

## Queries Included

The query script performs:

- Total goals scored  
- Average goals per game  
- Most goals in a match  
- 2018 tournament winner  
- Champions by year  
- Teams in specific rounds  
- Teams starting with specific letters  

Run:

```bash
./queries.sh
```

---

## Concepts Demonstrated

- Database normalization  
- Primary & Foreign Keys  
- JOIN operations  
- Aggregate functions (SUM, AVG, MAX, COUNT)  
- UNION  
- Filtering with WHERE and LIKE  
- Bash automation for database interaction

---

## How to Run

1. Create the database: psql -U postgres -f worldcup.sql
  
2. Make sure `games.csv` is in the same directory as the script.

3. Import the data: ./insert_data.sh

4. Run the queries: ./queries.sh
