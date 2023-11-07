
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
Entity Name - Coach
Column name - coachID
Description - unique identification number for each coach (PRIMARY KEY)
Data type and length - INT
Column name - coachFname
Description - first name of each ecoach
Data type and length - VARCHAR(45)
Column name - coachLname 
Description - last name of each coach
Data type and length - VARCHAR(45)
Column name - title
Description - title of each coach
Data type and length - VARCHAR(45)
Column name - salary
Description - salary of each coach
Data type and length - VARCHAR(45)
Column name - dob
Description - date of birth of each coach
Data type and length - DATE
Column name - Teams_teamID
Description - the teamID for the team they are the coach for (FOREIGN KEY)
Data type and length - INT

Entity Name - Injury
Column name - InjuryID
Description - unique identification number for each injury (PRIMARY KEY)
Data type and length - VARCHAR(45)
Column name - injuryType
Description - describes the area of the body where the injury occurred 
Data type and length - VARCHAR(45)
Column name - Matches_matchID
Description - the matchID for the the match when the injury occurred (FOREIGN KEY)
Data type and length - INT
Column name - Player_playerID
Description - the playerID for the player who got injured (FOREIGN KEY)
Data type and length - INT

Entity Name - Kits
Column name - kitsID
Description - the unique ID of the kit (PRIMARY KEY)
Data type and length - INT
Column name - kitName
Description - the name of the kit
Data type and length - VARCHAR(45)
Column name - kitType 
Description - the style of jersey each kit is 
Data type and length - VARCHAR(45)
Column name - Teams_teamID
Description - the ID of the team that wears the kit (FOREIGN KEY)
Data type and length - INT

Entity Name - Matches
Column name - matchID
Description - the unique identification number for each match (PRIMARY KEY)
Data type and length - INT
Column name - opponent 
Description - lists the name of the opponent our club’s team faced that match
Data type and length - VARCHAR(45)
Column name - date
Description - lists the date that the match was played
Data type and length - DATE
Column name - result
Description - lists the result of the match from our club’s perspective (win, loss, or draw)
Data type and length - VARCHAR(45)
Column name - Teams_teamID
Description - the teamID for the team of our club that played in the match (FOREIGN KEY)
Data type and length - INT
Column name - Stadium_stadiumID
Description - the stadiumID for the stadium where the match was played (FOREIGN KEY)
Data type and length - INT

Entity Name - Players
Column name - playerID
Description - the unique ID of the player (PRIMARY KEY)
Data type and length - INT
Column name - firstName
Description - the first name of each player 
Data type and length - VARCHAR(45)
Column name - lastName
Description - the last name of each player 
Data type and length - VARCHAR(45)
Column name - dateOfBirth
Description - the date of birth for each player 
Data type and length - DATE
Column name - position
Description - the position played by each player 
Data type and length - VARCHAR(45)
Column name - nationality
Description - the country of origin for each player 
Data type and length - VARCHAR(45)
Column name - salary
Description - how much each player is paid
Data type and length - VARCHAR(45)
Column name - Teams_teamID
Description - the teamID of the team that the player plays for (FOREIGN KEY)
Data type and length - INT

Entity Name - Revenues
Column name - revenueID
Description - the unique ID of the specific revenue stream (PRIMARY KEY)
Data type and length - INT
Column name - revenueType
Description - the type of revenue for each specific revenue stream
Data type and length - VARCHAR(45)
Column name - revenueAmount
Description - the dollar value brought in by the specific revenue stream 
Data type and length - INT
Column name - Teams_teamID
Description - the teamID of the team that is responsible for generate each specific revenue stream (FOREIGN KEY)
Data type and length - INT

Entity Name - Sponsor
Column name - sponsorID
Description - the unique ID of the sponsor (PRIMARY KEY)
Data type and length - INT
Column name - sponsorName
Description - the name of the sponsor
Data type and length - VARCHAR(45)
Column name - amountReceived
Description - the amount of money received from each sponsor
Data type and length - VARCHAR(45)
Column name - contractLength
Description - the length of each sponsorship contract
Data type and length - VARCHAR(45)



Entity Name - Stadium 
Column name - stadiumID
Description - unique identification number for each stadium (PRIMARY KEY)
Data type and length - INT
Column name - city 
Description - the city where each stadium is located
Data type and length - VARCHAR(45)
Column name - state 
Description - the state where each stadium is located
Data type and length - VARCHAR(45)
Column name - capacity
Description - how many seats for spectators there are in each stadium
Data type and length - VARCHAR(45)
Column name - stadiumName
Description - the name of each stadium
Data type and length - VARCHAR(45)
Column name - yearBuilt
Description - the year each stadium was built 
Data type and length - VARCHAR(45)

Entity Name - Team_Staff
Column name - staffID
Description - unique identification number for each staff member (PRIMARY KEY)
Data type and length - INT
Column name - title
Description - title of each staff member
Data type and length - VARCHAR(45)
Column name - staffFname
Description - first name of each staff member
Data type and length - VARCHAR(45)
Column name - staffLname 
Description - last name of each staff member
Data type and length - VARCHAR(45)
Column name - salary
Description - salary of each staff member
Data type and length - VARCHAR(45)
Column name - dob
Description - date of birth of each staff member
Data type and length - DATE
Column name - Teams_teamID
Description - the teamID for the team they are a staff member for (FOREIGN KEY)
Data type and length - INT
Entity Name - Teams
Column name - teamID
Description - the unique identification number for each team in our club (PRIMARY KEY)
Data type and length - INT
Column name - teamName
Description - the name of each team in our club (all teams go by our club name of FC Salge)
Data type and length - VARCHAR(45)
Column name - teamLevel
Description - gives the level each team plays at 
Data type and length - VARCHAR(45)
Column name - Stadium_stadiumID
Description - lists the home stadium for each team (FOREIGN KEY) 
Data type and length - INT

Entity Name - Teams_has_Sponsor (ASSOCIATIVE ENTITY)
Column name - Teams_teamID
Description - the unique ID of the team being sponsored (FOREIGN KEY)
Data type and length - INT
Column name - Sponsor_sponsorID
Description - the unique ID of the sponsor (FOREIGN KEY)
Data type and length - INT
Column name - teamsponsorID
Description - the unique ID of the pairing of the team and sponsor (PRIMARY KEY)
Data type and length - VARCHAR(45)

## Ten Queries
1. Find the salary distribution by position for each team where the total salary for the position group is greater than $500,000
Select teamLevel, position, SUM(salary) as totalSalary
From Players, Team
Where Players.Teams_teamID = Teams.teamID
Group By teamLevel, position
Having SUM(salary) > 500000;

2. Select all the kits for team 1
Select kitName FROM Kits
Where Teams_teamID = 1;

3. Find the names of players who suffered knee injuries:
Select firstName, lastName
From Players, Injury
Where Players.PlayerID = Injury.Player_playerID
And injuryType IN (“Knee”);

4. Find the names and teamIDs of team staff members that have a job title of Marketing and have last names that end in ‘n’:
Select staffFname, staffLname, teamID
From Team_Staff, Teams
Where Teams.teamID = Team_Staff.Teams_teamID 
And title IN ("Marketing")
And staffLname regexp "n$";

5. Find the names and salaries of defense coaches whose salaries are greater than the average salaries of the team staff members
Select coachFname, coachLname, salary
From Coach
Where title regexp ‘Defense Coach’
And salary > 
	(Select AVG(salary) from Team_Staff);’
 
6. Find the name and location of the stadium, as well as the date of the match, where a player suffered either an ankle or foot injury. Specify which type of injury was suffered.
Select stadiumName, CONCAT(city, ", ", state) as location, matchDate, injuryType
From Stadium, Matches, Injury
Where Stadium.stadiumID = Matches.Stadium_stadiumID
And Matches.matchID = Injury.Matches_matchID
And injuryType regexp "Ankle|Foot";

7. Lists all the players in the club that are from Brazil, this is for a simple 
Select firstName, lastName, playerID, teamID
From Players, Teams
Where Players.Teams_teamID = Teams.teamID
And nationality REGEXP ("Brazil");

8. Upper management wants to know which position has the highest average salary
Select Position, avg(salary) as Average_Salary
From Players
Group by Position;

9. Find the result of the games that england players have head injuries that are playing forward 
Select result, injuryType, nationality, position 
from Players, Injury, Matches 
Where Injury.Matches_matchID = Matches.matchID 
And Players.playerID = Injury.Player_playerID
And nationality IN  ("Italy")
And injuryType IN ("head")
And position IN ("Goalkeeper"); 

10. Find the number of players grouped by nationality who salaries are above the average salaries of players
		Select nationality, COUNT(*) as Number_Of_Players from Players 
Group by nationality;
