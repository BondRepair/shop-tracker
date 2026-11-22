BOND SHOP TRACKER — hosting the app (one-time, about ten minutes)

This folder is the whole app. Put it on any static web host and open index.html from the
shop phone or iPad. GitHub Pages is free and fine for this:

 1. Sign in at github.com (create a free account if needed). Click "New repository".
    Name it   shop-tracker   and leave it Public (the page has no data in it; records live on the device).
 2. On the empty repository page choose "uploading an existing file" and drop in every file from this
    folder: index.html, sw.js, manifest.webmanifest, icon-180.png, icon-192.png, icon-512.png.
    Click "Commit changes".
 3. Settings > Pages. Under "Build and deployment" set Source to "Deploy from a branch", branch "main",
    folder "/ (root)". Save. After a minute the page shows the address:
        https://<your-username>.github.io/shop-tracker/
 4. Install it on each device and open it from the icon from then on (it works without a signal
    after the first open):
      iPhone / iPad   Safari > Share > Add to Home Screen
      Android         Chrome > menu > Install app (or Add to Home screen)
      Windows / Mac   Chrome: install icon in the address bar; Edge: menu > Apps > Install this site as an app;
                      Safari on Mac: File > Add to Dock
    Reading labels: tap "Read label photo" in a scan box and photograph the plate (the reader downloads once,
    about 5 MB, then works offline). Or copy the text with the phone's own tool (iPhone: Scan Text in the box;
    Android: Camera > Google Lens > select text > Copy) and paste it. The app sorts the text into the fields
    either way. Always compare the serial with the plate: readers confuse O with 0 and I with 1.
 5. In the app: Setup > Restore from backup > pick bond-shop-starter-backup.json (every job, part line
    and stock line from Bond_Shop_Tracker_8.xlsx, including the Self / Chevy 3500 HD job).
    Already have real records in the app? Choose Merge, not Replace: it adds what is missing and
    leaves what you entered alone. With sync on, restore on one device and the other follows.

PARTS IN THE FIELD

Inside a job, + Add part needs only what the part is. Tap a quick pick (what you use most, with
shelf parts first and their count), or type it, or take a photo of the old part. Part #, supplier
and prices can stay blank; the line shows "no part # yet" on the job and in Parts > Needed, where
the Find button searches the machine's make and model plus your words, and OEM diagrams gives the
exploded-parts drawing. Fill the number in when you find it, then Order these as usual. The part
photo travels with the line to the other device.

SYNC BETWEEN TWO DEVICES (optional, one-time, about ten minutes)

With sync on, every job, part line, restock line and setting appears on every device that holds the
same sync key, usually within a second, and devices catch up after being offline. Photos stay on the
device that took them. The records are kept in a free Google Firebase database; the app's Setup tab
walks through it, in short:

 1. console.firebase.google.com > Add project ("Bond Shop Tracker", Analytics off).
 2. Build > Firestore Database > Create database > location us-east1 > production mode.
 3. Rules tab > paste the rules shown in the app (Setup > Sync > Create the key) > Publish.
 4. Build > Authentication > Get started > Sign-in method > Anonymous > Enable.
 5. Project Overview > Add app > Web. Copy the firebaseConfig block into the app > "Create key and connect".
 6. Copy the sync key (Setup > Sync) and paste it into Setup > Sync on the second device > Connect.
    Send the key by text message or AirDrop, not by posting it anywhere: whoever holds it can read and
    change the shop's records.

Free tier limits (50,000 reads and 20,000 writes a day) are far above what a shop generates; the
Firebase console shows usage. The "Delete everything on this device" button only clears that device;
with sync on, the shared records come straight back.

Updating the app later: replace index.html in the repository with the new one. Open devices pick it up
on their next launch; records are untouched.

Backups: Setup > Back up everything, once a week. Keep the file in Google Drive, iCloud Drive or OneDrive, in a folder shared with whoever else should have a copy.
If the device is lost, install the app on the new one and Restore.

Privacy: the address can be opened by anyone who has it, but it contains no records — those live only
on the device that entered them.
