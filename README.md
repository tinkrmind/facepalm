# facepalm

## [Demo](http://as11613.itp.io:3000/)

## Note:

I am not providing the code because the student blog data is sensitive information that I do not wish to be misused.

## Vision

The overarching design goal of this exercise is to promote inter student collaboration. Public knowledge is the first step to mutual trust and respect

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

#### Thoughts on identifying student skills
It's important to consider the diversity of student websites. The easiest way would be to crawl the site and collect all text, and process it through keyword detection to identify the type of project e.g. workshop, electronics, web, VR/AR, DIY, straight up coding.. But one also has to consider the fact that many people don't write extensive blogs and instead document projects via videos, gifs, photos, audio, javascript.. It'd be hard to train a n algorithm to recognise these media.

Perhaps a better solutioon might be to use a peer to peer rating system like github. People could star their peers who help them with problems. This system would not only be much easier to implement but would also promote student collaboration and teaching. Ofcourse measures would be put in place to prevent people gaming the system by exchanging stars on a quid pro quo basis, but this is a solved problem and the community would self regulate in this aspect as well. It is best to have minimum intervention to build mutual trust in the system. This information could later on be useful for staff and resident selection. It would also provide a platform for outside parties like tandon students to identify points of connection at ITP.

Identifying trending projects and people could also generate a self renewing news feed for ITP and the prospect of such attention would also push students to document their projects better. 

The biggest problem most publishing platforms face is lack of fresh content. Content is expensive. But at ITP, we have quite the opposite problem. Students are generating great, novel content and are too busy to look for publishing avenues. The lack of attention to well documented projects demotivates further investment into documentation. ITP should be a publishing platform of it's own. Adjacent is a step in the right direction but curated magazines are slow and again, always wanting for tailored content. 
