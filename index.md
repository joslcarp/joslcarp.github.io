---
layout: default
---

### Senior Seminar Project

### Presented on at the Association for Computing Machinery 2016 Fall Conference in Gatlinburg

### Abstract-

Speed and efficiency are essential to customer service; today, that means having quality software with a clean underlying database. After serving the university for almost a decade, the UTM Computer Store’s inventory system fails to meet these expectations. The system experiences numerous issues including erroneous user input and faulty permission checking. Many of the store’s systems, including its inventory, are based in FileMaker Pro, a database management system with its own built-in applications and scripting functionality. We will work with the current FileMaker Pro applications to add new features while preserving the store’s current infrastructure.  By automating processes including barcode entry as well as providing previously unwritten documentation to users, we intend to include features that will provide partial cleanup to the store’s disorganized database without burdening the user.  

### Keywords- inventory, system, database, UTM Computer Store, FileMaker

### I. INTRODUCTION

The UTM Computer Store has been utilizing a system that has existed for more than two decades.  Over time, some issues with the store's system have become apparent, causing several different problems that have resulted in inefficiency.  We have attempted to implement solutions to these problems within the current system that uses FileMaker Pro.  As a result, we hope to improve the computer store's ability to do business without having to consistently deal with issues within the software they use every day.

### II. BACKGROUND

The idea for this project was born out of a critical need for a local store.  The UTM Computer Store began as a small branch of the ITS department that grew over the years to become an independent store.  As a result, their database is reliant on the ITS's own database system, sharing data with other school systems.  The system that has been used since is the 90's was created with an application called FileMaker Pro.  As the database has expanded over the years, the amount of issues has increased as well.  The UTM Computer Store utilizes a universal product code (UPC) to uniquely identify products in inventory.  However, the employees of the store do not always have access to this code when a product is ordered, and it is not always updated correctly at a later time.  This is emphasized by the high rate of turnover within the staff, which results in some users being unfamiliar with the system at times.  As a result this causes some of the store's inventory to contain erroneous data that have produced some negative consequences for the business.  When a UPC is not correct, it can cause issues for employees to find the correct item within the system.  Additionally, sometimes employees end up creating a new record for the item in the system.  If this occurs, any future sales will only modify one of the existing records, which can result in negative quantity values appearing.  The computer store also performs periodic inventory audits.  The erroneous data in the system can cause these audits to be inefficient and time consuming.  Additionally, the computer store has accumulated over 15000 records over the years.  They wanted us to build a tool that could export records that are not currently used to a backup file, leaving the main file with a smaller record base.
We immediately began by using a school licensed copy of FileMaker Pro to begin learning the environment in which we would be working on the project in.  Since neither of us had utilized the FileMaker Pro application before, it took us a couple weeks to familiarize ourselves with the software.  After some time, we were able to get a handle on the ins and outs of the FileMaker platform, and we were ready to begin work on the project.  However, we encountered a couple hindrances at this point that resulted in delays on the start of the project.  We worked with a member of the faculty in order to set up a meeting with all the stakeholders involved in the project; however, this ended up taking an additional couple weeks for everyone involved to be able to meet.  Furthermore, we needed an offline clone of the current system to work on for this project.  This took another couple weeks to obtain.  Once we were able to overcome these issues, we began work on our solutions for the computer store's system.

### III. DEVELOPMENT TOOLS

A. Software (FileMaker Pro)

FileMaker Pro is a relational database platform that utilizes a GUI to develop applications for businesses and organizations.  The applications built in FileMaker run within the FileMaker program.  FileMaker applications are cross-platform, working across the major three operating systems (Linux, Mac, and Windows) and between various devices (mobile, PC, tablet).  The FileMaker platform enables rapid deployment of applications as well as for quick adaptability with agile systems.  
Some of the major components of FileMaker include the database, layouts, fields, records, portals, and scripts.  The database component of FileMaker allows the user to create an entity relationship model (ERM) based database using a GUI.  You can create entities and attributes of entities as tables.  From the tables, you can define relationships between tables and specify attribute keys.

The layout component of FileMaker determine how information is organized to display to the user.  In the layout editor you can arrange and format the display of fields and labels, create reports by grouping and summarizing data, and add graphical effects to each layout.  

A field within FileMaker is the basic unit of data entry for each record.  Each field is linked to an attribute from a database table.  Entering in data for a field will save that data to the database for the corresponding record for which it was entered.  Additionally, you can define other ways in which for the field to save the data.  For example, a field could save data based on an automated calculation or it could be saved from text-based input from the user.
A record in FileMaker consists of a set of fields that have been populated on a layout.  Each record consists of the data that is contained from a single activity or transaction.  An example record from a business's inventory product layout could include product name, product ID, cost, quantity, ect.
The portal component of FileMaker allows for the user to display fields from multiple related tables in an organized table.  You can directly modify the records through the portal.  For example on a student record, you could display a list of all the classes a student is taking.
Finally, the scripting component of FileMaker allows the user to automate reptitive or difficult tasks that can't be handled in other ways.  You can design scripts using predesignated control structures contained within FileMaker.  The control structures in FileMaker follow traditional programming paradigms for functions such as conditional statements and loop statements.

B.


### IV. Computer Store Inventory System Solutions

We implemented solutions to alleviate some of the issues the store has been experiencing.  In order to reduce the amount of records that contain an invalid UPC, we have designed several protocols.  We added a new boolean field to the Product entity in the database that stores whether or not a record contains a valid UPC.  Additionally, a color conditionally formatted button has been added to the main inventory layout that displays whether a record's UPC is valid based upon the respective boolean value.  The button is linked to a script that will check whether the current UPC is valid.  If the UPC is valid, the script modifies the new boolean field to reflect this as well as changing the color of the button.  Additionally, the script will format the string in the Product ID field so that is formatted in a standardized way that will be used across all records.  
   These protocols allow for validation of the UPC field of products.  In addition to the validating the field, we have added visual indicators to alert the user to potential errors before any further modification occurs.  We have implemented this by modifying existing scripts to check for inconsistency in fields such as quantity.  If a user pulls up a specific record that contains a negative quantify value, they will be immediately alerted to this through a prompt.
Furthermore, we have also created a method in which to trim the number of records in the current system file.  An export script has been created that searches the current file for all records that are two years older than the current date.  Once all the respective records have been found, they are exported to a backup file in the same directory.  The records are then deleted from the main system file.

### V. Future Development

Future Development
Currently, we are developing additional features for the inventory system.  We are working on a tool that handles the merging of two duplicate records given by the user.  The tool will copy the needed information from a designated parent as well as handling all the back-end rerouting that needs to occur to result in the correct values for fields such as quantity that are derived from other fields and files within the system.
Moreover, we are also working on another feature that aids in preventing user-induced error.  The school library's FileMaker application uses a built-in menu to navigate around the program.  Similarly, we are currently designing a menu that users interact with to handle queries in the system rather than users having access to unnecessary records.
The current computer store FileMaker application does not have any reference guides or documentation.  In the future, we would like to write a user reference guide that teaches the employees the how to operate the system and provide a means for immediate help if necessary.
We have noticed through examination of the current database structure that certain keys and relationships exist that can create problems for the inventory system.  In the future we would like to improve some of these database relations in order to prevent inconsistencies and lessen redundancy in the current system.

### VI. Summary

Several issues within the UTM Computer Store Inventory System have been addressed through modification of the current system with FileMaker Pro.  As we continue to implement solutions, we hope to make the FileMaker application that the UTM Computer Store uses more efficient and user-friendly so that the employees of the store do not have to waste needed resources due to software problems.

<hr>

>References
"FileMaker Script Execution Time Cut From 5 Hours To 6 Seconds." HOnzas Bits 24U RSS. N.p., n.d. Web. 10 Oct. 2016.

>Industry, By. "FileMaker Solution Showcase | FileMaker." FileMaker. FileMaker, Inc., n.d. Web. 03 Oct. 2016.  (FileMaker, 2016)

>Weber, Mike. "FileMaker History." Mac Software Guide. Cobweb Publishing, Inc., 15 Sept. 2008. Web. 3 Oct. 2016.  (Weber, 2008)

>What Is FileMaker? Perf. Richard Carlton. YouTube. FileMaker Training Videos, 22 May 2016. Web. 3 Oct. 2016. (Carlton, 2016)
