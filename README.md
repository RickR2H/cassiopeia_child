# Setup VScode for Child theme SCSS compiling

## Creating the child theme
In my example I've created a Joomla child theme with the name of "child". The name of the new theme is "cassiopeia_child"

## Setup VScode
Install the SCSS compiler extension in VScode: https://marketplace.visualstudio.com/items?itemName=glenn2223.live-sass

To make maintance easy I automatically copy the folders and files from **media/templates/site/cassiopeia_child** to **templates/cassiopeia_child/media** folder. That way the template is installable. Also maintaining a git repo is easier as all the files are in one folder.

To copy the files automatically I use the extension FileSync:
https://marketplace.visualstudio.com/items?itemName=pgmjah.filesync (example configuration files is present in the .vscode folder)

Note: the files are only copied. When working on SCSS files use the **media/templates/site/cassiopeia_child/scss** folder.

## Setup the development environment
- Install Joomla on your local server
- download and install the repo. The child theme is now installed.
- Move the .vscode folder to the Joomla root
- To make the FileSync work, change the paths in the fsconfig.json to the absolute paths to the **media/templates/site/cassiopeia_child** and **templates/cassiopeia_child/media** folder.

## Override the bootstrap variables
I've created the two example files (template.scss / template-rtl.scss) which are needed to compile the template.css with custom bootstrap variables.

To start compiling the CSS just click the "Watch Sass" button on the bottom right of VScode. As soon as the template.scss or template-rtl.scss is changes the css files are created.

## Good to know:
- Make sure all the folder in the templates media folder are not empty. I used .keep files for that. This will also add the empty folders to a git repo.
- The template-rtl.scss is only compiled when you start the Sass watcher or when the template-rtl.scss is saved. When the site goes to production, make sure you template-rtl.scss is create (Just save the file once or turn the compiler on and off again)
- I've made some small modifications to the templateDetails.xml. I added the .vscode folder to the installation.

Youtube link to video: https://www.youtube.com/watch?v=lIli9zzOrg0
