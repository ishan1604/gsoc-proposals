GOOGLE SUMMER OF CODE 2017

**Implementing R****ole-based permissions in Mifos Android Client App**

**Abstract**

Android client for Mifos X allows the bank staff to manage the client details and records at any time remotely with both offline and online support. Mifos has already released the documentation having set of APIs needed to finish the app and I propose to implement a role-based permissions feature which will add up a layer of security to the transactions made by field agents for the clients and will help in authorized activation of different services.

**Problem Statement****   **

Financial security and fraud prevention are of utmost importance for any company. The process of creating a loan, client and transaction entry by the field agents is not supervised. Agents have unrestricted access to modify data and sensitive information which is a potential vulnerability. Due to lack of tracking, identification, and verification, there are chances of internal and external frauds which could lead to monetary losses.

**Proposed Solution**** **

The proposed implementation will enable role-based permissions in the application and will help in having a verification by higher authorities for all the critical transactions. This will enable multiple Officers in the organization having different roles, that will be validating documents for clients, loans, saving accounts, groups, centers before approval.

**Benefits**

For the organization, it will introduce an additional level of verification for documents before accessing bank utilities for activating any service for the client.

For the clients, it is ensuring that the loan has been sanctioned after proper verification which ensures a good level of security. This will reduce the chances of fraudulent cases or human error by the field agent.

**Project Goals**** **

These are the goals of the project which would help reduce the risk of fraudulent activities and errors.

* Role-based permissions - At first, role-based permissions need to be implemented for the existing modules and new proposed modules for the client, loan, saving account, group and center.

* Activation, updating, deletion, rejection, reactivation, the closing of a client should be implemented.

* Assigning and unassigning staff to a client need to be implemented.

* Loan Approve, reject, withdraw, rescheduling request, rescheduling approval, and rejection should be implemented.

* Saving account approval, rejection, withdrawal of request and closing of an account will be implemented as new modules.

* Group activation, updating, deletion, closing needs to be implemented.

* Center activation, updating, deletion, closing needs to be implemented.

**Project Timeline** **Official Coding Period**

GSOC officially provides 12 weeks to code and work on the project. In every 2 weeks, I will get mentors feedback on the code quality and design architecture as well as on UI/UX. In all the new and existing modules I will work with service interfaces, data-tables, model & presenter classes to implement role-based permissions wherever it’s needed and end API calls for some specific features. Writing documentation and testing with mock data-table providers will be a necessary activity in each week.

* **Week 1 ( 30th May - 5th June )**

    * Implementation of role-based permissions architecture.

    * Understanding the architecture of client module.

    * Implementation of client activation, client update and delete feature.

* **Week 2 ( 6th June - 12th June )**

    * Implementation of closing, rejecting, reactivating client.

* **Week 3 ( 13th June - 19th June )**

    * Implementation of modules related to assignment and unassignment of staff to/from a client. 

    * Writing documentation for client module.

* **Week 4 ( 20th June - 26th June ) **

    * Time to clear backlogs, implement feedback/changes proposed by mentors.

    * Writing Unit Test cases for client modules.

* **Week 5 ( 27th June - 3rd July )**

    * Understanding the architecture of loan module.

    * Implementing of Approval, withdrawal, and rejection of loan application.

* **Week 6 ( 4th July - 10th July )**

    * Creating new loan reschedule request along with approving loan reschedule and reject loan reschedule components.

    * Writing documentation for loan module.

* **Week 7 ( 11th July - 17th July )**

    * Understanding the architecture for group module.

    * Implementation of activating, deactivating, deleting and closing of the group.

* **Week 8 ( 18th July - 24th July )**

    * Understanding the architecture and working structure of the center module.

    * Implementation of Activation, updating, deletion, and closing of center.

* **Week 9 ( 25th July - 1st August ) - Work on Evaluation 2**

    * Time to clear backlogs, implement feedback/changes proposed by mentors.

    * Writing documentation for group and center modules.

    * Writing unit test cases for the group, center modules.

* **Week 10 (2nd August - 8th August )**

    * Understanding the working architecture for savings module.

    * Implementation of approving, rejecting, withdrawal, and closing of Saving Application. 

* **Week 11 (9th August - ** **15th August )**

    * Writing documentation for saving module.

    * Writing unit test cases for saving module.

    * Testing and debugging of Saving module along with all the other modules.

* **Week 12 ( 15th August - 21st August ) Final Evaluation Week**

    * Time to clear backlogs, implement feedback/changes proposed by mentors.

    * Improvements in documentation and test cases.

    * Testing of the whole app with different role-based permissions and debugging.

**About Me**

* **Why are you the right person for this project:**

Last year, I pursued my summer internship from Elanic, Bangalore and there I learned the Implementation of Model-View-Presenter architecture, I worked on an Application that helped in automation of order status updating and checking order details, I implemented a custom barcode scanner and used RxJava and RxAndroid for implementation of it.

Here is the link for RxJava Implementation - 

[https://github.com/CodeNicely/BunchOfFoolsApp/blob/master/app/src/main/java/app/bunchofools/codenicely/project/spot_upload/presenter/UploadSpotPresenterImpl.java](https://github.com/CodeNicely/BunchOfFoolsApp/blob/master/app/src/main/java/app/bunchofools/codenicely/project/spot_upload/presenter/UploadSpotPresenterImpl.java)

Here is another Project with MVP Architecture and Retrofit Implementation -

[https://github.com/CodeNicely/GroceryApp](https://github.com/CodeNicely/GroceryApp)

* **If in college, the current area of study:**

B.Tech in Computer science and Engineering from NIT Raipur, currently studying in 3rd year.

* **Contact information and preferred method of contact:**

Email: [meghal.nit@gmail.com](mailto:meghal.nit@gmail.com)

Gitter Id: @meghalagrawal

Telephone number: +91 8109109457

Time zone: UTC +05:30

Skype Id: meghal.nit

Preferred method: Email, gitter or telephonic call

* **Career Goals:**

I am seeking to start a company on my own and contribute to the community.I aspire to work with a collaborative team of talented individuals and produce work that can functionally and potentially serve the needs of the clients.Taking a step forward, I recently took an initiative and started a developing club, to guide the students on how to get exposure to real-world projects and experience of working with the team on big projects.Completing that as my near term goal, I will prepare myself to take on expanded roles and responsibilities in the future.

* **Please share any links to source codes you have written or websites you have built:**

I have developed apps for some real world problems that are live on play store. I have made a lot of my projects open source to guide my juniors and classmates about the way I learn and implement.

Github profile link - [https://github.com/meghalagrawal](https://github.com/meghalagrawal)

	Grocery Android App - An app for a grocery based startup from Jaipur.

	Github link - [https://github.com/CodeNicely/GroceryApp](https://github.com/CodeNicely/GroceryApp)

	

	Bunch of fools App - An app for Clean India Movement for a local NGO

	Github link - [https://github.com/CodeNicely/BunchOfFoolsApp](https://github.com/CodeNicely/BunchOfFoolsApp)

1Mile App - An app for a startup focuses for different things within a mile.

	Github link - [https://github.com/CodeNicely/ChatAroundApp](https://github.com/CodeNicely/ChatAroundApp)

	

	Python based Server end using Flask framework -

	1Mile App server end GitHub link - [https://github.com/CodeNicely/LocationServer](https://github.com/CodeNicely/LocationServer)

* **If you have visited our gitter chat room, what nickname did you use?**

	My gitter id is - @meghalagrawal

	Name I used - Meghal Agrawal

* **Have you contributed to other open source projects? If so which?**

I have worked on my own projects ideas by making teams, building those ideas as open source project during development in either Github or Bitbucket.

* **Have you any previous experience with Javascript/Java/Spring/Hibernate/Mysql**

    * Javascript - I have experience with javascript as I have worked on a website where I used JS and ajax to call REST API endpoints.

Unfortunately, I lost all my commit records while using git push --force for one of the live website in which I was a part of the Team - [http://www.mpenavmo.com](http://www.mpenavmo.com)

The repository link is here - [https://github.com/CodeNicely/navmo](https://github.com/CodeNicely/navmo)

    * Java - I learned java with the experience as I am actively involved in developing Android projects.

    * Mysql - I have used Mysql with Django and native PHP while working on server end for Android apps as well as for a Website 

Offercart Server end - [https://github.com/CodeNicely/OfferCartServer](https://github.com/CodeNicely/OfferCartServer)

* **What other commitments do you have this summer? **

For this summers my primary commitment is Google Summer of Code and I will be able to give at least 30 - 40 hours a week for the project. I will work 5 hours on weekdays and 8 hours on weekends.

I have my college starting from 5th July 2017. No other commitments, I just want to work on GSOC project so that I can get exposure to new challenges and best open source project.

* **Have you deployed and run the platform?**

Yes, I have already built the Android client app and self-service app and I have even submitted some PRs and issues after some commits.

	

* **Have you submitted any patches or source code to Mifos X yet? Please provide links to the commit in Github?**

Yes, I have added some pull requests in the Android client app for Mifos X. Here are the links -

	

* [https://github.com/openMF/android-client/pull/647](https://github.com/openMF/android-client/pull/647)

* [https://github.com/openMF/android-client/pull/588](https://github.com/openMF/android-client/pull/588)

* **Have you previously participated in Google Summer of Code?**

	No, this is the first time I am applying for GSOC.

* **Are you applying to multiple organizations this year?**

	No, I am just applying for Mifos X.

