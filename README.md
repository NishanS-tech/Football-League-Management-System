⚽ Football League Management System

A Java-based **Football League Management System** developed to simulate essential football league operations, including team registration, player management, match scheduling, result tracking, league standings, and player performance evaluation.

The application demonstrates the practical implementation of **Object-Oriented Programming (OOP)** concepts, Java Collections Framework, and role-based performance management through a structured league management system.

📌 Project Overview

The Football League Management System is designed to organize and manage a football competition involving multiple teams and players.

It allows teams to be registered, players to be assigned to their respective teams, and matches to be scheduled automatically. The system records match results, calculates league points, tracks individual player performance, updates player ratings, and identifies the Most Valuable Player (MVP).

The application uses Java's object-oriented features to maintain a modular structure and implement different player roles with specialized performance calculations.

 ✨ Key Features

 1. Team Management
- Register teams with unique team IDs.
- Store team names, coach details, and city information.
- Prevent duplicate team registrations.
- Maintain individual player lists for each team.

 2. Player Management
- Support multiple player roles using an abstract Player class.
- Register Strikers and Goalkeepers.
- Assign unique player IDs across the league.
- Maintain individual player statistics and performance ratings.
- Prevent duplicate player registration.

3. Automatic Match Scheduling
- Generate matches between registered teams.
- Automatically assign unique match IDs.
- Generate sequential match dates.
- Prevent repeated match scheduling.
- Display upcoming fixtures.

 4. Match Result Management
- Record home and away team scores.
- Automatically determine match outcomes.
- Prevent negative scores.
- Prevent duplicate result submissions.
- Maintain match scorecards and result summaries.

 5. League Standings
- Automatically calculate points based on match results.
- Award 3 points for a win.
- Award 1 point to each team for a draw.
- Award 0 points for a loss.
- Sort teams by accumulated points.
- Use team names as a secondary sorting criterion.

 6. Player Performance Tracking
- Record individual player performance after a match.
- Update striker goals and goalkeeper saves separately.
- Calculate player ratings based on new performance.
- Validate that players belong to the participating teams.
- Prevent duplicate performance updates for the same player in a match.

 7. MVP Award Selection
- Evaluate players based on accumulated statistics.
- Rank players by performance statistics.
- Use player ratings as a secondary ranking criterion.
- Handle cases where no players are registered.

 8. Match History
- Display completed match results.
- Display upcoming matches separately.
- Maintain match IDs, dates, scorecards, and outcomes.

 🛠️ Technologies Used

| Technology | Purpose |
|---|---|
| Java | Core application development |
| Java Collections Framework | Managing teams, players, and matches |
| ArrayList | Storing teams, players, and match records |
| HashSet | Preventing duplicate player-stat updates |
| HashMap | Managing player performance data |
| Comparator | Sorting league standings and player rankings |
| LocalDate | Generating match dates |
| Exception Handling | Managing invalid operations and data |

 🏗️ Application Architecture

The application follows a modular class-based structure using nested Java classes.

| Class | Responsibility |
|---|---|
| `LeagueAppMain` | Application entry point and execution workflow |
| `Player` | Abstract base class containing common player attributes and performance methods |
| `Striker` | Manages striker-specific goals and rating calculations |
| `Goalkeeper` | Manages goalkeeper-specific saves and rating calculations |
| `Team` | Maintains team information, player lists, and league points |
| `Match` | Handles match results, scorecards, and individual performance updates |
| `LeagueService` | Coordinates team registration, player management, scheduling, standings, and awards |

 🧠 Object-Oriented Programming Concepts Applied

This project demonstrates the practical application of the following Java OOP concepts:

 1. Abstraction
The `Player` class is declared as an abstract class with an abstract `updateRating()` method.

It defines common player properties while requiring subclasses to implement their own performance-based rating calculations.

 2. Inheritance
The `Striker` and `Goalkeeper` classes inherit common attributes and methods from the `Player` class.

This reduces code duplication and establishes a reusable class structure.

 3. Polymorphism
Both player subclasses override the `updateRating()` method to implement role-specific calculations.

- Striker: Rating increases by 0.1 for each additional goal.
- Goalkeeper: Rating increases by 0.05 for each additional save.

 4. Encapsulation
Player, team, and match attributes are protected or private, with controlled access through methods.

 5. Method Overloading
The `Match` class implements two versions of `recordResult()`:

- `recordResult(int homeGoals, int awayGoals)` – Records the match score and updates league points.
- `recordResult(Map<Player, Integer> playerStats)` – Records individual player performance and updates ratings.

 6. Collections Framework
Different collection types are used to manage league information efficiently:

- `ArrayList` for teams, players, and matches.
- `HashMap` for mapping players to performance values.
- `HashSet` for tracking player IDs whose statistics have already been recorded for a match.

 🔄 Application Workflow

1. Register football teams with their coaches and cities.
2. Register players under their respective teams.
3. Assign player roles such as Striker and Goalkeeper.
4. Generate fixtures automatically between registered teams.
5. Record match scores using unique Match IDs.
6. Calculate match outcomes and update team points.
7. Record individual player performance.
8. Update player statistics and ratings according to their roles.
9. Generate the league table based on accumulated points.
10. Identify the Most Valuable Player using performance statistics.
11. Display completed and upcoming matches.

 💻 Sample Application Output

```text
Match result recorded successfully.
Match result recorded successfully.
Match result recorded successfully.

Player statistics updated successfully.
Player statistics updated successfully.
Player statistics updated successfully.

--- Match Results ---

Match 1: Falcons vs Tigers
Result: Falcons wins | Score: 2 - 1

Match 2: Falcons vs Wolves
Result: Draw | Score: 0 - 0

Match 3: Tigers vs Wolves
Result: Tigers wins | Score: 3 - 2


--- League Table ---

Team                 Points
Falcons              4
Tigers               3
Wolves               1


--- Awards ---

MVP: Leo
Player ID: 6
Role: Goalkeeper
Statistics: 17
Rating: 4.25


--- Upcoming Matches ---

No upcoming matches.
```

*Note: Match dates are generated dynamically based on the system date, so the displayed dates will vary.*

 📂 Project Structure

```text
Football-League-Management-System/
│
├── javaprg/
│   └── LeagueAppMain.java
│
├── README.md
│
└── .gitignore
```

 🚀 Getting Started

 Prerequisites

- Java Development Kit (JDK 14 or later)
- IntelliJ IDEA, Eclipse, or Visual Studio Code
- Basic understanding of Java programming

 Installation

**Step 1: Clone the repository**

```bash
git clone https://github.com/YOUR-USERNAME/Football-League-Management-System.git
```

**Step 2: Navigate to the project directory**

```bash
cd Football-League-Management-System
```

**Step 3: Compile the Java program**

```bash
javac -d . javaprg/LeagueAppMain.java
```

**Step 4: Run the application**

```bash
java javaprg.LeagueAppMain
```

The application executes a predefined demonstration workflow that registers teams and players, schedules matches, records results, updates performance statistics, and displays league information.

 🧪 Validation & Testing

The application includes validation mechanisms for important league operations.

| Test Scenario | Expected Behavior |
|---|---|
| Register an existing team | Duplicate registration rejected |
| Register an existing player ID | Duplicate player registration rejected |
| Schedule matches with fewer than two teams | Scheduling prevented |
| Schedule matches multiple times | Duplicate scheduling prevented |
| Record a result using an invalid Match ID | Match not found |
| Submit negative match scores | Rejected |
| Record the same match result twice | Duplicate result prevented |
| Update statistics for an unrelated player | Rejected |
| Record the same player's statistics twice in one match | Duplicate update prevented |
| Display awards without registered players | Handled without errors |

 🔮 Future Enhancements

The system can be extended with additional functionality:

- Develop an interactive menu-driven interface for team and player registration.
- Integrate MySQL using JDBC for persistent data storage.
- Introduce player transfers between teams.
- Add additional player roles such as Defender and Midfielder.
- Track goals, assists, saves, and other performance metrics independently.
- Implement goal difference and goals scored as league-table tie-breakers.
- Introduce tournament formats, knockout stages, and playoffs.
- Add match rescheduling and manual fixture management.
- Develop a graphical user interface using JavaFX or Swing.
- Generate detailed player and team performance reports.

 🎯 Learning Outcomes

Developing this project helped strengthen my understanding of Java Object-Oriented Programming and the practical implementation of abstraction, inheritance, polymorphism, encapsulation, and method overloading.

It also provided hands-on experience in designing class relationships, managing collections, implementing match-processing logic, validating operations, calculating league standings, and developing role-specific player performance calculations.

 👨‍💻 Author

**Nishan S.**

B.E. Electronics and Communication Engineering

---

⭐ If you find this project interesting, consider giving the repository a star!
