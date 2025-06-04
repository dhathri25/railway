# 🚂 Railway Reservation System — README.md

## 📜 Overview

This project establishes a foundational **Relational Database System** for a railway reservation system using MySQL. It covers essential modules like **USER**, **TRAIN**, **STATION**, **TICKET**, **PASSENGER**, and more. The database schema captures various aspects of booking, passenger management, and train operations with a playful yet professional flair.

## 📂 Table Definitions

Below are the key tables defined with **CREATE TABLE** statements:

| Table Name                      | Description                                                                          |
| ------------------------------- | ------------------------------------------------------------------------------------ |
| `USER`                          | Stores user personal details including contact and security info.                    |
| `TRAIN`                         | Contains train details such as arrival/departure times, seat availability, and date. |
| `STATION`                       | Defines station details and their association with trains.                           |
| `TRAIN_STATUS`                  | Tracks seat availability and fare details for each train.                            |
| `TICKET`                        | Manages booking information including user and train references.                     |
| `PASSENGER`                     | Records individual passenger details linked to tickets.                              |
| `STARTS`, `STOPS_AT`, `REACHES` | Models train routes and schedules at stations.                                       |
| `BOOKS`, `CANCEL`               | Tracks user bookings and cancellations.                                              |

### 🔍 Notable Highlights:

* **Foreign Keys** are established to ensure referential integrity between tables.
* Use of **time** and **date** types enhances temporal accuracy.
* Simple but effective **primary key** definitions support fast lookups.

---

## 🗂️ Insertions

Sample data insertions are provided for all key tables to simulate a working system:

* Users with names and contact details.
* Trains with arrival/departure times and seat availability.
* Stations mapped to trains.
* Bookings, passengers, and cancellations to demonstrate system usage.

---

## 📌 Sample Query

A select query to **print the user ID and concatenated name of users who booked tickets on the 'Pinakini Express'** is included:

```sql
SELECT u.user_id, CONCAT(u.first_name, u.last_name) AS name
FROM USER u, TRAIN t, TICKET tc
WHERE u.user_id = tc.user_id
  AND t.train_no = tc.train_no
  AND t.train_name LIKE 'pinakiniexp';
```

(Note: Ensure consistent spelling of train names in your insertions for accurate results.)

---

## 🚀 Future Enhancements

* 🎯 Implement triggers and stored procedures for auto-updates and notifications.
* 📊 Add analytical queries for seat utilization and revenue trends.
* 🔒 Enhance security with password hashing and multi-factor authentication.
* 🧩 Integrate with a front-end or API for real-time booking and passenger updates.

---

## 🔧 Troubleshooting

* **Typo Alerts**: Watch for spelling errors in table names (e.g., `exsists` vs. `exists`).
* **Foreign Key Consistency**: Confirm train and station references align in their respective tables.
* **Date and Time Formatting**: Ensure date (`YYYY-MM-DD`) and time (`HH:MM:SS`) formats align with MySQL requirements.

---

## 💡 Author’s Note

This project embodies a learning-friendly yet production-ready database design, reflecting **engineering ingenuity** and **future-readiness**. Play around with the queries, add new modules, or even invent your own features — think outside the tracks! 🚂✨

---

## 📝 License

This project is open for educational and development use. Attribution is appreciated but not mandatory. Stay curious and keep building! 🔍
