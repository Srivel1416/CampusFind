# CampusFind
CampusFind is a college Lost and Found platform that helps students report, search for, and recover lost belongings. Users can post lost or found items with descriptions, images, dates, and locations, making it easier to connect owners with finders and ensure lost items are returned safely.
1. HTML – Structure of the website
HTML is used to create all the elements that appear on the website.
A. Document declaration and head section (Lines 2–8)
- <!DOCTYPE html> tells the browser that the document uses HTML5.
- <html lang="en"> specifies that the page language is English.
- <head> contains information about the webpage.
- <meta charset="UTF-8"> supports different characters and symbols.
- <meta name="viewport"> makes the website adjust to different screen sizes.
- <meta name="theme-color"> specifies the browser theme colour.
- <title> sets the browser tab title to CampusFind — Lost & Found.
B. Sidebar navigation (Lines 95–115)
The sidebar is the main navigation area of the website.

It contains:
1. CampusFind logo and website name.
2. Overview – displays the home page.
3. Report an item – opens the reporting form.
4. Browse reports – displays lost and found reports.
5. Dashboard – displays statistics and recent activity.
6. Quick calculator – opens the calculator.
7. Help section – allows users to open the chatbot.
8. Profile section – displays the campus member information.
The data-page attribute identifies which page should open when a navigation button is clicked.
C. Main content area (Lines 117–208)
The <main> element contains the different pages of the website.

1. Home page (Lines 123–139)

The home page introduces CampusFind.

It contains:
- Welcome banner.
- Report an item button.
- Number of lost items.
- Number of found items.
- Total number of reports.
- Website features.
- Recently reported items.
2. Report an item (Lines 141–159)

This section contains a form for reporting lost or found belongings.

The form collects:
- Student's full name.
- Register number.
- College email.
- Phone number.
- Item name.
- Report type (Lost or Found).
- Item category.
- Location and description.
It also contains a confirmation checkbox, Submit button and Clear form button.

3. Browse reports (Lines 161–167)

This section displays all the submitted reports.

It contains:
- Search box.
- Lost items filter.
- Found items filter.
- List of available reports.
4. Dashboard (Lines 169–180)

The dashboard provides a summary of website activity.

It displays the number of lost reports, found reports and total reports. It also shows the latest activity and quick navigation buttons.

5. Quick calculator (Lines 182–193)

This section contains a calculator with:
- Addition.
- Subtraction.
- Multiplication.
- Division.
- Percentage.
- Decimal values.
- Clear and delete options.
6. Signup and Signin (Lines 195–207)

These sections provide forms for creating a demo account and signing in.

The signup form collects an email address and password. The signin form checks the entered credentials against the saved demo account.
D. Notification and chatbot (Lines 211–217)
The website contains a notification system and a chatbot.
- Toast notification: Displays messages such as successful report submission or incorrect login details.
- Chatbot: Provides basic instructions to users.
- Chat input: Allows users to type questions.
- Send button: Sends the message and displays an automatic response.

2. CSS – Designing the website
CSS controls the appearance of CampusFind. It makes the website attractive, organized and user-friendly.
A. Google Fonts (Line 10)
The code imports two fonts:
- DM Sans
- Manrope
These fonts improve the readability and appearance of the website.
B. CSS variables (Lines 11–16)
The :root selector defines reusable colour values.

For example:
- --bg – background colour.
- --surface – card background colour.
- --text – text colour.
- --primary – main purple colour.
- --mint – green colour.
- --radius – border radius.
Why are CSS variables used?

Instead of writing the same colour repeatedly, we define it once and reuse it throughout the website.
C. Universal selector and body styling (Lines 17–20)
- * applies box-sizing: border-box to all elements.
- scroll-behavior: smooth provides smooth scrolling.
- body sets the background, text colour and font.
- body.dark changes the colour variables when dark mode is enabled.
D. Sidebar and navigation styling (Lines 21–34)
These styles control:
- Sidebar background.
- Logo appearance.
- Navigation buttons.
- Hover effects.
- Help card.
- Profile avatar.
The position: sticky property keeps the sidebar fixed at the top while scrolling.
E. Main layout and buttons (Lines 35–46)
These styles control the main content area, headings, buttons and page transitions.

The .primary-btn class creates the main purple buttons, while .secondary-btn creates secondary buttons.

The .page class hides inactive pages, and .page.active displays the selected page.
F. Hero section and statistics (Lines 47–60)
The hero section is the large welcome banner on the home page.

It uses:
- Linear gradients.
- Rounded corners.
- Decorative circles.
- Text shadows and visual effects.
The statistics section uses CSS Grid to display four information cards in a row.
G. Forms and item cards (Lines 61–80)
These styles control:
- Input fields.
- Dropdown menus.
- Text areas.
- Form labels.
- Search boxes.
- Lost and found item cards.
- Category labels.
- Empty-state messages.
The .pill.lost and .pill.found classes use different colours to distinguish lost and found items.
H. Calculator, notifications and chatbot styling (Lines 81–89)
These styles control the calculator display, calculator buttons, toast notifications and floating chatbot window.
I. Responsive design (Lines 90–91)
The @media rule makes the website responsive.

It adjusts the layout according to screen width.

For example:
- On smaller screens, the sidebar changes into a mobile navigation menu.
- Feature cards are displayed vertically.
- Forms change into a single-column layout.
- Item cards adjust to fit mobile screens.
This allows the website to work on computers, tablets and mobile phones.

3. JavaScript – Functionality of the website
JavaScript is the most important part for making the website interactive.
A. Selecting HTML elements (Line 220)
const $ = id => document.getElementById(id);

This creates a shortcut for selecting HTML elements using their IDs.

For example:

$('reportForm')

is equivalent to:

document.getElementById('reportForm')

This makes the JavaScript code shorter and easier to write.
B. Local storage (Lines 221–225)
The website uses localStorage to store information in the browser.

Two important functions are:
- storage.get() – retrieves previously saved information.
- storage.set() – saves information in the browser.
The reports are stored using the key campusfind_reports.

This allows submitted reports to remain available even after refreshing the page in the same browser.
C. Page navigation (Lines 228–249)
The navigate(page) function is responsible for switching between different pages.

How it works:
1. It removes the active class from all pages.
2. It selects the requested page.
3. It adds the active class to that page.
4. It updates the page title and subtitle.
5. It closes the mobile navigation menu.
6. It refreshes the reports or dashboard when required.
7. It scrolls to the top.
The toggleMobileNav() function opens and closes the mobile menu.
D. Toast notification (Line 250)
The showToast(message) function displays temporary notification messages.

For example:
- Your report has been submitted successfully!
- Account created!
- Incorrect email or password.
The notification disappears automatically after 2.6 seconds.
E. Dark mode (Lines 251–255)
The toggleTheme() function switches between light and dark modes.

It works by adding or removing the dark class from the <body> element.

The selected theme is saved in localStorage, so the website remembers the theme when reopened in the same browser.
F. Displaying item reports (Lines 258–280)
This part handles the display and organization of submitted reports.

1. escapeText()

This function converts special HTML characters into safe text characters before displaying user-submitted information. It helps prevent HTML injection.

2. itemCard()

This function creates an HTML card for each reported item.

It displays:
- Lost or found status.
- Item category.
- Item name.
- Description.
- Location.
- Report date.
3. renderStats()

This function counts the lost reports, found reports and total reports.

It updates the statistics on both the home page and dashboard.

4. renderRecent()

Displays the two most recently submitted reports on the home page.

5. renderReports()

Displays all reports after applying the search and filter options.

6. renderDashboard()

Displays the five latest reports and updates the dashboard statistics.
G. Search and filter functionality (Lines 282–282)
The search input listens for the input event.

Whenever the user types something, renderReports() is called.

The filter dropdown listens for the change event.

It allows users to display:
- All reports.
- Lost items only.
- Found items only.
The search checks the item name, category, description and location.
H. Report submission (Lines 284–294)
This is one of the main functionalities of CampusFind.

When the user submits the report form:
1. preventDefault() prevents the page from refreshing.
2. checkValidity() checks whether the required fields are correctly filled.
3. The entered details are collected into an object.
4. The object is added to the reports array using push().
5. The reports are saved in localStorage.
6. The form is cleared using reset().
7. Statistics and report sections are refreshed.
8. A success notification is displayed.
9. The user is redirected to the dashboard.
I. Signup functionality (Lines 297–301)
When a user creates an account:
1. The form is validated.
2. The email and password are collected.
3. The account information is stored in localStorage.
4. The form is cleared.
5. A success notification is displayed.
6. The user is redirected to the signin page.
J. Signin functionality (Lines 302–309)
When the user tries to sign in:
1. The entered email and password are collected.
2. The saved account is retrieved from localStorage.
3. Both credentials are compared.
4. If they match, the user is signed in and redirected to the dashboard.
5. If they do not match, an error notification is displayed.
The Show Password checkbox changes the password input from hidden text to visible text.
K. Chatbot functionality (Lines 311–333)
The chatbot provides automatic responses based on keywords.

Important functions:
- toggleChat() – opens or closes the chatbot.
- addBubble() – displays messages inside the chat window.
- botReply() – checks the user's message and generates a suitable response.
- sendChat() – sends the user's message and displays the chatbot's reply.
For example, if the user types "How do I report a lost item?", the chatbot provides instructions for submitting a report.

Note: This is a rule-based chatbot. It uses predefined conditions and responses rather than artificial intelligence.
L. Calculator functionality (Lines 335–363)
The calculator uses JavaScript variables to store its current value, previous value and selected operator.

Important functions:
- updateCalc() – updates the calculator display.
- calcPress() – handles button operations.
It supports addition, subtraction, multiplication, division and percentage.

It also includes:
- AC – clears the calculator.
- DEL – deletes the last entered digit.
- Decimal point support.
- Division-by-zero checking.
The keyboard event listener also allows users to operate the calculator using their computer keyboard.
M. Initial loading (Line 364)
The following functions are called when the website loads:
- renderStats()
- renderRecent()
- renderReports()
- renderDashboard()
These functions display previously saved reports and update the statistics.

4. Important concepts used in this project
These are some programming concepts you should understand because they may be asked during your project demonstration.
Concept	Meaning in your project
HTML	Creates the webpage structure.
CSS	Designs and styles the webpage.
JavaScript	Adds functionality.
DOM	Allows JavaScript to access and modify HTML elements.
DOM Manipulation	Changes webpage content dynamically.
Event Listener	Detects actions such as clicks, typing and form submission.
Functions	Reusable blocks of JavaScript code.
Arrays	Store multiple reports.
Objects	Store individual report details.
Local Storage	Saves information in the browser.
CSS Grid	Arranges elements into rows and columns.
Media Queries	Adjust the website for different screen sizes.
JSON	Converts objects into a format suitable for local storage.

5. Important things to know about your project
There are a few technical limitations in the current code that you should be aware of:

1. No database: Reports are stored in browser localStorage, not in a central database. Different students using different devices cannot automatically see each other's reports.

2. Demo authentication: Signup and signin use localStorage. Passwords are stored as plain text, so this is not suitable for a real production login system.

3. No actual chatbot AI: The chatbot responds using predefined keyword conditions.

4. No image upload: The reporting form currently collects text details but does not allow users to upload item photographs.

5. Location field: The location and description are collected together in one textarea.

These are possible improvements for a future version of CampusFind.  


Vercel link: https://campusfind-sepia.vercel.app
