The idea behind this project is as follows:

I wanted to create a wedding website for myself.  Somewhere where information about my wedding is easily accessible and guests can RSVP directly through it.  I also wanted to be able to easily recreate the website for other couples.

This meant that I needed a way to recreate the front end of the website and an easy way to edit key pieces of information for each couple.

This project utilizes the following technologies to accomplish this:

Sanity
Sanity is a Content Management System (CMS).  Things like the couples' names, wedding date, photos, guest information, etc. can be stored on Sanity's managed system.  This information can then be easily accessed onto the website using API calls.  Different data sets can be created for different couples.  This makes duplicating the front end simpler, as you only need to edit the API calls to create a customized website.

The information being submitted to Sanity can be managed by the couples themselves or any developers involved.  This is done through a Sanity server container (Dockerfile.sanityserver) living on an AWS EC2 instance.  The server can be accessed anywhere using a browser.  Couples' data is protected from others through a login system.

Using a CMS makes it significantly easier to customize each website for a couple.  No more hard-coding things like names, dates, pictures, etc.  It even makes it easier for couples to edit information themselves, without having to contact a developer to do it for them. 

Github actions and Terraform:
Upon committing code, github actions automatically updates the docker containers being used to serve Sanity and the individual wedding sites.

This part is stil under construction so don't ask me exactly how it works