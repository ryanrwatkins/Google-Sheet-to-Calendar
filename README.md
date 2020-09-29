# Google-Sheet-to-Calendar
A Google Script (java) for linking a spreadsheet to calendar in order to maintain an updated calendar

Here are the steps to get started:

1. The script is easiest to use if the Google Sheet and the Google Calendar are associated with the Google account, though you could do it with separate accounts if you have permissions for each).
2. Create a new Calendar with the Google Calendar. This is the calendar you want to update from the Google Sheet.
3. Create a new Google Spreadsheet that you will update.
4. In cell A2 of the Sheet you will want to insert the ID of the calendar you just created. Get the Calendar ID in the setting menu for the calendar. So head back to calendar, go into settings, select the new calendar, and then scroll down until see the Calendar ID number. Copy that number (which actually also looks like an email address) and past it in cell A2. You could put in A1 or any other cell, I just selected A2.
5. Now we have to create the part of the spreadsheet that will information for the calendar. I named my columns in Row 4 and then put the information starting in Row 5, though you could put it elsewhere.  For instance, A4 is Start Time, B4 is End Time, C4 is Topic, and D4 is presenter... and you could labels these as it makes sense for your events.
6. With the columns now labeled, you can create some draft events in the rows below. Maybe start out with 3 or 4, and then once you are used to working with the script you can add more. 
7. The dates and times do have to be in the date format, so once you have those in the sheet, highlight the dates and go to the Format menu, the Number submenu, and select Date-Time. You can highlight and change more cells if you want, but all date cells will have to be in this format for the calendar to know what to do with them.
8. Now for the script. Go to Tools in the Google Spreadsheets menu, and select script.  This will open up the Google Apps Script editor in a new tab. If this is your first time, you will have to give it permissions to access your Google Account.
9. Copy and paste the script from here (above) into the Google Apps Script editor.  This will replace the blank "myfunction" that they give you to start. 
10. The script has notes on what each element is doing. There are a couple that you will want to edit.

10a. On line 12 you will have to update the URL (web address) for the Spreadsheet you useing to maintain the calendar. If you have multiple Sheets, you can also add which Sheet within the Spreadsheet you are referring to.
10b. On line 13 you will want to update which cell of your sheet you put the calendar ID (again, mine was A2)
10c. On line 16 hange the range of cells that you are using to update your calendar. My script has cells A5:E17 since I had 5 elements I wanted to bring into each event (start time, end time, topic, description, and presenter).
10d. From lines 28 to 32 you will see the first elements for each event and I assigned those to variables. If you only want to bring 3 elements, for example, then just delete the others.  You have to have a title, start time, and end time to create an event, the other optional.
10e. The events are created on line 46 by sending the variables we just created. I also added a location for each event, 30 minute reminder to each event, and then the description at the end. You can delete any of these that you are not using, the first three are the required one (title, start time, end time).

11. And that is it. At the top of the script I did another function that adds a menu item to the Google Sheet each time it is opened, and this allows you to run script (i.e., create the calendar events) without having to open Google Apps Script editor each time.  You can also add Triggers in the Google Apps Scripts within the Edit menu (for instance, you can set a trigger to run the script every 4 hours, as an alternative to creating the menu option). Depending on your use, you may have preferences for how (and when). it is best to update your calendar with new events or edited events.

That is it, when you run the script you should get an updated calendar. I have it set to pause for 2 seconds between creating each event (line 49) since Google will only let you update so many events per second, but it runs quickly (depending on the number of events you have on the calendar).


