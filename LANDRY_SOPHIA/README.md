# Project Title
Personal Workout Coach for Women

# Installation Instructions
This program reqires modules ics for Calendar download and datetime to manipulate dates and times in scheduling.
!pip install ics must be ran in order to download the ics file at program completion.

# Program Description
This program is designed to provide a workout plan for women to align with their hormone/menstrual cycle.
Throughout the menstrual cycle, the hormones change and syncing your workouts to align with those changes has shown
to be beneficial for mood, sleep, and cycle symptoms.
This program requires the user to know what day of their cycle they are on. The user will be prompted to enter the day
of their cycle they are on. The program will convert that number into a variable that will be used to create a workout plan
starting from that day in their cycle. The program will create events that will be downloadable in an ics file and can be imported into
any calendar system, such as Outlook, Google, or Apple Calendar.

The program will repeat for 3 cycles. At that point, the user should re-evaluate their cycle to ensure it is still on the same schedule.
The user will need to run this program again to download a new file to be imported to their calendar system.

# Issues during development
I first started by developing a simple program that would tell users what workout to do on the day they are currently on in their cycle.
However, this was not as efficient as I wanted it to be. I was being given the same few exercies but I wanted more variety. I also
didn't think it would be helpful for a user to have to go into the program every day to know what workout to do. In the second version of the
program, I utilized the random module to select a specified number of random items in a list.

I wanted to be able to upload this into a calendar system. This proved to be very difficult. I was able to find the module to use but ran
into many obstacles while developing the code:
1) I had to change the "print" command to reflect the calendar module - this required the creation
of an event for each workout.
2) I kept receiving an error that there wasn't an object in the list for each event/workout. I knew I needed to re-do
how the event descriptions were written. I found the solution to be joining the two parts (exercise + cardio, etc) as one string using the ".".join function.
3) I kept receiving an error when trying to download the file. I learned that "!pip install ics" was required to download the ics module into the
system.
4) I wasn't seeing the file download onto my computer. I learned that Colab downloads files into its own folder which you must open to
download onto your device.
5) When I finally downloaded the file into my calendar system (Google Calendar), the events were being imporoted at the
time that I imported the file. I had to go back through to add a specified time using hours, minutes, seconds, etc. However, when I imported the
file, instead of entering them at 9AM as specified in the code, it entered at 4AM. I wasn't able to figure out why that was. I am wondering if it
has to due with timezones, but in  my research I found that the ics module uses the users time zone.
6) Once I had the file imported, I realized it
only provided the workouts for those 28 days. I went back to the datetime module to see what I needed to do to create the repeat. I used the month
variable to create a 28 day month that would repeat for 3 months, or for one quarter. I felt this would be sufficient to allow the user to update
their cycle if it were to change.
