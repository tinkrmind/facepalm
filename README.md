# facepalm

### Getting student photos:

Easily downloaded by downloading the source code of itp.nyu.edu/er/people (only accessible by staff) Don't tell Marlon!

### Getting student websites:

I was surprised to find that there is no central repository for the student websites. So, I had to scrape the web for them. The class websites were a good place to start. But I finally settled on googling student names along with the word 'itp' to get the websited. I made a google sheet with student names and made a google URL using the same. Then I manually clicked on the URL and pasted the webpage address from the resulting search back into the doc. This took a lot more time than I'm willing to admit and I'm not even halfway through.

Having accumulated enough webpages I tried to scrape blogs and make a word cloud for each person. I soon realised that this was not possible simply because of the diversity of the student webpages.
Tried to follow this guide: https://www.dataquest.io/blog/web-scraping-tutorial-python/

### Redirecting to another website:

I found that the redirects go to the / directory of the server unless they begin with http://. So a redirect to "google.com" takes you to localhost:3000/google.com while redirecting to "http://google.com" takes you to google homepage. This little bit to trivia cost me around an hour. Also, 301 in code lets the search engines know that it is a permanent redirect.

References:
 	https://davidwalsh.name/express-redirect-301

### Storing website addresses

A variable student address means that the webpage address has to be stored off the server so that if the server restarts the data is still maintained. I could use mongodb for this, but then I'd have to query mongodb for the webpage every time and that would add to the delay for pageload. Since most student webpages aren't that fast to begin with, I decided to save everyone the trouble and use [node-persist](https://www.npmjs.com/package/node-persist) instead.

### Allowing students to change redirect address:

Student webpages change constantly and a student should have the freedom to change which website their name forwards to without having to write me an email and then me changing the address manually. 

### Using google's Roboto font

Reference: https://fonts.google.com/?selection.family=Roboto

### Generating user passphrases

Reference: https://www.fourmilab.ch/javascrypt/pass_phrase.html

### Future direction:
- Add people skills
- Filter by skills
- Make a project search
- Better user/password management
- Use jQuery for form submission result
- Rollover with webpage preview
