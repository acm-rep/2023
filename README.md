# ACM REP 2023 Conference website

## Repository structure

Most markdown for the content of the website is in `/content`. Each webpage has its own directory. Each of these directories contain a single `index.md` that determins whether the webpage's content is based on a single markdown file (the body of `index.md`) or is assembled from a series of "widgets" that are specified by seperate markdown files in the same directory. The order of widgets as they will appear on the rendered webpage is specified by `weight:` in the frontmatter of each of these files. Widgets can be hidden by setting `active: false` in its frontmatter.

Images and movies can be included using html within the body of each page or included by setting attributes specific to a particular widget. With some exceptions, images are stored in `/assets/media`. For instructions on how to reference media, see [here](https://wowchemy.com/docs/content/writing-markdown-latex/#images).

## The special meanings of main and gh-pages branches

Everything that is pushed or merged with the `main` branch will automatically trigger a workflow that will render the page using the `gh-pages` branch. The only purpose of `gh-pages` is for that workflow to function. If you are interested, the workflow is specified in `.github/workflows/gh-pages.yml`. **Please do not push to either of these branches directly, and please do not issue a pull request to the `gh-pages` branch.**

## Editing the website

**For small edits** just edit the relevant markdown file directly on github. It is safer to create a pull request than to commit directly to main since a pull request will determine conflicts without interrupting other progress. 

**For larger edits** there are two possibilities: 
1. **Using a local git repository (recommended):** 
    - Clone the repository, 
    - Perform edits -- I highly recommend using Visual Studio Code for editing and common git commands. It does a great job showing all files in the repository and their git status. Make sure to create a repository in a _local_ directory that is not backed by Google Drive, iCloud, or any other file sharing service. Bad things tend to happen if you do, and 
    - [Install hugo](https://wowchemy.com/docs/getting-started/install-hugo-extended/#prerequisites) (skip "Download a Template") and [view your site](https://wowchemy.com/docs/getting-started/install-hugo-extended/#view-your-site) locally using `hugo server` (it quickly rebuilds the local view whenever you save a change). 
    - Create a pull request against the `main` branch of the origin `acm-rep/2023` repository.
    
2. **Using the github website:** fork the repository, perform the edits there and create a pull request against this repository. Unfortunately, I have not figured out how to get the web page render correctly in a forked repository.