# Hosting digital lit in online journals

I've been asked a few times for advice on how best to host digital literature (i.e. work that is interactive/multimedia and often is made with bespoke HTML/CSS/JavaScript) in online journals.

I have been involved in editing/publishing digital-born literature since 2018 – first through [Voiceworks Online](https://www.voiceworksmag.com.au/), and more recently through [Crawlspace](https://crawlspace.cool). I've also been fortunate to have digital work published in other journals and gotten some insight into how they approach hosting digital work.

Here's how I recommend approaching hosting broswer-based digital work. This is likely not the perfect solution, and I'm learning more every day.

This guidance assumes a very basic understanding of what HTML is.

## Use `<iframes>`

An iframe is a HTML element that 'represents a nested [browsing context](https://developer.mozilla.org/en-US/docs/Glossary/Browsing_context), embedding another HTML page into the current one' ([MDN](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/iframe)). Simply put, it is like a window into another webpage you can put on your webpage.

The reason I recommend iframes is that many content management systems used by literary journals (Wordpress, Squarespace, Wix, etc) do not easily support complex custom code elements to be embedded into the blog posts. Most, however, have some sort of 'code block' or 'embedded content' content type which enables simple embed codes, e.g. the embed code for YouTube videos (which are in fact iframes!)

It's far easier to embed the digital work as an iframe than try to upload the digital work directly into your CMS – depending on how the work was made, the code may conflict with others.

Here's an example of an iframe element code:

`<iframe src="https://rory.green" width="100%" height="900px"></iframe>`

You should add the following attributes to any iframe element you're using to host work:
- `src`:  the URL of the page you want to embed into your own page
- `width`: the width of the iframe in your page – I recommend a value of 100% by default, but play around with what works for your site
- `height`: the height of the iframe in your page – I set this depending on what's inside the iframe, but generally between 700-1200px. Play around with what works for your site
Although iframes usually make it easy to embed digital work inside the current tech infrastructure of your journal, you now have another issue: where do you host the digital work, the webpage you are linking in your iframe?

## Host your own instance of the work

I strongly recommend liaising with artists to host your own instance of their work, rather than relying on artists to host themselves, for two reasons:
- They may take down their page at any time, breaking the iframe you have in your journal
- They may change the content of their page at any time, potentially resulting in you having work you haven't vetted appearing in your journal
There are several hosting services for simple websites. I suggest that you set up an account for your journal with one of these sites:
- [Netlify](https://netlify.app/): I use this service a lot, and what I'd recommend most for those with not heaps of technical expertise. It's simple to host a website through their [Netlify Drop](https://app.netlify.com/drop) service – you drag and drop a folder with the work onto the site, and it will generate a site for you. The free usage tier is very generous – I have used this for years and have dozens of small sites on my account, and I am still decades away hitting the limit of the free tier.
- [Glitch](https://glitch.com): I use this service a lot too, but more for prototyping and refining digital work. The free tier will suit most journal's needs. Projects can be collaboratively edited, which is great if you are actively developing/editing the piece with an artist. It also has a simple asset-hosting feature which is good for image/sound-heavy work. However, in my experience Glitch is more prone to small drop-outs as opposed to Netlify.
- [Neocities](https://neocities.org/): I have not personally used Neocities but I know many who have! It's on my to-do to test it out, and once I have I will update this note with more details. 
Ask the artist to send you a zip file of the completed piece, and then unzip and upload that to one of the services above. Make sure the main HTML file of the work is named 'index.html', so that the hosting services know what to serve as the homepage.

### Host your own multimedia assets for the work

There are two ways of embedding images or sounds into a HTML page – via an internal link or an external link.
An internal link is one made to another file within the website. In the code, the `src` value will be to a filepath, e.g. `src="images/duck"`.
An external link is one made to a file hosted on another web server. In the code, the `src` value will be a URL to a webpage e.g. `src="www.ducksarecool.com/ducks.jpg"`.
You should endeavour to have all embedded content – images, sound, custom fonts – internally linked, rather than externally. Why? For the same reason you want to host your own instance of the webpage – if the external links go down for any reason, an element of the piece will no longer work.
In past digital editor roles I've held, I usually advise artists on acceptance that they will need to bundle their assets in with the work, and update any filepaths accordingly. When I receive the zip from them, I open up the work and do a quick CTRL+F search for 'src', to check that there aren't any external links. If I find one, I will usually download it from the source and update it to an internal link myself, then inform the artist what I've done before it's published.

## Be clear about what you can/cannot publish
The guidelines above are for what are known as *static websites*. These sites are made up of HTML, CSS, JavaScript, and media files that only reference what is within the files of the project. Work made with Twine and Bitsy fit under this banner, as do most small-scale digital pieces. 

Some digital work, such as those that rely on a back-end database for the website, or those that rely on APIs to other software, may not be able to be hosted using the approach above. For this reason some journals (such as [Taper](https://taper.badquar.to/9/about.html#submit)) specify in their submissions guidelines that submissions 'should not use any external libraries or APIs, nor link to any external resources'.

It's up to the journal's editorial team to decide what level of technical complexity they can support. Whatever that is, you should communicate it clearly to artists in your submission guidelines so they don't waste time making something that you aren't equipped to publish.


## Be respectful of the wishes of the artist

Some digital work, such as Everest Pipkin's [Anonymous Animal](https://everestpipkin.itch.io/anonymous-animal), intentionally use external links as part of the creative intention behind the work. If you receive push back from artists on the hosting configuration for the journal, don't stress. Keep an open mind and have a conversation with them about the needs of the work and how that can be handled within the context of your journal's infrastructure.     


