# Getting Started with Liferay Sync

Liferay Sync, released in February 2012, is an add-on product for Liferay 6.1 CE and EE that synchronizes files from your Liferay server directly to users' desktop and mobile environments. With Liferay Sync, your users can publish and access shared documents and files from their native environments without using a browser. Windows and Mac OS Desktops, and iOS-based mobile platforms are currently supported. As users add and collaborate on documents and files, Liferay Sync automatically synchronizes them across all configured Sync clients. Liferay Sync is fully integrated into the Liferay Platform so features such as authentication, versioning, workflow, and social collaboration extend naturally into the supported environments. Liferay Sync also makes documents available offline with automatic synchronization upon reconnection.

## How does it work?

Liferay Sync manages documents and site information through Liferay 6.1's built-in web services. Clients securely communicate to Liferay using user-supplied credentials, such that each user can only access those documents and sites for which they have permissions. Changes made through Liferay Sync are immediately available to the rest of the Liferay Platform, including users accessing Liferay through traditional web-based interfaces.

For desktop environments, a new folder structure is created and used for synchronizing files. Files found therein can be treated as any ordinary file. Credentials, sync frequency, and other folder options can be configured in-client. Native desktop notification events keep you abreast of what Sync is doing, and native menu and taskbar integration keep Sync controls within easy reach.

Mobile environments are naturally dependent on the way in which documents are handled. For iOS, documents are maintained in a file list, and can be viewed by clicking on the files themselves. External files accessible from other apps can be "opened" using Liferay Sync, thereby dropped into your Sync folder and synchronized across other Sync clients. "Pulling down" on the Sync file list forces a refresh (automatic sync frequency can be configured as well).

This Liferay Sync release is designed to work with both Liferay 6.1 Community Edition and Enterprise Edition. When used with the Enterprise Edition of Liferay, Sync will enable users to synchronize documents and files across all of the sites for which they have access.

## Installing Liferay Sync

For Windows or Mac OS, visit the Liferay Sync product page [Liferay Sync Product Page](http://www.liferay.com/products/liferay-sync/features), and click *Get it Now* (on the right-side navigation menu) to download the client application for your desktop environment. For Windows, the client application installer should be named `liferay-sync-<version>-<date>.exe`. For Mac OS, it should be `liferay-sync-<version>-<date>.dmg`. Follow the on-screen instructions of the installer wizard to configure your client to connect to an existing Liferay 6.1 deployment using your Liferay credentials.

### Windows

Upon launching the Windows application installer, you'll be promted to choose an installation location for Liferay Sync. Browse to an appropriate location and your machine and click *Next*.

![](../../images/liferay-sync-setup.png)

On the next screen, you can configure some properties for Liferay Sync, including whether you'd like Liferay Sync to start when you log on to your computer, whether to display desktop notifications from Liferay Sync, and how often to check the Liferay server for updates. The Desktop notifications inform you when new files or new versions of files are downloaded. Click the *Edit Settings* button to specify your server's URL and enter your Liferay credentials. Use the *Test Connection* button to make sure Liferay Sync can communicate with the server. Lastly, select the Liferay sites whose documents and files you'd like to sync.

![](../../images/liferay-sync-properties.png)

On the last screen, leave the *Run Liferay Sync* button checked to automatically start Liferay Sync after you click *Finish*.

![](../../images/liferay-sync-setup-complete.png)

The options for the Mac OS application installer are similar.

### Mac OS

<!-- to do -->

### iOS

<!-- get more detailed instructions -->

For iOS, visit the App Store and search for Liferay, and install the Liferay Sync App. Once installed, follow the on-screen instructions as above.

## Using Liferay Sync

Once installed, you'll see a Liferay Sync icon in your taskbar whenever it's running. A green checkmark means Liferay Sync has a working connection to your Liferay server and is updating the files in your Sync folder according to the interval you specified in the wizard. Click the Liferay Sync icon in your taskbar to bring up the menu.

![](../../images/liferay-sync-taskbar-menu.png)

*Open Sync Folder* opens your Liferay Sync folder in your native file manager.

*Open Site* provides links to the Control Panel pages of all the Documents and Media repositories which you have permission to access. By default, you can find links to your Liferay user's Documents and Media repository, and links to the Documents and Media repositories of all other sites which you belong to. If your Liferay user is an administrator, you'll also find a link to the global Documents and Media repository.

*Recent Files* shows a list of recently created or modified files from all the repositories you can access.

*Properties* opens the Liferay Sync Properties page that the installation wizard presented to you. The properties page lets you enter your Liferay server's URL, your Liferay user's credentials, and configure other permissions like automatic login, desktop notifications, and sync frequency.

*Sync Now* instructs Liferay Sync to immediately check the Liferay server for updates to shared files.

*Pause Syncing* instructs Liferay Sync to suspend syncing until further notice. If someone added a very large file that's taking a very long time to one of your shared folders, you might want to use this option and resume syncing at a later time.

*About* displays Liferay Sync version information, copyright information, and a link to Liferay's homepage.

*Check for Updates* checks to see if a new version of Liferay Sync is available from [liferay.com](liferay.com) and allow you to set whether or not Liferay Sync should automatically check for updates.

## Using your Sync folder

Once Liferay Sync has been configured and is running, any files you add to or modify in your Sync folder are automatically detected and uploaded to your Liferay server. Also, changes from other users are downloaded to your Sync folder.

When you delete files from your Sync folder, a `.liferay-sync.deletions` file is created there with the names of the files you deleted. This lets Liferay Sync know that you don't want these files in your Sync folder so it won't download them the next time it syncs. Note that the files listed in your `.liferay-sync.deletions` file are only local deletions since only the owner of a file can delete it from the Liferay server. You can remove entries from your `.liferay-sync.deletions` file to have Liferay Sync download them the next time it syncs.

Let's run through a simple exercise to familiarize ourselves with how to create, edit, download, and upload files with Liferay Sync. First, open your Liferay Sync folder in your file manager (use the *Open Sync Folder* option of the Liferay Sync menu from the taskbar) and create a new file called *README.txt*. Edit this file and enter the word *test*. Then use the *Sync now* option of the Liferay Sync menu to make sure that your README.txt file gets uploaded to your Liferay server. Let's check that we can access this file from our Liferay site. Open your browser, navigate to your Liferay site and sign in with your Liferay account credentials. Then navigate to your site's Documents and Media page in the Control Panel. Use *Go to* &rarr; *Control Panel*, make sure the site chose to sync with is selected in the context menu selector and click on *Documents and Media*. You should see your README.txt file listed there.

![](../../images/liferay-sync-documents-and-media.png)

Download the file (click the small triangle icon at the top right corner of the README.txt icon and select *Download*) to a convenient location on your machine and check that it still says *test*. Now open the *README.txt* file in your Sync folder and edit it so that it says *second test*. Choose *Sync now* again and then go back to your browser and refresh your Documents and Media page. Click on the *README.txt* icon, look at the information displayed to the right and you'll see that its version number has incremented.

![](../../images/liferay-sync-README.png)

Download the file again and you'll see that it now says *second test*--your edit was uploaded to the server and downloaded again by Liferay Sync. You can be confident that this edit was also downloaded by all other Liferay Sync clients connected to your site.