# Cipher Site

## Created by Xia Amendolara 28th, 2017

  This website was built in Drupal, a framework of PHP. It features a custom module that allows the user to encrypt messages using a Caesar's cipher (aka shift cipher). Shift ciphering is a commonly used form of encryption.


## User Story

* As a user I would like to click on a menu item to encrypt a message.

* As a user I would like to enter a phrase to be encrypted.

* As a user I would like to choose the direction letter will shift between left and right.

* As a user I would like to enter the number of spaces letters will be shifted (positive integers only).

* As a user I would like to receive my encrypted message on another page, and I would like it to be all lowercase.


## Implementation Plan

| Objective | Implementation | Status |
|:-------------:|:-------------:|:-------------:|
| Download the Drupal core and create a new project | cd cipher project | completed |
| Remove the .gitignore file | $ git rm .gitignore | completed |
| Add README.md | $ touch README.md | completed |
| Set up database with localhost user | navigate to myphpadmin | complete |
| Export database to db-backup | export .zip to sites/db-backup | complete |
| Create custom module for cipher | mkdir sites/all/modules/cipher | complete |
|Create two files necessary for custom module (.info and .module)| touch sites/all/modules/cipher .info and .module | complete |
| Fill out necessary information in .info file | name, description, package, core, and files[] | complete |
| Set up hook_menu within .module (with success page redirect) | function cipher_menu() | complete |
| Create function for form | function cipher_form() | complete |
| Create form validation | "#required" => true | complete |
| Create form submission with corresponding function | $form[submit] , function cipher_form_submit() | complete |
| Create function for success  with session data | function cipher_success() | complete |
| Create element validation for positive integers with corresponding functions | "#element_validation " => array('element_validate_integer_positive', 'element_validate_range') | complete |
| Create element validation for shift direction with corresponding functions | "#element_validation " => array('element_validate_direction') | complete |
| Add to submit form function: string to lower, filter for letters | drupal_strtolower($phrase), ctype_alnum($letter)| complete |
| Convert letters to corresponding ASCII number | ord($letter) | complete |
| Add conditional to account for alphabet range | if($ascii_letter < 0 || $ascii_letter > 26 ) | incomplete |
| Use shift value to shift numbers to the right | incomplete |
| Use shift value to shift number to the left | abs() (more research needed not quite sure yet) | incomplete |
| Convert ascii back to letter | chr(ascii_letter + 97 (lower case letters start at 97 on chart)) | incomplete |
| Print encrypted phrase to sucess page | $_SESSION['phrase_output'] = $encrypted_phrase | started |



## Setup/Installation Requirements

  * Follow the link to the Git repository for this project. [Github](https://github.com/Xesme/cameron-coffee.git)
  * In the terminal run `$ git clone link-to-repo-here`
  * In the terminal run `$ cd project-name`
  * Open MAMP and and click on preferences
  * In the preferences menu navigate to webserver and set your document root to project-folder and click okay
  * Click start server in MAMP homescreen
  * On the MAMP homepage click `myphpadmin` to be redirected to the tools page
  * Use the import tab to import the project sql file located in project-root/sites/db_backup/
  * Use the users tab to create a new user with all privledges
  * Open your broswer and go to `localhost:8888` to view the web application in browser.

## Bugs

There are no known bugs at this time, but please contact the creator with questions or concerns regarding this application.

## Technologies Used
* Drupal
* PHP
* Git
* SQL

## Licensing
This application features MIT licensing.

Copyright &copy; 2017 **Xia Amendolara** All Rights Reserved.
