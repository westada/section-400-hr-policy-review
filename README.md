# Board Documents - *Experimental*

This repository is an alternative approach to Board document management using open-source based tools.  **It should not be considered official**.  The official board management software for the West Ada School District can be found [here](https://simbli.eboardsolutions.com/index.aspx?S=36031062).

## Tools
This approach uses the following tools:

-[Markdown](https://www.markdownguide.org)

-[Github](https://www.github.com/westada)

-[MkDocs](https://www.mkdocs.org)

Here is a brief explanation each tool’s function:

### Markdown
Typically we write files using proprietary software such as Microsoft Word.  Formatting such as Bold, Italic, Underling, Titles, etc., are put into place by selecting text and clicking buttons.  The software then translates those button clicks into what we want to see, which is saved in the file as a set of internal instructions only available to that particular software.  

In contrast, Markdown is just plain text.  There are no “secret” instructions unique to that software program.  Instead, Markdown is a set of simple conventions that are well-known by other computers, software and intuitively readable by humans.  Generally speaking, a person totally unfamiliar with Markdown itself should be able to read the content of a Markdown file and not only process the words themselves, but also intuitively understand formatting context such as bold, italics, sections, etc. 

For instance, when we want to emphasis a word, we surround it in asterisks.  This accomplishes two things:

1. When reading in plain text, humans know that the word `*asterisks*` has added emphasis without needing to see the italics themselves.  
2. Computers also know what this means and so if we wanted to print it, save it as a PDF, render into a webpage, etc., then it removes the asterisks and presents the worked *asterisks* with italics (or bold, underline, etc.) accordingly.

Markdown can do most everything a proprietary software like Word can do, including headings, bullet lists, tables, equations, images, etc., in any text editor application.  Moreover, there are a variety of applications that produce Markdown using all the same buttons and keystrokes to which a user has become accustomed.

> To see this in action, try [Dillinger](https://dillinger.io), which is a free Markdown editor that is entirely online. Other popular desktop and mobile applications include [Obsidian](https://obsidian.md), [Typora](https://typora.io), [IA Writer](https://ia.net/writer) -- or simply search online for “Markdown Editor” and try them all.  


#### Style Guide
When writing the policies in Markdown, please use the following conventions:

- Every policy should have its own file.  A file is equivalent to a Word document, but is written in plain text and ends with `.md`. 

- When creating files, always start with the policy number, using leading and trailing zeros for the (e.g., 401.1 should written as 0401.20).  Then, follow with the title of the policy joined by dashes, replacing any special characters like ampersands with the corresponding word. There should be no spaces in the filename.  For example, “Policy 401.1 Contracts & Supplemental Contracts” should have the file name of `0401.10-Contracts-and-Supplemental-Contracts.md`.

- Be sure each file is located in the proper directory (ie, file folder) corresponding to the section for that policy.  For example, Policy 0401.02 should be filed in the `0400-Staff` folder.

	Also please note that the policies themselves are found in the `docs/policies/` directory in the root of the repo.  Also in `docs` is and `img` folder (used for things like our logo) and `meetings` and `regulations`, which are there for potential future use corresponding to our meeting agendas and ARs, respectively.

- The contents of the file should start file meta-data (ie, data about the file itself rather than the core text of the file.)  This is typically called “Front-Matter”, and is denoted by various descriptors each on their own line, followed by a colon, and then the specific meta data itself, all placed between between two sets of three-dashes.  

	Here is an example of a front matter from policy 0410.01:
	
	```
	---
	created: 2007-05-08
	updated: 2012-03-13
	reviewed: 2012-03-13
	legal: Code of Idaho 33-1201 thru 33-1210, 33-513
	---
	```
	
	Again, most of this should be intuitive, but this means that the policy was created on May 8, 2007, was last updated and reviewed on March 13, 2012, and references the corresponding Legal codes.  
	
	The useful thing about Front-Matter is that it can be used to store important information about the policy that people can read and access without being part of the file itself.  

	Not all of these categories will be present in every file, and some of the legal references will require cleanup.  We may also add and remove front-matter categories as time goes on. 

- Following the front-matter, the official title should be the first line of the policy, with a title header.  In markdown, a Title Header is connoted by preceding the line of text with a single hash (#) mark, and written in Title Case.  The title should be the only line of the file using a single hash.

	For example, the title line of 0401.10 is written as:

	```
	# 0401.10 Contracts and Supplemental Contracts
	```

- After the main title, create sections and sub-sections by writing a single line of text, preferably in Title Case, preceded by two hash-marks `## Section Title`.  Subsections under that can use three hash marks `### Sub-Section Title`.  You can continue this pattern as far as necessary.   

	Effective sectioning is good for organization in general, but in Markdown it has the extra advantage of allowing for auto-creation of tables of contents so that users can easily find what they’re looking for in the file.  

- Paragraphs of text should be soft-wrapped; meaning, they should not have a carriage return in the middle of a paragraph.  Most editors will do this for you automatically.  

- Lists are created by using specific marks and indentation.  Lists take two forms, unordered and ordered.  

	Unordered list can use either `-`, `*`, or `+` marks at the start of each line, followed by a carriage return.  For example, 
	
	```
	- Item One
	- Item Two
	- Item Three
	```

	If you then wish create a nested list, you denote this through indentation.  For example:
	
	```
	- Item One
		- Sub-Item A
		- Sub-Item B
	- Item Two
	```

	Ordered lists work in much the same way, but instead of a tick mark it uses a `1.` at the beginning of each line.
	
	```
	1. Item One
	1. Item Two
	1. Item Three
	```

	This can be a bit confusing at first, but when presenting the list the computer will know to re-number it 1, 2, 3 accordingly.  This allows you to easily re-order a list without having to change the underlying text.
	
	That said, if you wish you may also number them more intuitively, as follows:
	
	```
	1. Item One
	2. Item Two
	3. Item Three
	```

	And the computer will do the same thing.
	
	> Note, the computer will always re-number the list according to what’s presented, regardless of the number itself.  So a list that is numbered 1., 4., 3., will still be presented as 1., 2., 3., in the final product.

	Please note that for nesting of ordered lists, you need to use the same `1.` convention -- it’s the indentation that matters, not the leading number or letter.  For instance:
	
		```
		1. Item One
			1. Sub-Item A
			2. Sub-Item B
		2. Item Two
		```
	
	will do what you want, while:
	
		```
		1. Item One
			a. Sub-Item A
			b. Sub-Item B
		2. Item Two
		```
	
	will not.  
	
	In general, use unordered lists (ie, with just tick marks) unless a specific order is required.  	
- When creating links, denote the linked text by using square brackets with the link itself following inside parenthesis.  It is important there be no spaces between the last bracket and the first parenthesis to ensure the link is properly formatted.  For example, `[West Ada Home Page](https://www.westada.org)` 


- Footnotes can be added by using square brackets `[ ]`, with a caret `^` followed by a shorthand reference.  The footnote mark can then be placed immediately after the text you wish footnoted, with the reference itself at the bottom of the file.  For example:

	```
	Markdown is very useful[^1]
	
	...rest of file...
	
	
	[^1] At least, this is what Dave thinks.  We'll see.
	```

	This will then create all of the footnotes automatically, wherever they appear, and can be reused throughout the file.  
	
	I anticipate we’ll use footnotes mostly for legal and external references, particularly Idaho Code and IDAPA Regulations.  Given that they’ll be so common, we should use `ic-<chapter>-<section>` and `idapa-<section>` as a convention.  For example, from Policy 0200.10:
	
	
	```
	Accordingly, the West Ada School District is granted authority in Idaho Statute to operate as a body politic per section 33-301, Idaho Code[^ic-33-301], and will be governed by a Board of Trustees per section 33-501, Idaho Code.[^ic-33-501]
	```
	
	With the footnotes at the bottom formatted as:
	
	```
	[^ic-33-301]: [Idaho Code 33-301](https://legislature.idaho.gov/statutesrules/idstat/title33/t33ch3/sect33-301/)
	[^ic-33-501]: [Idaho Code 33-501]( https://legislature.idaho.gov/statutesrules/idstat/title33/t33ch5/sect33-501/)
	```
	
	You’ll notice that you can format the footnotes themselves with links, that allow an easy way to get access to the source of the citation.  In general, anytime we reference a specific Idaho Statute we should footnote and link it in the policy itself for easy access.
	
These style conventions should suffice for most of the policies; as we get into more complex things like tables I’ll provide further assistance.
	


### Github

GitHub is a service that hosts open-source distributed version control software.  Version Control is just like it sounds: it tracks changes in files through time, and keeps a record of each version for future use.  It was developed to help manage computer code, which is its primary use-case today, but can manage any files that are text-based.

When we make duplicates of Word files and then send those edits via email with one person accepting or modifying those changes, we are effectively doing version control.  However, using this approach means that we have to do a lot of manual processing with a great deal of mental juggling on whose edits should be accepted, and where, and when -- along with the additional challenges of software incpompatibilies.

In contrast, GitHub was designed specifically to track and manage changes in files in distribution systems, with a number of tools and automations that simplifies -- to the extent possible -- a fundamentally complex process.  GitHub works best with plain text files, which is why using Markdown is important; it opens up version control tools that are otherwise inaccessible to proprietary software approaches like Word or Simbli.

#### GitHub Core Features

GitHub's Version Control can handle very complex situations comprising multiple systems built by large teams distributed over wide geographies and languages.  This is great in that it will handle nearly every situation in which we're likely to find ourselves; the downside is that it can be overwhelming when all you're expecting to use is a fraction of that power.

GitHub organizes like content into logical groupings called “repositories”, or repos for short.  Permissions are tied to repos; so, for instance, one person can have full privileges, while another might only be able to read what’s what’s in a repo but not make contributions.  For our purposes we will have one repo (“policies”) within the main West Ada organization.

We'll focus on four main concepts when using GitHub:

1. Branching
1. Commits
1. Pull Requests
1. Merging

#### Branching

Branching is equivalent to duplicating Word files.  When you create a branch, you are making a copy of the original file, which you then own and can make edits to.  The main branch -- sometimes referred to as the “trunk”, is what is considered the “official” file, equivalent to what the Board has approved and is currently in force at the District.  Multiple people can work on the same branch at the same time, or have multiple branches.  These branches can also be copied locally (ie, to a person’s computer) either in part or in whole, and can be updated to GitHub (called “pushing”) or updated from GitHub (called “pulling”) at any time.

The power of GitHub resides in its ability to manage the state and changes between these branches automatically.  We’ll revisit this later when we get into the fourth concept of ‘merging’.

#### Commits

Commits are equivalent to saving Word files.  More precisely, it’s like a “Save As”, with each save representing a particular version of the document at that time.  Commits can be made to any branch at any time; every commit is saved forever, and can include meta-data about the commit itself (such as side-discussions or notes about what was changed in that particular commit.)

Commits allow us to go back into time to correct errors, to see what we were thinking at a particular moment, or to see the evolution of a policy document, etc.  All commits have unique identifiers, and so this allows us to see the entire history of everything at any moment, and is a very powerful feature of GitHub.

It’s worth noting that you can save the files without making official commits.  This allows users to see what changes were made before making it official through a commit.  That’s why commits are more precisely thought of as a “Save As” in the GitHub system rather than strictly saving.  But the main difference is that commits don’t actually create new files; they are just a milepost marker for that point in time.  The files -- or in this case, the policies themselves -- remain in place until and unless they are rescinded.  And on that topic, even deleted files are not truly deleted; there still is a record of them in GitHub, and can be viewed or restored at anytime, even if they are no longer officially part of the “main” branch.

#### Pull Requests

Pull Requests are equivalent to sending an email with an attached Word file and saying “can we add this text to the policy?”  As mentioned before, when we update files to GitHub that is called a “push”, and when we update files from GitHub that is called a “pull”.  In this case, a Pull Request takes a group of changes from a particular branch and bundles them together as a specific request for the main branch to be updated from GitHub -- to pull -- with those changes.

Specifically, what happens is that we take a particular Commit -- which again represents the files at a specific moment in time -- and ask every one to approve/reject those specific changes.  You can add specific checks such as mandatory reviews from particular people, or computerized checks like spelling, or more complicated checks that “passes an Artificial Intelligence for legality”, etc.

We can manage multiple Pull Requests at a time, with multiple checks as we choose.  Once these checks pass, the Pull Request is ready for merging, which is the last step in the workflow.

#### Merging

Merging is the equivalent of doing all the final editing in a single Word document, saving the results, and printing it out as the final version.  It can be as simple as accepting the final file in one swipe, or as complicating as reconciling differences word-by-word.

Once a pull request is merged, it becomes part of the main trunk -- along with all of the commits, edits, notes, changes, history, etc. -- and the branch itself effectively ceases to exist.

GitHub provides many tools to help ease the merging process, including presenting clear and precise “diffs” (the differences between the file versions) from the main branch, prior versions of the edited commits, or anything at any point in the history of the policies.  However, the merging process itself is still manual: a human being must decide what is OK to include and what is not.

In computer code, this typically is a project manager of some type who is ultimate responsible for what gets in to the main branch.  In our world, this is Board when it decides to approve a policy revision.  So for us, the workflow will be for Niki to review all Pull Requests and ensure they are ready for the Agenda, then posted, then voted on and, if approved, then merged into the main branch where they become official policy.

When this happens, the final step is to publish the results, for which we use the final tool: MkDocs.

### MkDocs

MkDocs is an open-source Static-Site Generator, or SSG.  This is a tool that takes the plain-text files written in Markdown syntax and converts them into HTML, or the language of websites.  It then allows these converted files to be uploaded to the internet where they can be served to the public at large.  There are a wide-variety of SSGs available for free; I choose MkDocs because it is written in Python, the language with which I am most familiar.

As the name might imply, MkDocs is tailored towards documentation, which is the closest proxy to our policies that I can envision.  It provides a clean, easy-to-understand interface and allows for rapid searching and easy formatting.

MkDocs takes the files that are committed to the GitHub main branch and renders a website from them automatically.  Specifically, merging a pull request into the main branch triggers a set of scripts that updates the website to those changes in roughly a minute or so.

In addition to the policies, other pages can be written in Markdown and committed to GitHub directly.  So, for instance, if we wanted to create a Home Page for the Board, or sub-pages with Bios, contact forms, etc., all of this can be done simply by writing files in plain text and committing them to the main branch in GitHub.  This can include tables, images, PDF files -- basically anything that is included on a web page can be included using Markdown and GitHub, rendered using MkDocs.

In terms of flow, there is not much to do on our side.  Once the scripts are in place, everything is automated.  It only requires someone to ensure everything is working and to fix anything that happens to break along the way.

SSGs also do some of the heavy-lifting on aspects like site-security, internationalization, and accessibility.  MkDocs specifically adheres to the [Web Content Accessibility Guidelines](https://en.wikipedia.org/wiki/Web_Content_Accessibility_Guidelines) Version 2, standard AA -- which is the standard to which public school district websites are held.

## Workflow

With all of the tools in place, this is how our workflow should proceed.

### GitHub Accounts

Everyone should sign up for a (free) GitHub account, and send that information to either Niki or Dave B.  One of them will add you to both the “West Ada Organization” as general members, and then specifically add you to the “Policies” repo where the text itself will reside.  You’ll be assigned specific privileges which may change, but assume for the time being that most will be able to read and write to all policies.

### Making Edits

It is assumed that either Niki or Amy will start the process by editing a specific file with the individual edits needed.  When doing so, there is no need to do things like making copies or doing strikethrough; just overwrite what is there with the new text.  The system will then allow you to see the changes (the “diffs”) in a variety of formats to understand what you’ve done is what you want.

When the edits are where you want, you commit these changes, which saves it in time.  This then provides you with the opportunity to create a branch or commit your comments to the main directly.

In almost all cases we will want to create a new branch with the edits.  I say almost because sometimes it may make sense to make direct edits to main without creating a branch.  For instance, right now I am taking the files imported from Simbli and converting them into Markdown syntax via the style guide. I can also see a situation where Amy makes updates to the Legal References in the Front-Matter section of the file.

Basically, direct edits to the main trunk should be reserved for changes to meta-data (such as formatting and front-matter) rather than the policy body itself.  Again, everything is tracked and can be undone so there isn’t any real risk here; the point is that the body text of the policy shouldn’t officially change until and unless approved by the Board in open session, even for things like typos.

Most edits will be committed to a new branch, which ideally should be a single-branch per file.  There may be cases where multiple files depend on one another (such as moving set from one policy to another) but in general -- and certainly in the beginning -- simpler is better.

When committing the branch you can add comments (called a ‘commit message’).  These comments can provide useful context, most typically a description of the changes made and why.  You can also use this to do @mentions with particular members of the Organization, so that people can be made aware that changes are in process.  (Think of this as the email that you send with an attached document, and the mentions are those you cc to the email.)

### Making Pull Requests

While changes can be merged into the main branch at any time, the typical way for this happen is through a Pull Request.  For our flow, the way to think about this is that the Pull Request means that it’s ready to be considered for a First Reading.

Pull Requests are a bit different in that they allow for a specific review and check process; for example, say we have a policy edit that affects finance.  Niki could make the changes and after preliminary discussion create a Pull Request requesting approval from Dave R. (for finance), Amy White (for legal), and Dave B./Rene O. (For trustees).  We are then able to provide any generalized comments, approve, or reject with requests for changes.  This is all tracked and we can each provide our own recommended language, which Niki is then able to consolidate into a revised Pull Request.

Once we get everyone’s approval on any revisions, the Pull Request “passes all checks” and is ready for a Board Reading.  If any changes are made during the reading they can be made on the Pull Request itself, and Niki can either restart the approval process or simply make the changes directly.  Each time, we can change the label of the PR to reflect the status:  First, Second, Third Reading, etc, or put into any other state we choose.

### Merging into Main

When presenting to the Board, we can use the various “diff views” to show the changes made, either from original/last-edit, or both.  These will be a bit of a manual process in the near term since we work off of PDFs, but it is not unreasonable for me to imagine literally pulling up the GitHub repo to show everything to the Board in realtime.  This would have the advantage of incorporating all changes, including last minute changes, automatically with no chance of showing old files.

Regardless, assuming the Board Approves after a third reading, Niki then simply Merges the Pull Request into main, and the process is complete:  the website automatically updates, and the branch on which the edits are made is deleted.  Again, it’s not unreasonable for me to envision Sarah literally pressing that merge button on completion of a vote, with the Board vote itself in the merge commit message.  Overkill, perhaps, but a nerd can dream...


## Summary

With these three tools (Markdown, GitHub and MkDocs) we can replace all our current functionality using a better, more comprehensive workflow, include rich history, and do more with the resulting content than we currently do.  It will require some changes in how we write the policies and think about the flow, but overall will be in a much better position for ourselves, the administration and our patrons.

Oh, and did I mention all of these tools are free?  :-)
