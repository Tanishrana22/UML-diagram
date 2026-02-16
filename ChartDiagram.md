## Gantt Chart :
A Ghantt chart is bar chart commonly used in project management to visulize and track the schedule of a project . It provide a clear and concise overview of the project's tasks, duration , dependencies and milestones over time.

**Syntax:**
The Gantt chart starts with the gantt keyword.
gantt
    title Project Title
    dateFormat YYYY-MM-DD
    section Section Name
    Task Name : task_id, start_date, duration

---
```mermaid 
gantt 
    title sample Gantt Chart 
    tickInterval 1day

    section One 
        Task 11: a11 , 2026-02-15,3d
        Task 12: a12 , after a11,2d
    section Two
        Task 21: a21, 2026-02-20,2d
        Task 22: 2026-02-22, 2d
```
gantt 
    title sample Gantt Chart 
    section One 
        Task 11: a11 , 2026-02-15,3d
        Task 12: a12 , after a11,2d
    section Two
        Task 21: a21, 2026-02-20,2d
        Task 22: 2026-02-22, 2d

 * It is important to remember that when a date, day, or collection of dates specific to a task are "excluded", 
 the Gantt Chart will accommodate those changes by extending an equal number of days,
  towards the right, not by creating a gap inside the task


* A Gantt chart is useful for tracking the amount of time it would take before a project is finished, but it can also be used to graphically represent "non-working days", with a few tweaks.

---

**EXAMPLE:**

```mermaid
gantt
    title Software Development Project
    dateFormat YYYY-MM-DD

    section Planning
    Requirement Analysis : 2026-02-01, 2026-02-05
    Feasibility Study    : 2026-02-06, 2026-02-08

    section Design
    System Design        : 2026-02-09, 2026-02-12
    Database Design      : 2026-02-13, 2026-02-15

    section Development
    Backend Development  : 2026-02-16, 2026-02-25
    Frontend Development : 2026-02-18, 2026-02-28

    section Testing
    Unit Testing         : 2026-03-01, 2026-03-05
    Integration Testing  : 2026-03-06, 2026-03-10

    section Deployment
    Deployment           : 2026-03-12, 2026-03-13
```

**CODE:**

gantt
    title Software Development Project
    dateFormat YYYY-MM-DD
    section Planning
    Requirement Analysis : 2026-02-01, 2026-02-05
    Feasibility Study    : 2026-02-06, 2026-02-08
    section Design
    System Design        : 2026-02-09, 2026-02-12
    Database Design      : 2026-02-13, 2026-02-15
    section Development
    Backend Development  : 2026-02-16, 2026-02-25
    Frontend Development : 2026-02-18, 2026-02-28
    section Testing
    Unit Testing         : 2026-03-01, 2026-03-05
    Integration Testing  : 2026-03-06, 2026-03-10
    section Deployment
    Deployment           : 2026-03-12, 2026-03-13

---

## COMPONENT:
**Title:**
The title is an optional string to be displayed at the top of the Gantt chart to describe the chart as a whole.

**Excludes:**
The excludes is an optional attribute that accepts specific dates in YYYY-MM-DD format, days of the week ("sunday") or "weekends", but not the word "weekdays". These date will be marked on the graph, and be excluded from the duration calculation of tasks. 

**Weekend:**
When excluding weekends, it is possible to configure the weekends to be either Friday and Saturday or Saturday and Sunday. By default weekends are Saturday and Sunday. To define the weekend start day, there is an optional attribute weekend that can be added in a new line followed by either friday or saturday.

**Section statements:**
You can divide the chart into various sections, for example to separate different parts of a project like development and documentation.

**Milestones:**
You can add milestones to the diagrams. Milestones differ from tasks as they represent a single instant in time and are identified by the keyword milestone. Below is an example on how to use milestones.

**Vertical Markers:**
The vert keyword lets you add vertical lines to your Gantt chart, making it easy to highlight important dates like deadlines, events, or checkpoints. These markers extend across the entire chart and are positioned based on the date you provide.

---

## Adding Milestones & Compact :
```mermaid

---
displayMode: compact
---
gantt
title Sample Gantt Chart
dateFormat YYYY-MM-DD

section One
Task 11 :done,a11,2026-02-15,3d
Task 12 :a12,after a11,3d

section Two
Start Building :milestone,m1,2026-02-19,1d
Task 21 :crit,done,a21,2026-02-19,2d
Task 22 :crit,2026-02-20,2d
End Building :milestone,m2,after a21,1d
Task 24 :active,after a12,4d
```
**CODE:**

---
displayMode: compact
gantt
title Sample Gantt Chart
dateFormat YYYY-MM-DD

section One
Task 11 :done,a11,2026-02-15,3d
Task 12 :a12,after a11,3d

section Two
Start Building :milestone,m1,2026-02-19,1d
Task 21 :crit,done,a21,2026-02-19,2d
Task 22 :crit,2026-02-20,2d
End Building :milestone,m2,after a21,1d
Task 24 :active,after a12,4d

---

##  Pie Chart :

* A pie chart is a circular statistical graphic that is divided into slice to illustrate numerical proportions. It is a popular way to represent data in a visually appealing and easy-to-understand format

**It is used to represent:**

* Percentage distribution
* Data comparison
* Resource allocation
* Project contribution

**Syntax:**
pie
    title Chart Title
    "Label 1" : 30
    "Label 2" : 40
    "Label 3" : 30

---

```mermaid
pie
    title Chart Title
    "Label 1" : 30
    "Label 2" : 40
    "Label 3" : 30
```
**Syntax Structure :**
| Element       | Syntax           | Description      |
| ------------- | ---------------- | ---------------- |
| pie           | pie              | starts pie chart |
| title         | title Chart Name | chart title      |
| "Label"       | "Frontend"       | category name    |
| value         | : 30             | numeric value    |
| mermaid block | ```mermaid       | required block   |
---

**EXAMPLE:**

```mermaid
pie
title Project Distribution
"Frontend" : 35
"Backend" : 30
"Database" : 20
"Testing" : 15
```

**CODE:**

pie
title Project Distribution
"Frontend" : 35
"Backend" : 30
"Database" : 20
"Testing" : 15

---

## Quadrant Chart :
* A quadrant chart is visual representation of data that is divided into four quadrants.
* It is used to plot data points on a two-dimensional grid, with one variable represented on the x-axis and another variable represented on the Y -axis.
* The quadrants are determined by divided the chart into four equal parts based on a set of criteria that is specific to the data being analyzed .
* They are commonly used in **business**, **marketing** and **risk management** , amony other fields.
---

**Quadrant Chart Diagram:**
```mermaid
    quadrantChart
    title Reach and engagement of campaigns
    x-axis Low Reach --> High Reach
    y-axis Low Engagement --> High Engagement
    quadrant-1 We should expand 
    quadrant-2 Need to promote 
    quadrant-3 Re-evaluate 
    quadrant-4 May ne improved 
    
    Campaign A:[0.3,0.6]
    Campaign B:[0.45,0.23]
    Campaign C:[0.57,0.69]
    Campaign D:[0.78,0.34]
    Campaign E:[0.40 , 0.34]
    Campaign F:[0.35,0.78]
```
**CODE:**
 quadrantChart
    title Reach and engagement of campaigns
    x-axis Low Reach --> High Reach
    y-axis Low Engagement --> High Engagement
    quadrant-1 We should expand 
    quadrant-2 Need to promote 
    quadrant-3 Re-evaluate 
    quadrant-4 May ne improved 
    Campaign A:[0.3,0.6]
    Campaign B:[0.45,0.23]
    Campaign C:[0.57,0.69]
    Campaign D:[0.78,0.34]
    Campaign E:[0.40 , 0.34]
    Campaign F:[0.35,0.78]

---

```mermaid 
%%{
    init:{
"theme":"default"
"themeVariables":{
    "quadrant1Fill":"red",
    "quadrant2Fill":"green",
    "quadrant3Fill":"#eeff00
    "quadrant4Fill": "blue"
    "quadrant2TextFill":"white"
                 }
    }
  }%%
quadrantChart
    title Business Process Evaluation 
    x-axis Inefficient --> Efficient 
    y-axis Low Impact --> High Impact 

    quadrant-1 Strategic Focus 
    quadrant-2 Optimization Opportunities
    quadrant-3 Evaluate Effectiveness 
    quadrant-4 Imporvement Needed 
    
    Process A:[0.2 , 0.8]
    Process B:[0.6 , 0.7]
    Process C:[0.8 , 0.4]
    Process D:[0.3 , 0.2]
    Process E:[0.5 , 0.5]
    Process F:[0.7 , 0.9]
```
**CODE:**
quadrantChart
    title Business Process Evaluation 
    x-axis Inefficient --> Efficient 
    y-axis Low Impact --> High Impact 
    quadrant-1 Strategic Focus 
    quadrant-2 Optimization Opportunities
    quadrant-3 Evaluate Effectiveness 
    quadrant-4 Imporvement Needed 
    Process A:[0.2 , 0.8]
    Process B:[0.6 , 0.7]
    Process C:[0.8 , 0.4]
    Process D:[0.3 , 0.2]
    Process E:[0.5 , 0.5]
    Process F:[0.7 , 0.9]
    
---


## Requirement Diagram :
A Requirement diagram provides a visualization for requirements and their connections, to each other and other documented elements.

**A Requirement Diagram is used to show:**

* System requirements
* Functional requirements
* Non-functional requirements
* Relationships between requirements
* Dependencies and hierarchy

 **Requirement Diagram Elements**:
| Element     | Description                      |
| ----------- | -------------------------------- |
| Requirement | A condition or capability needed |
| ID          | Unique identifier                |
| Text        | Description of requirement       |
| Derive      | Derived from another requirement |
| Satisfy     | Implemented by component         |
| Verify      | Tested by test case              |

**Syntax:**

requirementDiagram
requirement Req1 {
    id: 1
    text: The system shall allow user login
    risk: medium
    verifymethod: test
}

---

**Example:**
```mermaid
requirementDiagram
    requirement req1 {
        id: 1
        text: User Text
        verifymethod: Analysis
    }
    element elem1{
        type: simulation
        docref: github.com/all_the_test
    }

    req1 -satisfies->elem1
```

---

## Web App Requirement Diagram:

```mermaid
requirementDiagram
    requirement Web_APP {
        id: 1
        text: Sample Web application
        verifymethod: Inspection
    }

    requirement Responsive {
        id: 1.1
        text: Application should support moblie and desktop screen
        verifymethod: Test
    }

    requirement User_Auth {
        id: 2
        text: Enable user signup and login 
        risk: High
        verifymethod: Analysis
    }

    requirement DB_Access {
        id: 3
        text: Application requires access to a SQL database
        risk: Low
        verifymethod: Inspection
    }
    element Frontend {
        type: SPA
        docRef: specs/frontend.pdf

    }
    element Backend {
        type: NodeJS REST API
        docRef: specs/backend.pdf
    }
    element DB {
        type: PostgreSQL 12
        docRef: admin/db_schema.sql
    }

    Frontend - satisfies ->Responsive 
    Backend - satisfies ->User_Auth
    DB - satisfies ->DB_Access
    Web_APP - contains -> Responsive
    Web_APP - contains -> User_Auth
    Web_APP - contains -> DB_Access

```
**CODE:**

requirementDiagram

    requirement Web_APP {
        id: 1
        text: Sample Web application
        verifymethod: Inspection
    }

    requirement Responsive {
        id: 1.1
        text: Application should support moblie and desktop screen
        verifymethod: Test
    }

    requirement User_Auth {
        id: 2
        text: Enable user signup and login 
        risk: High
        verifymethod: Analysis
    }

    requirement DB_Access {
        id: 3
        text: Application requires access to a SQL database
        risk: Low
        verifymethod: Inspection
    }
    element Frontend {
        type: SPA
        docRef: specs/frontend.pdf

    }
    element Backend {
        type: NodeJS REST API
        docRef: specs/backend.pdf
    }
    element DB {
        type: PostgreSQL 12
        docRef: admin/db_schema.sql
    }

    Frontend - satisfies ->Responsive 
    Backend - satisfies ->User_Auth
    DB - satisfies ->DB_Access
    Web_APP - contains -> Responsive
    Web_APP - contains -> User_Auth
    Web_APP - contains -> DB_Access

---

## GitGraph Diagram:
* A Git graph is a pictorial representation of git commits and git acitons (commands ) on various branches.
* These kind of diagram are particularly helpful to developers and devops teams to share their Git branching strategies. For example , it makes it easier to visualize how git flow works. 
* It improves Git workflow by allowing users to perform Git operations visually instead of using command-line commands.
Purpose of Git Graph

**The main purposes of Git Graph are:**

* Visualize Git commit history
* View branches and merges
* Manage Git repositories easily
* Perform Git operations using GUI
* Improve understanding of project version history

**Features of Git Graph**:

 **Visual Commit History:**

* Git Graph displays commits in a graphical tree structure showing:
* Commit ID
* Author
* Date and time
* Commit message

 **Branch Visualization:**
* Shows all branches including:
* Main branch
* Feature branches
* Remote branches
* Helps understand branch structure clearly.

**Branch Management:**

* You can perform operations like:
* Create branch
* Delete branch
* Checkout branch
* Merge branch

**Commit Information:**

* Shows detailed commit information:
* Commit message
* Files changed
* Author name
* Commit time

 **Merge and Rebase Support**

* Allows users to:
* Merge branches visually
* Rebase branches
* Resolve conflicts easily

**Remote Repository Support**
* Supports remote repositories such as:
* GitHub
* GitLab
* Bitbucket

**You can:**

Push changes
Pull changes
Fetch updates

#  Git Graph Diagram :

```mermaid
gitGraph
   commit id: "Initial Commit"

   branch develop
   checkout develop
   commit id: "Setup project structure"

   branch feature/login
   checkout feature/login
   commit id: "Create login UI"
   commit id: "Add authentication logic"
   commit id: "Fix login bugs"

   checkout develop
   merge feature/login
   commit id: "Integrate login feature"

   branch feature/dashboard
   checkout feature/dashboard
   commit id: "Create dashboard UI"
   commit id: "Add dashboard functionality"

   checkout develop
   merge feature/dashboard
   commit id: "Integrate dashboard feature"

   branch release/v1.0
   checkout release/v1.0
   commit id: "Prepare release v1.0"
   commit id: "Fix minor bugs"

   checkout main
   merge release/v1.0
   commit id: "Release v1.0"

   branch hotfix/security
   checkout hotfix/security
   commit id: "Fix security vulnerability"

   checkout main
   merge hotfix/security
   commit id: "Hotfix applied"

   checkout develop
   merge hotfix/security
   commit id: "Sync hotfix to develop"
```
**CODE:**


gitGraph
   commit id: "Initial Commit"

   branch develop
   checkout develop
   commit id: "Setup project structure"

   branch feature/login
   checkout feature/login
   commit id: "Create login UI"
   commit id: "Add authentication logic"
   commit id: "Fix login bugs"

   checkout develop
   merge feature/login
   commit id: "Integrate login feature"

   branch feature/dashboard
   checkout feature/dashboard
   commit id: "Create dashboard UI"
   commit id: "Add dashboard functionality"

   checkout develop
   merge feature/dashboard
   commit id: "Integrate dashboard feature"

   branch release/v1.0
   checkout release/v1.0
   commit id: "Prepare release v1.0"
   commit id: "Fix minor bugs"

   checkout main
   merge release/v1.0
   commit id: "Release v1.0"

   branch hotfix/security
   checkout hotfix/security
   commit id: "Fix security vulnerability"

   checkout main
   merge hotfix/security
   commit id: "Hotfix applied"

   checkout develop
   merge hotfix/security
   commit id: "Sync hotfix to develop"

---

