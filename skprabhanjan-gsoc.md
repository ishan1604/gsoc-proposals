Angular JS Web App Enhancements

Prabhanjan S Koushik

( [skprabhanjan@gmail.com](mailto:skprabhanjan@gmail.com) )

# Project Idea

## Overview

The Project AngularJS Web App Enhancements Deals with a bunch of Additions, Enhancements, Adding new features, improving the UI/UX for the existing Web Application which is a standard application on the Mifos X distribution that provides all the core functionality for the most common methods of financial inclusion and products and services.So the goal is to keep improving it based on user feedback, better the performance, and to integrate new design standards.

## Goals

This project would involve making additional UI enhancements, implementations listed here:

* 1) Redesign the client, group, and center records
* 2) Redesign the loan and summary savings pages
* 3) Implement Wizard UI product and account creation
* 4) Implement UI for workflows & data table entity checks
* 5) Improve the collection sheet UI
* 6) Extend the notifications framework
* 7) Improve interface for role-based dashboards.
* 8) Performance improvements by introducing on demand loading

 In brief the project goal is to make a new design to client, group and center records page. Make loan and savings summary page more user-friendly by revamping it, Implementing wizard UI for creation of account and product, workflows and data table entity checks, improvements in collection sheet UI, Extending notifications frameworks for better use, improvements in role-based dashboards for a better user experience, performance improvements.
 I have gone through how each of these can be dealt in brief in the next section, happy to look into any suggested changes by the mentors.

# Implementation

Looks at the existing UI or features and provides methods for what should be relooked and redesigned for a better application, how things can be implemented if it does not exist.

Detailed Description about each of the goals that needs to be achieved:

 * 1) Redesign the client, group, and center records.
    The page to view the records for clients, group and center currently looks like this [https://demo.openmf.org/#/clients],[https://demo.openmf.org/#/groups],[https://demo.openmf.org/#/centers] .
    The Redesign will take it account the UI/UX improvements that were suggested by feedbacks and making it more user-friendly and intuitive for the user to understand and get through the flow easily, includes few Table layout tweaks, aligning and positions of few things that are not proper(buttons, search and Navigation to next set of records). The new_reskin branch has a few of these fixes but can be made better and I will make sure its completed successfully by tweaking the above mentioned UI/UX fixes.

  * 2) Redesign the loan and summary savings pages.
    An example of loan account Summary page looks like this [https://demo.openmf.org#/viewloanaccount/923] and savings account Summary page looks like this [https://demo.openmf.org/#/viewsavingaccount/690].
    The Redesign will take into account the UI/UX improvements , few of those are the top panel that lets the user "Post Interest As on","Deposit","Withdraw" and etc. This pane is not so user friendly and designed neatly. Few improvements can be giving proper padding and fix the pane to span hundred percent width and make to more nicer to view and easier to use. Make the summary page more readable and understandable and add new functionalities if it suffices to the page design.

  * 3) Implement Wizard UI product and account creation.
    This is to Implement a Wizard UI for product and account creation and has to be dealt with properly as account and product creation is fairly long, but important process and we should not lose users because of complications involved here.
    So designing this needs a stable and simple design that lets the users to be willing to surrender control over what happens when. Will follow standard guidelines for creating a design flow, few links to design standards by Microsoft [https://msdn.microsoft.com/en-us/library/windows/desktop/bb246463(v=vs.85).aspx] and for a better user experience to walk through the wizard, I will follow standard text guidelines by Microsoft [https://msdn.microsoft.com/en-us/library/windows/desktop/bb246451(v=vs.85).aspx].

  * 4) Implement UI for workflows & data table entity checks.
    Implementing a new page for standard workflows and data table entity checks by taking into the account the ease of the workflow and how intuitive the checks for data table entity can it be made. Few insights I will be following in order to create an amazing workflow [http://crmbook.powerobjects.com/system-administration/processes/workflows/] , Implementing UI for data table entity checks would be dealt with a smooth and ease to use UI and improving UX while using this.

  *  5) Improve the collection sheet UI.
    The collection sheet generation flow starts at [https://demo.openmf.org/#/entercollectionsheet] where we need to enter the details,  a cumbersome and not so intuitive UI which can be taken care(Adding few placeholders and details in front of options and buttons) and the collection sheet generated (Productive collection sheet and collection sheet) can be seen at [https://demo.openmf.org/#/productivesheet/1/Head%20Office/01%20April%202017/42], which is rather empty, so we can show this at the first page itself instead of having the user to navigate to the next page and see nothing there. And currently selecting a Center and Group to generate a collection sheet does not seem to populate options, First I will fix that and then improve the UI of the collection sheet itself. There is another separate tab for individual collection sheet [http://localhost:9002/?baseApiUrl=https://demo.openmf.org#/individualcollectionsheet], Will work on improving that as well, making more insights as to the flow and the use of these different things to the user. Make the user clearly understand the need of when to use which collection sheet will be dealt with with proper care.

  * 6) Extend the notifications framework.
    Extending the notifications framework to make it more better and give a new feel and charm to it. A tab reserved for notifications can be seen in the left panel(in new_reskin only) but does not seem to populate any new data, first try to get around what is the data flow and why nothing seems to populate. Then learn more on existing notifications framework used or check the feasibility of using new modules, there is a good module for angularJS called angular-ui-notifications [https://github.com/alexcrack/angular-ui-notification]

  * 7) Improve interface for role-based dashboards.
    Find the role of the user at [https://demo.openmf.org#/profile], a few UI/UX improvements based on the feedbacks to make it more neater. The roles can be viewed at [https://demo.openmf.org#/admin/roles] , improving this page (example, showing a status code/color for enabled and disabled roles, or make it like a switch for admins having control to turn a role on/off(enable/disable) ). Using ui-routing , create templates for each role and a controller associated with that role. For example, redirecting the user to the url that specifies the roles for that user based on the account he is trying to log in through.
    $routeProvider
            .when('/user/role1', {
                templateUrl: 'views/role1.html',
                controller: 'role1Controller'
            })
            .when('/user/role1', {
                templateUrl: 'views/role2.html',
                controller: 'role1Controller'
            });


  * 8) Performance improvements by introducing on demand loading
    Achieving this would be a huge improvement. Using angularJS demand loading features (On-demand loading), a simple way is to use $routeProvider object and to config its routes. Few insights obtained from [https://www.codeproject.com/Articles/813421/AngularJS-On-demand-loading],[https://weblogs.asp.net/dwahlin/dynamically-loading-controllers-and-views-with-angularjs-and-requirejs] which would yield in a Performance benefit.
    A quick example taken from routes.js in new_reskin branch of community-app.
    $routeProvider
            .when('/', {
                templateUrl: 'views/start.html'
            })
            .when('/login', {
                templateUrl: 'views/login.html'
            })
            .when('/home', {
                templateUrl: 'views/home.html'
            })
            .when('/richdashboard', {
                templateUrl: 'views/private/rich_dashboard.html'
            })
            .when('/products', {
                templateUrl: 'views/products/products.html'
            });
    The new_reskin branch follows the tips from here , i.e [https://weblogs.asp.net/dwahlin/dynamically-loading-controllers-and-views-with-angularjs-and-requirejs] and Therefore performance benefits can be improved by tweaking this more finely and making sure to keep this consistent with the current design.


### Code Quality, Guidelines and standards to be followed
  Assuring neat and clean code is a major factor for open-source contributions. I will follow all the coding standards and guidelines that are now followed in the web app for a more easier integration and maintenance.


## Timeline

### After Submission of my proposal [4th Apr - 4th May]

* Fix more issues and bugs in the openmf community-app(Find out more bugs, solve them. Can something be done better.?, I will make sure I implement it on my own).

* Start sketching down new UI and the design decisions and specifications required for the project.

* For implementing few new features , get to know the exact things to be done, the flow and how to go about it in detail.

* Exam preparations may hinder my time a bit but I will make sure I will keep working on something to make it a better coding period, (Think Twice , Code Once).

* Actively interact with the community.

### Community Bonding [ 5 May to 20th May ]

* Exam Time, but will still make my time available for any discussions and clarifications.

* Will try to squeeze out more bugs and issues.

#### [ 20th May - 30th May]

* Exams Done, So will put all my time into actively involving myself and fine tuning my skills for a better experience.

* Fix few more bugs related to my project that might help me understand things better.

* Actively bond with the community and mentors to decide any design or implementation issues.

* Work on the design decisions and specifications,The UI/UX part, The flow of things (For redesigning of few pages).

* Work on the design, flow, things to be done with perfection for implementing new features.(wizard UI and workflow).

* Make myself hundred percent mentally fit, stable and clear for the next few months of rigorous coding period.


### Coding Period

#### Week 1 [31st May - 6th Jun]

* Finalize the redesign layout, pin down the final UI design and start working towards redesigning it completely.

* Redesign the client, group, and center records completion.

* Open for any changes suggested by mentors.


#### Week 2 [7th Jun - 14th Jun]

* Finalize the redesign layout, pin down the final UI design and start working towards redesigning it completely.

* Redesign the loan and summary savings pages completion.

* Open for any changes suggested by mentors.


#### Week 3 [15th Jun - 21st Jun] and Week 4 [22nd Jun - 29th Jun]

* Finalizing the exact steps needed for account creation and product creation in the wizard.

* Fix the exact flow of things for wizard UI, fix the UI layout and Finalize UI/UX.

* Start progressively designing the wizard UI.

* Testing and getting feedback from mentors and applying required changes.


#### Week 5 [30th Jun - 6th Jul]

* Understanding the exact requirements of workflows and data table entity checks.

* Fix the final UI/UX for workflows and data table entity checks.

* Implement the finalized UI with perfection.

* Implement UI for workflows & data table entity checks completed.

* Testing and any changes reported from the mentors.


#### Week 6 [7th Jul - 14th Jul]

* Finalize the exact sequence for generation of collection sheet and to throw some more light for the user by giving details of each category of collection sheet that can be generated.(As you can find many ways in the present website(productive collection sheet, collection sheet, individual collection sheet)).

* Pin down the exact UI/UX requirements and finalizing the changes required for a better collection sheet UI/UX.

* Implementing the changes completely.

* Testing and changes if any suggestions from the mentors.


#### Week 7 [15th Jul - 21st Jul]

* Study the current use of notifications module and try to check the feasibility of using angular-ui-notifications.

* Finalize the things that need a improvement and what should be and can be extended.

* Complete the Extension of the notifications framework.

* Testing and apply any changes suggested from the mentors.


#### Week 8 [22nd Jul - 29th Jul] and Week 9 [30th Jul - 5th Jul]

* Understand thoroughly the exact flow and how the role-based dashboard must work and what are the roles available.

* Start sketching down design decisions and other critical things required to implement role-based dashboard.

* Fix a final UI design for each role and the accessible material for that role.

* If all of these are already done and available, fix on things that need to be improved.

* Implement the role-based dashboard to proper completion.

* Testing and any further changes suggested by the mentors.


#### Week 10 [30th Jul - 5th Aug]

* Understand few bottlenecks that may be improved in order to increase the performance by a notch.

* Implement demand loading using $routeProvider and any other tweaks that can be achieved.

* Performance improvements by introducing on demand loading completed.

* Testing and implementing changes required that were suggested by mentors.


#### Week 11 [6th Aug - 12th Aug] and  Week 12 [13th Aug - 20th Aug]

* Buffer period

* If all the things go to plan, then try fixing more issues and bugs in this buffer period.

* Complete all the unfinished work and make sure everything is perfectly working without even a small glitch.

* Improvise on anything that the mentors were not completely satisfied with.


# Questions

### Why are you the right person for this project?

* Firstly , as you can observe, I have things sorted out for each of the goals that needs to be achieved, Where to find the redesign pages, how to redesign them and how to implement new things and finally how to achieve a performance benefit, So this would be a huge advantage for the development process to go smoothly without any hitch nor delay of knowing what to do, I am clear about my steps forward for achieving what is required here.

* Being very well versed in the tech stack used here, It might be of great advantage for the project to be completed with greater quality and for the development process to be carried out smoothly without any bottlenecks due tech stack used here and time required to be comfortable with using all these technologies efficiently, As I am very good with HTML5,CSS3,AngularJS and have experience of using it for over an Year.

* As I mentioned that I possess the technical skills required to finish this project on time, efficiently and with a great feel to it, Being a quick and effective learner also adds to my profile.

* Working on few bugs and Fixing them in the community-app has helped me know the code structure and would help me a lot in future work for redesigning and implementing new things as it wont take me time to understand the codebase, As I am clearly familiar with it already.

* Eagerness to contribute as a part of GSOC 2017 for Mifos community and the love for open-source contributions.

* You can further dig into my profile and check out my skillsets in my website skprabhanjan.me(resume downloadable there, please refer it for the projects completed, source codes and my skill set).

### If in college, current area of study?

I’m currently studying in PESIT, A 3rd (Pre-Final) Year Student pursuing a degree in Bachelor of Engineering(B.E) in Information Science and Engineering.

### Contact Information and preferred method of contact

Name: Prabhanjan S Koushik

Email: [skprabhanjan@gmail.com](mailto:skprabhanjan@gmail.com) (Preferred)

Skype Id: skprabhanjan

Telephone Number: +91 9886514275

GitterID: skprabhanjan

Time Zone​: Indian Standard Time (IST),+5:30 GMT

### Career Goals

Firstly, Be a very good Full Stack Web Developer, handling both front end user facing website designs taking into account user interactions and experiences (UI/UX), making it flawless and handling proper design of the database and to improve efficiency for the API's written.
Writing and building websites that are useful to many and my biggest goal is to create my own startup to serve a purpose and make the world a better place to live.

### Please share any links to source code you have written or websites you have built?

  My website link - skprabhanjan.me
  You can find all the details of all the projects I have completed and all the source code in my resume, downloadable from the above website.
  PS: Please download the resume and gid into my profile completely and find all the source code on my github profile([https://github.com/skprabhanjan/])

### If you have visited our Gitter chatroom, what nickname did you use?

Yes, I did visit the gitter chatroom and was actively interacting with the community, helping few people with what i knew and also helping myself by getting some doubts cleared. My nickname is @skprabhanjan

### Have you contributed to other open source projects? If so, which?

No, This is my first open source contribution.

### Have you any previous experience with JavaScript / Java / Spring / Hibernate / MySQL?

Yes I have a fair amount of experience using Javascript and MySQL.
Doing Web Development from over an year now, So very familiar with JS, angularJS and nodeJS.
A lot of projects using MEAN stack really makes me a very good and avid user of this TECH STACK.
Find more details on skprabhanjan.me

### What other commitments do you have this summer? (working on this project is a full-time job and must be your primary commitment!)

I don’t have any active commitments this summer. Completing this project is my only primary goal and I will my hundred percent time only towards this.

### Have you deployed and run the platform ([https://github.com/openMF/incubator-fineract](https://github.com/openMF/incubator-fineract)) and reference User Interface ([https://github.com/openMF/community-app)?](https://github.com/openMF/community-app)?)

Yes I have deployed and run the platform, and worked on the community app and fixed a few bugs and got very familiar with the codebase.

### Have you submitted any patches or source code to Mifos X yet? Please provides links to the commit in GitHub or the JIRA ticket (students looking to be seriously considered should make at least one submission)

Yes I have worked on the following issues in the community-app:

1. [https://github.com/openMF/community-app/issues/2016](https://github.com/openMF/community-app/issues/2016)

2. [https://github.com/openMF/community-app/issues/1866](https://github.com/openMF/community-app/issues/1866)

3. [https://github.com/openMF/community-app/issues/1952](https://github.com/openMF/community-app/issues/1952)

4. [https://github.com/openMF/community-app/issues/1767](https://github.com/openMF/community-app/issues/1767)

5. [https://github.com/openMF/community-app/issues/1773](https://github.com/openMF/community-app/issues/1773)

6. [https://github.com/openMF/community-app/issues/1784](https://github.com/openMF/community-app/issues/1784)

The following were merged:

1. [https://github.com/openMF/community-app/issues/1767](https://github.com/openMF/community-app/issues/1767)

2. [https://github.com/openMF/community-app/issues/1773](https://github.com/openMF/community-app/issues/1773)

3. [https://github.com/openMF/community-app/issues/1866](https://github.com/openMF/community-app/issues/1866)

Two Active PR's:

1. [https://github.com/openMF/community-app/issues/2016](https://github.com/openMF/community-app/issues/2016)

1. [https://github.com/openMF/community-app/issues/1952](https://github.com/openMF/community-app/issues/1952)


### Have you previously participated in the Google Summer of Code?

No, This is my first time participation in Google Summer of Code.

### Are you applying to multiple organizations this year?

No, Mifos is the only organization I’m applying to this year.
