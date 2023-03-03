The project repo we will be updating can be found at: https://github.com/Ludolab/PeerPresents

Our clients instructed to specifically focus on development environment setup during this sprint as there were [unknown] difficulties for previous developers. They further requested that we maintain documentation about changes or deviations to the guides included in the repo's existing documentation. Each member of TEAM___? had access to a different combination of hardware and operating system, and by the end of this sprint we were successful with an x86_64/Linux installation and setup which was demonstrated in class; over spring break, the other two members will explore this option in order to facilitate progress on testing and development in sprint 3.

Included in the Sprint 2 directory are the following files:
    • Updated Team Contract to reflect pronounciation of TEAM___? name (Team Fill-in-the-Blank)
        ◦ Team Contract (Updated).docx
    • Daily check-ins primarily occurred in Discord - please refer to Timesheet.xlsx for details
    • In-person meetings were held on Tuesdays and Thursdays; notes from each meeting follow the format:
        ◦ Month_Day_Year Team Meeting Notes.docx
    • Client meetings were held over Discord, and notes are named following the format:
        ◦ Month_Day_Year Client Meeting Notes.docx
    • A draft of documentation for changes with respect to the repo's existing setup guides for successful development environment setup is included. The client has not yet requested this document, and as such it is a work in progress. We will improve readability in upcoming sprints as other members of the team are able to provide feedback based on their own experience.
        ◦ Local Development Environment Setup Notes (WIP).docx
    • Timesheet - please see Sprint 2 tabs
        ◦ TEAM____ Capstone Timesheet.xlsx
    • Sprint 2 Reflection meeting notes:
        ◦ Sprint 2 Reflections Notes.docx
    • Powerpoint presentation used to supplement demonstration of working development environment:
        ◦ Sprint 2 Demo Day Presentation.pptx
    • The model diagram hasn't changed:
        ◦ PeerPresents Model Diagram.pdf
    • The wireframes have not changed either, but pending confirmation during our next client meeting. The wireframes related to graphical data visualization are most relevant including HOME-Studies, Create Study Page, Study 9:
        ◦ PeerPresents User Flow.zip

During Sprint 2:

These were our goals at the start of the sprint
        ◦ Client expected difficulty in development environment setup and tasked us with solely focusing on setup and troubleshooting during this sprint
            ▪ Existing documentation, but outdated
            ▪ Age of project and development over years led to dependency mismatches among packages included in the app
                • Removed some (ex: navigation-test-utils)
                • Modified versions (ex: downgraded react, others)
                • Some were deprecated, and had to be installed using legacy dependencies (npm install with --legacy-peer-deps flag)
    • This is how we divided goals among team members
        ◦ Some difficulties were common while others were unique, which forced us to work more independently as we overcame the common issues
            ▪ Hardware/OS different for each team member
            ▪ Common:
                • Dependency versioning
                • Certain elements of MongoDB usage (ex: outdated instructions in guide -> shell alias is mongosh instead of mongo)
            ▪ Unique:
                • Homebrew issues on M1 Mac - troubleshooting pathing issue broke critical system commands
                • Homebrew issues on Intel-based Mac - running mongo service
    • This is how far we got (including a demo of live code)
        ◦ One member completed setup due to a fortunate OS/CPU architecture combination.
            ▪ Can demo app, but because we haven't begun development there's nothing to show beyond what already existed; still issues with live database.
    • This is where we struggled, and what we are going to change so things go better next sprint
        ◦ Backend (Master) - we either misunderstood or miscommunicated, and lost the better part of a week troubleshooting an issue later clarified during our subsequent client meeting
            ▪ Can do better next sprint: observe a time limits to tasks we cannot resolve within the team and make use of communication channel with our client to with comments and questions
        ◦ Particularly issues unique to each member:
            ▪ Develop on OS (->VM) whose setup process is known to be successful?
            ▪ Our individual paths merge again (as we overcome the unique issues), so our ability to collaborate improves
        ◦ Our workflow will necessarily change during the next sprint as setup becomes testing and development, so the issues we struggled with should not be the same as any future issues
        ◦ Still waiting for instructor codes from the client so we can develop with full/administrative permissions (expected today)
    • These are our goals for the next sprint
        ◦ Complete our setup before the next client meeting (Tuesday after spring break)
        ◦ Begin development and testing
