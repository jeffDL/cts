# csv_to_sms
 Bridge between csv `phone_list.csv` and [Twilio](twilio.com) sms


To set up:
1. Install Anaconda.
2. Launch the CMD.exe prompt
3. In the Command prompt,

    `cd csv_to_sms`  to switch folders and type:

    `init`

to install Twilio and set up environment. If the other commands aren't working, start over by typing `init` again.

* To send a mass sms to everyone in *phone_list.csv*

    > *Remember to always text person-to-person and **secure positive consent to recieve sms updates** before sending any automatic messages!*:

    `list_send`

* To refresh all the day's messages:

    `check_sms`

* To send a single sms:

    `single_send 5553334444 "Type your message here after the quote mark and escape quotes with backslash"`

* If you want to check all the messages for a given number, or you forget to write down the ( \*auto \*Name ) with the real name, you can always look up by number with:

    `contacts 5553334444`


*single_send.py* and *contacts.py* will try to associate numbers with the main phone_list.csv, and if there is no match, it will provide the ( \*auto \*Name ) that will be associated with incoming replies.

* To Add or Modify a name on the master *phone_list.csv*, Type:

    `add 5553334444 firstname Lastname`

  These will be added to the bottom of *phone_list.csv* unless the last record for that number matches the input. They will not overwrite old records in the list, but csv_to_sms **will** take the lowest name in the file for every given phone number, ignoring earlier listings. Be careful with this!

Records roll over to next date at *cutoff_time* set in *variables.py*
