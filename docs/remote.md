# remote 

## References
* http://www.patrickjwaters.com/blog/2011-07-24/how-setup-eclipse-php-pdt-remote-system-explorer-theme-manager-and-drupal-plugins/35

##### Install Remote System Explorer End-User Runtime and Remote System Explorer User Actions
* Help > Install New Software
  * Work with: All Available Sites
  * Name: General Purpose Tools
    * Click 'Remote System Explorer End-User Runtime' and 'Remote System Explorer User Actions'
  * Click Next
  * Agree to license terms
  * Click Finish
  * Restart Eclipse

##### Create SSH connection
* Window > Open Perspective > Other
 * Select Remote System Explorer

##### 
* File > New > Other > PHP Project
  * Create a PHP Project
    * Project name: whatever
    * Create project at existing location (from existing source)
    * Directory: C:\DEV\git\reponame
    * Use project specific settings: YES
    * PHP Version: PHP 5.3
    * Use project as source folder
    * Enable JavaScript support for this project: YES
    * Click Next
  * PHP Facets
    * Configuration: Minimal Configuration
    * Click Next
  * PHP Include Path
    * Click Next
  * PHP Build Path
    * Click Finish


