
# Group Project 1

Dylan Vila, Jonathan Gilbertson, Robert Delorme, Ryan Burstiner, Brett Serwin


## Problem Description
As the owner and operator of a soccer club, my business is centered around the management and operation of a professional soccer team. Our club competes in a prominent soccer league and participates in various competitions at the national and international levels. We aim to be a successful and well-recognized soccer club, both on and off the field. Here is an overview of our organization:
Club Information:
Club Name: [Your Club Name]
Year Founded: [Year of Establishment]
Home Stadium: [Stadium Name]
Location: [City, State]
Logo and Colors: [Description of Club Logo and Colors]
Club Vision and Mission: [Brief overview of the club's goals and values]
Teams and Players:
We have multiple teams, including senior, reserve, and youth teams.
Each team has a roster of players with details such as name, age, nationality, position, and jersey number.
Players can move between teams, and transfers or loan deals may occur.
Matches and Competitions:
We participate in various leagues, tournaments, and friendly matches.
Each match has details like date, time, opponent, venue, and match results.
We need to keep records of past and upcoming fixtures.
Coaching Staff:
Our coaching staff includes head coaches, assistant coaches, and other support staff.
Coaches have their profiles, including name, qualifications, and coaching history.
Club Staff and Management:
Non-playing staff, such as administrators, medical personnel, and management, are vital to our operation.
We need to keep track of their roles and contact information.
Sponsors and Partnerships:
We have partnerships and sponsorships with various companies and organizations.
Details about these partnerships, contracts, and sponsorship agreements are important.
Finances:
Managing the club's finances is crucial. This includes revenue from ticket sales, merchandise, and sponsorships, as well as expenses related to player contracts, staff salaries, and operational costs.
Youth Development:
Our club is committed to nurturing young talent through youth academies.
We need to track the progress of young players, coaching staff, and development programs.
Fan Base:
Engaging with our fans and supporters is essential. We need to keep track of season ticket holders, fan clubs, and fan engagement initiatives.
Injuries and Medical Records:
Monitoring and managing player injuries and medical histories is crucial for player well-being and performance.
Scouting and Recruitment:
We scout new talent and negotiate player transfers and contracts.
We need a system to keep track of potential recruits, their evaluations, and negotiations.
The database project will be crucial for us to manage these aspects effectively. The MIST 4610 class from the University of Georgia will play a critical role in designing a relational database that can efficiently store and retrieve information related to our club's various entities, attributes, and relationships. We need a database that ensures data accuracy, security, and accessibility for different club stakeholders, including management, coaches, players, and fans.

## Data Model
<img width="338" alt="Screenshot 2023-11-06 223444" src="https://github.com/Jonathan-Gilbertson/Group-Project-Jonathan/assets/118770927/9ef40660-1278-4272-a7ec-009e6a27af90">

## Data Dictionary 

| Entity Name        | Column Name        | Description                                         | Data Type and Length  |
|--------------------|--------------------|-----------------------------------------------------|-----------------------|
| Coach              | coachID            | Unique identification number for each coach (PRIMARY KEY)   | INT                 |
| Coach              | coachFname         | First name of each coach                            | VARCHAR(45)          |
| Coach              | coachLname         | Last name of each coach                             | VARCHAR(45)          |
| Coach              | title              | Title of each coach                                 | VARCHAR(45)          |
| Coach              | salary             | Salary of each coach                                | VARCHAR(45)          |
| Coach              | dob                | Date of birth for each coach                        | DATE                |
| Coach              | Teams_teamID      | The teamID for the team they are the coach for (FOREIGN KEY)  | INT                 |
| Costs              | costID             | Unique ID for each specific cost (PRIMARY KEY)     | INT                 |
| Costs              | Teams_teamID      | The teamID for the team that is the source of each cost (FOREIGN KEY)  | INT                 |
| Costs              | costType           | The type of each cost                               | VARCHAR(45)          |
| Injury             | InjuryID           | Unique identification number for each injury (PRIMARY KEY)   | INT                 |
| Injury             | injuryType         | Describes the area of the body where the injury occurred | VARCHAR(45)          |
| Injury             | Matches_matchID    | The matchID for the match when the injury occurred (FOREIGN KEY) | INT                 |
| Injury             | Player_playerID    | The playerID for the player who got injured (FOREIGN KEY) | INT                 |
| Kits               | kitsID             | The unique ID of the kit (PRIMARY KEY)              | INT                 |
| Kits               | kitName            | The name of the kit                                 | VARCHAR(45)          |
| Kits               | kitType            | The style of jersey each kit is                    | VARCHAR(45)          |
| Kits               | Teams_teamID      | The ID of the team that wears the kit (FOREIGN KEY) | INT                 |
| Matches            | matchID            | Unique identification number for each match (PRIMARY KEY) | INT                 |
| Matches            | opponent           | Lists the name of the opponent our club's team faced that match | VARCHAR(45)          |
| Matches            | date               | Lists the date that the match was played            | DATE                |
| Matches            | result             | Lists the result of the match from our club's perspective (win, loss, or draw) | VARCHAR(45)          |
| Matches            | Teams_teamID      | The teamID for the team of our club that played in the match (FOREIGN KEY) | INT                 |
| Matches            | Stadium_stadiumID | The stadiumID for the stadium where the match was played (FOREIGN KEY) | INT                 |
| Players            | playerID           | The unique ID of the player (PRIMARY KEY)           | INT                 |
| Players            | firstName          | The first name of each player                       | VARCHAR(45)          |
| Players            | lastName           | The last name of each player                        | VARCHAR(45)          |
| Players            | dateOfBirth        | The date of birth of each player                    | VARCHAR(45)          |
| Players            | position           | The position played by each player                  | VARCHAR(45)          |
| Players            | nationality        | Country of origin for each player                   | VARCHAR(45)          |
| Players            | salary             | How much each player is paid                        | VARCHAR(45)          |
| Players            | Teams_teamID      | TeamID of the team that the player plays for (FOREIGN KEY) | INT                 |
| Players            | Players_playerID  | The playerID of the player that is the mentor for the player whose playerID is the primary key of the row (ONE TO MANY RECURSIVE) | INT |
| Revenues           | revenueID          | The unique ID of the specific revenue stream (PRIMARY KEY) | INT                 |
| Revenues           | revenueType        | Type of revenue for each specific revenue stream    | VARCHAR(45)          |
| Revenues           | revenueAmount      | The dollar value brought in by the specific revenue stream | INT               |
| Revenues           | Teams_teamID      | The teamID of the team that is responsible for generating each specific revenue stream (FOREIGN KEY) | INT |
| Sponsor            | sponsorID          | The unique ID of the sponsor (PRIMARY KEY)           | INT                 |
| Sponsor            | sponsorName        | Name of sponsor                                     | VARCHAR(45)          |
| Stadium            | stadiumID          | The unique identification number for each stadium (PRIMARY KEY) | INT           |
| Stadium            | city               | The city where each stadium is located              | VARCHAR(45)          |
| Stadium            | state              | State where the stadium is located                  | VARCHAR(45)          |
| Stadium            | capacity           | Stadium capacity                                   | VARCHAR(45)          |
| Stadium            | stadiumName        | Name of the stadium                                 | VARCHAR(45)          |
| Stadium            | yearBuilt          | Year the stadium was built                         | VARCHAR(45)          |
| Team_Staff         | staffID            | The unique identification number for each staff member (PRIMARY KEY) | INT              |
| Team_Staff         | title              | Title of each staff member                          | VARCHAR(45)          |
| Team_Staff         | staffFname         | First name of each staff member                     | VARCHAR(45)          |
| Team_Staff         | staffLname         | Last name of each staff member                      | VARCHAR(45)          |
| Team_Staff         | salary             | Salary of each staff member                         | VARCHAR(45)          |
| Team_Staff         | dob                | Date of birth of each staff member                  | DATE                |
| Team_Staff         | Teams_teamID      | The teamID for the team they are a staff member for (FOREIGN KEY) | INT                |
| Teams              | teamID             | The unique identification number for each team in our club (PRIMARY KEY) | INT          |
| Teams              | teamName           | The name of each team in our club (all teams go by our club name of FC Salge) | VARCHAR(45) |
| Teams              | teamLevel          | Gives the level each team plays at                   | VARCHAR(45)          |
| Teams              | Stadium_stadiumID | Lists the home stadium for each team (FOREIGN KEY)   | INT                 |
| Teams_has_Sponsor  | teamsponsorID      | The unique ID of the pairing of the team and sponsor (PRIMARY KEY) | INT          |
| Teams_has_Sponsor  | Teams_teamID      | The unique ID of the team being sponsored (FOREIGN KEY) | INT             |
| Teams_has_Sponsor  | Sponsor_sponsorID  | The unique ID of the sponsor (FOREIGN KEY)           | INT                 |
