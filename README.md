📌 Project Title : Khabar Bondhu (KindMeal)

AI-Powered Food Donation and Redistribution Platform

*Reducing Food Waste, Sharing Hope, Building a Better Future.*




📌Team Informtion :

Official Team Name :	CSE4104-7B-T02

1.	Rajorshi Roy           	11230121103     	Team Leader
2.	Bushrat Jahan Rafa     	11230321259     	Member
3.	Farhana Akter Ela      	11230321257	     Member
4.	Maiesha Anjum          	11230321275	     Member




  

📌 Project Overview :

Khabar Bondhu (“KindMeal”) is a web platform that rescues edible surplus food, brings less known institutions like small madrasas and orphanages into the limelight for donors, and allows donors to donate without any trouble, with all the transparency possible. Food providers (bakeries, shops, and events) put up surplus food on the website, volunteers pick up the food, and institutions acknowledge how much they received. People willing to help but too busy for that can get the whole process of donating managed by the team, after which a report will be provided to them with details and delivery proof. Three AI features support the platform: OCR-based expiry-date detection with safety flags, smart donor-to-institution matching, and a Bangla chatbot.

📌 Problem Statement:

There is excess packaged food close to expiry in many bakeries and stores. Moreover, food in excess remains after parties or weddings. On the other hand, many madrasas and orphanages do not come into the knowledge of donors and get less regular donations. Donors, willing to donate, don’t have the time to find a reliable institution, coordinate food provision and make sure that it has been done. No existing platform for donating food, whether international or local, provides food donation, lesser-known yet reliable institutions, donation by the donor with full transparency and Bangla language AI facility. (Invisibility of lesser-known institutions is an initial observation by us, which we will verify through a field study during the pilot stage.)

📌 Project Objectives:

•	Build a web platform that connects food donors, verified institutions, and donors who want to give but cannot manage the process themselves.
•	Reduce avoidable food waste by rescuing safe packaged food and event surplus and delivering it to institutions in need.
•	Make lesser-known institutions visible through verified profiles and a Need Map.
•	Provide OCR-based expiry-date detection with safety flags that go to a human for review.
•	Match donations and donor budgets to suitable institutions using an AI-assisted matching feature.
•	Provide a Bangla AI chatbot so non-technical users can use the platform in their own language.
•	Provide transparency through records of collection, delivery and spending, with status updates to donors.
•	Deliver a complete, deployed system with frontend, backend, database, authentication, AI integration, testing and documentation within the semester.


📌  Key Features :

1. Food Rescue

- Publish available surplus food.
- View food availability and details.
- Manage food collection and pickup schedules.

2. Institution Connect

- Connect food donors with charitable institutions.
- Manage institution profiles.
- Support institution verification.
- Share institutional food requirements.

3. Managed Giving

- Support structured donation management.
- Maintain donation and expense records.
- Improve transparency through donation reports.

4. Need Map

- Display relevant institutional food requirements.
- Support location-based donor discovery.
- Help donors identify nearby donation opportunities.

5. AI-Powered Features

OCR-Based Expiry Date Detection

- Extract expiry-date information from food labels using OCR.

Smart Donor-to-Institution Matching

- Recommend suitable donor-institution connections based on relevant requirements and availability.

Bangla AI Chatbot

- Provide AI-powered assistance in Bangla.
- Help users understand platform features and donation procedures.



📌 Technology Stack :

Category| Technology
Frontend| React.js
Main Backend| Node.js, Express.js
Database| PostgreSQL
AI Backend| Python, FastAPI
AI Integration| Gemini / OpenAI (Final selection pending)
OCR| OCR technology (Library/API selection pending)
Map Services| OpenStreetMap
Version Control| Git, GitHub
Development Environment| Visual Studio Code

Note: The technology stack is based on the initial project proposal. Final selections and implementation details will be updated during development.


📌 Scope of the Project:

In scope: A responsive web application (React.js frontend, Node.js and Express.js backend, PostgreSQL database, Python FastAPI AI service) with five user roles and these modules: Food Rescue, Institution Connect, Managed Giving, Need Map, and an Admin dashboard. The three core AI features (OCR expiry-date detection, donor-to-institution matching, Bangla chatbot), notifications, activity logs, online deployment, testing and documentation are also in scope. 
Out of scope:
•	An online payment gateway. Donors pay outside the platform, and the Admin records the payment reference.
•	A native mobile app. The system is a responsive website that works on phones.
•	Route optimisation, need analysis from institution requests, fraud and anomaly detection, demand prediction, and AI impact analysis. These are future work.
•	Legal registration of an organisation and any official food-safety certification. The AI only flags items, and a person makes the final safety decision.
•	Onboarding real partner shops and institutions beyond what is needed for a demonstration with sample data.



📌 User Roles:

The system has five user roles. The four roles other than the Admin are called Platform Members in the use case diagram because they share the same account, chatbot and problem-reporting features.

(i) Admin:
A team member who runs the platform.

Responsibilities:
•	Manage user accounts
•	Verify institutions and set verification levels
•	Review food items flagged by the AI
•	Accept donation requests, record payments and expenses
•	Resolve complaints
•	Monitor the dashboard and generate reports

(ii) Donor:
An individual or company that wants to give food or money.

Responsibilities:
•	Browse institutions and the Need Map
•	Receive institution suggestions based on budget and preferences
•	Request and track managed donations and view reports
•	Use the Bangla chatbot and report problems

(iii) Food Partner:
A bakery, shop or event organiser with surplus food.

Responsibilities:
•	Register business details
•	Create, edit and cancel food listings
•	Follow the status of their listings
•	Use the chatbot and report problems

(iv) Institution Representative:
A person who represents a madrasa, orphanage or similar institution.

Responsibilities:
•	Create and update the institution profile and its needs
•	Confirm receipt of delivered food
•	Use the chatbot and report problems

(v) Volunteer:
A person who collects and delivers food.

Responsibilities:
• View available listings and accept pickup tasks
• Check packages with the OCR feature
• Update pickup status and upload delivery proof
• Browse institutions, use the chatbot and report problems

*** AI Service (system component): The AI service is not a user. It performs OCR, matching and
chatbot tasks for the platform, and its results are always reviewed by a person where safety is
involved


📌 Repository Structure:

Khabar-Bondhu/
|

├── CSE4104-7B-T02_Week01.zip

      └── CSE4104-7B-T02_Week01.pdf(Team Details & Initial Idea)
│

├── CSE4104-7B-T02_Week02.zip

     ├── Project-Proposal.pdf

     ├── Project-plan.pdf

     └── Team-info.pdf
   
│
├── CSE4104-7B-T02_Week03.zip

      ├── SRS.pdf
      ├── UseCaseDiagram.pdf
      ├── ERDiagram.pdf
      └── ArchitectureDiagram.pdf
│

└── README.md
