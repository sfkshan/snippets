# How to un-install PostgreySQL

[SO link](https://stackoverflow.com/questions/8037729/completely-uninstall-postgresql-9-0-4-from-mac-osx-lion/9240197#9240197)

The following is the un-installation for PostgreSQL 9.1 installed using the EnterpriseDB installer. You most probably have to replace folder /9.1/ with your version number. If /Library/Postgresql/ doesn't exist then you probably installed PostgreSQL with a different method like homebrew or Postgres.app.

To remove the EnterpriseDB One-Click install of PostgreSQL 9.1:

Open a terminal window. Terminal is found in: Applications->Utilities->Terminal
Run the uninstaller:

sudo /Library/PostgreSQL/9.1/uninstall-postgresql.app/Contents/MacOS/installbuilder.sh
If you installed with the Postgres Installer, you can do:

open /Library/PostgreSQL/9.2/uninstall-postgresql.app
It will ask for the administrator password and run the uninstaller.

Remove the PostgreSQL and data folders. The Wizard will notify you that these were not removed.

sudo rm -rf /Library/PostgreSQL
Remove the ini file:

sudo rm /etc/postgres-reg.ini
Remove the PostgreSQL user using System Preferences -> Users & Groups.

Unlock the settings panel by clicking on the padlock and entering your password.
Select the PostgreSQL user and click on the minus button.
Restore your shared memory settings:

sudo rm /etc/sysctl.conf
That should be all! The uninstall wizard would have removed all icons and start-up applications files so you don't have to worry about those.