# 🌌 Universe Database Project

This project is part of the freeCodeCamp Relational Database Certification.

## 📌 Project Description

The Universe database models astronomical objects including:

- 🌌 Galaxy
- ⭐ Star
- 🪐 Planet
- 🌙 Moon
- ☄️ Comet

The database is built using PostgreSQL and demonstrates:

- Primary Keys
- Foreign Keys
- Relationships between tables
- Constraints (NOT NULL, UNIQUE)
- Proper data types (INT, NUMERIC, TEXT, BOOLEAN, VARCHAR)

---

## 🗄️ Database Structure

### Tables Included:
- `galaxy`
- `star`
- `planet`
- `moon`
- `comet`

### Relationships:
- Each **star** belongs to a galaxy
- Each **planet** belongs to a star
- Each **moon** belongs to a planet
- Each table has a primary key
- Foreign keys follow naming conventions

---

## 🛠️ Technologies Used

- PostgreSQL
- psql
- GitHub
- freeCodeCamp Codespaces

---

## 📂 How to Restore the Database

Run the following command in PostgreSQL:

```bash
psql -U postgres < universe.sql
```

---

## 🚀 Getting Started

1. **Clone the repository**
   ```bash
   git clone https://github.com/Rajaneeshkumar-code/universe-db-project-rajaneesh
   cd universe-database
   ```

2. **Start PostgreSQL**
   ```bash
   sudo service postgresql start
   ```

3. **Restore the database**
   ```bash
   psql -U postgres < universe.sql
   ```

4. **Connect to the database**
   ```bash
   psql -U postgres -d universe
   ```

---

## 🗃️ Sample Queries

```sql
-- List all galaxies
SELECT * FROM galaxy;

-- Find all planets orbiting a specific star
SELECT planet.name FROM planet
JOIN star ON planet.star_id = star.star_id
WHERE star.name = 'Sun';

-- Count moons per planet
SELECT planet.name, COUNT(moon.moon_id) AS moon_count
FROM planet
LEFT JOIN moon ON moon.planet_id = planet.planet_id
GROUP BY planet.name;
```

---

## ✅ Project Requirements Met

- [x] Minimum 5 tables
- [x] Each table has a primary key
- [x] Use of foreign keys linking related tables
- [x] At least 2 columns per table that are NOT NULL
- [x] Use of `INT`, `NUMERIC`, `TEXT`, `BOOLEAN`, and `VARCHAR` data types
- [x] At least one `UNIQUE` constraint
- [x] Database exported as `universe.sql`

---

## 📜 License

This project is open source and available under the [MIT License](LICENSE).

---

*Built with 💫 as part of the [freeCodeCamp Relational Database Certification](https://www.freecodecamp.org/learn/relational-database/)*
