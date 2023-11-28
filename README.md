# FixApacheLinux

https://www.youtube.com/watch?v=PhjtBCh5HBE



#Change PHP version
sudo update-alternatives --config php


#fĩ php ini // php version
The error message you provided indicates that the PHP extensions ext-dom and ext-curl are missing from your PHP installation, and they are required by the packages listed. To resolve this issue, you should install and enable these PHP extensions. Here are the steps to do so:

Install and Enable ext-dom:
Install the ext-dom Extension:

The ext-dom extension is used for Document Object Model (DOM) manipulation in PHP. You can install it using the package manager appropriate for your system. Here are some examples for common package managers:

On Debian/Ubuntu-based systems:

bash
Copy code
sudo apt-get install php8.0-dom  # Replace with your PHP version
On Red Hat/CentOS-based systems:

bash
Copy code
sudo yum install php-dom
On macOS with Homebrew:

bash
Copy code
brew install php@8.0  # Replace with your PHP version
brew link php@8.0
brew install php@8.0-dom  # Replace with your PHP version
Enable the ext-dom Extension:

Once the extension is installed, you need to enable it in your PHP configuration. The configuration file for the CLI version of PHP is typically located at /etc/php/8.0/cli/php.ini. You can edit this file using a text editor:

bash
Copy code
sudo nano /etc/php/8.0/cli/php.ini  # Replace with your PHP version and use your preferred text editor
Find the line that starts with ;extension=dom (it may be commented out) and remove the semicolon at the beginning to uncomment the line:

ini
Copy code
extension=dom
Save the file and exit the text editor.

Restart PHP:

After enabling the extension, you need to restart PHP for the changes to take effect. You can do this by restarting your web server (if you're using one) or by restarting PHP-FPM if you're using PHP-FPM. Here's how to restart PHP-FPM:

bash
Copy code
sudo service php8.0-fpm restart  # Replace with your PHP version
Install and Enable ext-curl:
The ext-curl extension is used for making HTTP requests from PHP. You can follow a similar process to install and enable it:

Install the ext-curl Extension:

On Debian/Ubuntu-based systems:

bash
Copy code
sudo apt-get install php8.0-curl  # Replace with your PHP version
On Red Hat/CentOS-based systems:

bash
Copy code
sudo yum install php-curl
On macOS with Homebrew:

bash
Copy code
brew install php@8.0-curl  # Replace with your PHP version
Enable the ext-curl Extension:

Edit the PHP configuration file for the CLI version (e.g., /etc/php/8.0/cli/php.ini) as described in the previous section, but this time find the line related to ext-curl and uncomment it:

ini
Copy code
extension=curl
Restart PHP:

Restart PHP-FPM or your web server as mentioned earlier to apply the changes.

After completing these steps, both ext-dom and ext-curl should be installed and enabled in your PHP environment, resolving the issues you encountered with the packages that require them. You can then try running your PHP application or Composer again to ensure that the problems are resolved.






