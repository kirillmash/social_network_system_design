
# Homework
## Social network, System design


### Functional requirements:
- Create and publish posts with images and link to trip
- likes and comments travellers posts
- subscription on other travel users
- search for popular places to travel and view posts from these places in the form of TOP places by country and city
- chatting with travellers in DM
- view feed travellers


### Non-functional requirements:

- 10 000 000 DAU
- availability 99,95%
- only for CIS
- store posts forever
- one user create one post in 5 day
- one user views 15 posts in day
- 2000 symbols for post
- 5 photos for post
- Timings:
    - create post - 1s
    - get posts - 2 s
    - subscribe - 0.5 s

## Basic calculations

RPS (create post):

    DAU = 10 000 000
    Each user creates one post in 5 day
    RPS = 10 000 000 / 5 / 86 400 ~= 20 

RPS (Read post):

    DAU = 10 000 000
    Each user view 15 posts in day
    RPS = 10 000 000 * 15 / 86400 = 1700
    
Traffic (create post):
    images: 20 * 5MB = 100MB/s
    text: 20 * 4KB = 80KB/s

Traffic (read post) 10 post per reading:
    images: 1700 * 5MB * 10 = 80 GB/s
    text: 1700 * 4KB * 10 = 70 MB/s

Required memory:
    images: 100MB/s * 86400 * 365 = 3PB
    text: 80KB/s * 86400 * 365 = 7GB

RPS (create comment):
 1 user write 1 comment daily, 500 symbols per comment
    
    10 000 000 / 86 400 = 115

Traffic (create comment):
    115 * 500 * 2 = 115KB/s

Required memory:
    115 * 86400 * 365 = 4GB

Will use 20 hdd x1TB for posts storage and 170 ssd x20TB for images storage and 1 hdd x 500gb for comments storage