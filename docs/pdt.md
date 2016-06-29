# pdt



## References
* https://wiki.eclipse.org/PDT/Installation
* https://wiki.eclipse.org/Eclipse/Installation
* https://eclipse.org/pdt/

##### Install JDK
* https://github.com/bachmeb/java-jdk

##### Download the version of Eclipse that works with your JRE
* Eclipse 4.2.2 (Junu) runs on JRE 1.6
  * https://wiki.eclipse.org/PDT/Installation#Eclipse_4.2_.2F_Juno_.2F_PDT_3.1.1
  * http://www.eclipse.org/downloads/packages/release/juno/sr2
  * http://www.eclipse.org/juno/
  
* Mars runs on JRE 1.7
  * https://www.eclipse.org/downloads/packages/eclipse-php-developers/marsr

##### Extract eclipse-php-mars-R-win32-x86_64.zip
* Use 7-Zip on Windows
 
##### Add Zend to Available Software Sites
* Help
  * Install New Software
    * Click Add
      * Name: Zend
      * Location: http://downloads.zend.com/pdt
      * Click OK

##### Install Zend Debugger
* Help
  * Install New Software
    * Work with: Zend
    * Select available software
      * Name: Zend CE Features
        * Zend Debugger Feature
    * Click Next
    * Click Next
    * Agree to license terms
    * Click Finish
    * Restart Eclipse
