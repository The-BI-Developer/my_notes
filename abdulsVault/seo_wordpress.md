# check your website visibility settings
Setings > Reading > Search engine visibility

# permalink
settings > permalinks
setup in a better way
at least do post name
__don't recommend this for old websites__


# (general settings) wordpress address must equal site address url 

# plugin
All in one seo
xml sitemap - what pages & posts are on my site

# submit xml sitemap to google search console
## html tag verification method
all in one seo > websmaster tools > embedded code > ownership verified

index > sitemaps
domain/sitemap.xml //sitemap submitted successfully >> there is two day delay proces

# check console on monthly basis

# optimising blog posts for seo
## title and description optimised
all in one seo > snippet preview in right pane
additional keywords
preview snippet editor

on page seo - what to do on each blog post

# keyword research
examples: semrush

# best practices
categories and tags
category is like a book chapter
add categories to menu structure
href phrases in your blog post > within and outside your website
optimise comments (not spam)
akismet anti spam plugin
settings > discussion > other comment settings > break comments into pages (enable) > save changes > paginated comments

# external links
help build ranking (link juice)
no follow attribute

<a href="http://example.com" rel="nofollow">example site</a>

allinoneseo > go to posts > add "nofollow" link

# excerpts
don't show full articles > considered duplicate
settings > reading > for each post > show excerpt

# speed and performance
hosting provider
caching plugin e.g. wprocket
reduce image heavy site > scale images down
descriptive image names + alt tags

# security and safety of the site
phishing site?
sucuri plugin
install ssl for your site


# 90% of google searches
scour pages and index them
answering query really well

# on page seo
first phrase of title
include keywords in your first paragraph
url's structure should be short - keywords that help us rank
optimise subheadings - supporting keyword
internal links close to the top
keyword in external article e.g. <u>how to install google analytics for beginners</u>
add links to previous blog posts
alt text - what is the image about (image library)
meta description - what this article about - its excerpt of the link in google search

working on site itself


easier as within control
- content
- alt & title tag
- keyword
- image description
- internal link

## intro
homepage, post page, category page, date archive page, tag page, author page = duplicate!!!
tag pages for organising content

one full webpage...other places excerpts or titles
## themes
genesis and thesis

GTMetrix.com - analyse page load times > look for A or B ratings

look for large files that causes problems

delete old themes - route for hackers???

## general settings
site title & tagline
	custom logo image
	don't stuff keywords in here
## writing settings
Update Services
	search "wordpress ping list" | notifies services about new content posted
## reading settings
creates rss feeds for your site - limit rss feeds to 10
use excerpt for each post in feed

## permalinks
?p=123 is ugly and useless for search engine 
post name uses post slug - portiont of url that represents post
cusotm structure: %category%%postname%
google panda/penguin look for spam

## essential plugins
seo: yoast or all in one
w3 total cache: speeds up (by fredrict townes)
dynamic widgets: context sensitive sidebards and other elements
keep plugins to a minimum

wpp-dbmanager - periodic updates and backup via email for server crash circumstances
google xml sitemaps for video - if you have lots of video
contact form

automatic updater

broken link checker - google doesn't like broken links - good for seo

akismet anti spam
ci blacklins - internal linker - setup rules > internal links updated when you add new content e.g. it would be a pain to find related posts that mention your new post

wp secure

yarpp - related posts section on each of the posts - interlinks content

wp sticky - introductions to category and tag pages

## repittion of keywords
pacificplex prom dresses
ever-pretty prom dresses

##sidebar dynamic menus

## <!--more--> quicktag

## rel=nofollow //stops following
affliate links are nofollow
only endorse credible sites

## google tools (webmaster, analytics, authorship)
visitor tracking tool - analytics
website <-> google plus profile - authorship so no one steals your content

# off page seo
site promotion

relying on other people
back links - link building
networking with your industry

## settings up category pages


# meta data for each page 
<head>	
	...
	<meta name="keywords" content="kitchen remodelling">
	<meta name="description" content="best planners">
	...
</head>
<body>
...
</body>

# define what is on the web page and what the searcher wants to more specifically find

# content attribute

<meta name="keywords" content="BAltimore kitchen remodelling">
<meta name="googlebot" content="index,follow">
<meta name="Revisit-After" content="7 days"> //crawl every 7 days

follow - follow links
nofollow - dont follow links e.g. affliate marketing
index - index the page
noodp - don't use tag

# checklist
accessibility
	reach all pages without 4,5,3 errors

keyword tagging
	keyword targeting - search vol, relevance, difficulty

content quality - does it answer my query?


link building
	throwing a link at external websites


social accounts
	facebook, linkedin, twitter, google+

seo tools
	seo audits
	spyfu
	wordtracker
	keywordspy.com

# seo goals
keyword research


# data highlighter

# check google webmaster for recommendations

# seo info
marketingterms.com
google seo guidelines

# dynamic url contains ? (get request)
complicated one's cause crawlability problems like this `HTTP://WWW.YOURDOMAIN.COM/PAGE.SRC?
ID=3456&XID=9765487&CID=333394445&VID=34521456&SESSION=875694875`

this is better `HTTP://WWW.YOURDOMAIN.COM/PAGE.SRC?ID=3456`

# dynamic code on pages
output dynamically cause code bloat - js causing dramatic content change from the original content

## robots.txt (find robottxt.org resources)
	User-agent:*
	Disallow:/
	
	will block all bots, crawlers, spiders from accessing

## bad xml sitemap
	list of urls to search for
	not replacement for on site navigation
	
## seo spamming 
	check googlewebmastercentral.blogspot

## google reconsideration request
