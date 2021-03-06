# Assignment 3: Static Website

To deploy a static website using [Hugo](https://gohugo.io) (a static web site generator) and host it on GitHub Project Pages.

This is a group activity. Hence, participation of all group members is mandatory.

## Static web site generator

A static web site generator is an application that takes plain text files and compiles them to HTML files.


### Hugo
![](https://d33wubrfki0l68.cloudfront.net/c38c7334cc3f23585738e40334284fddcaf03d5e/2e17c/images/hugo-logo-wide.svg)

Hugo is a static HTML and CSS website generator written in Go. It is optimized for speed, ease of use, and configurability. Hugo takes a directory with content and templates and renders them into a full HTML website.

Hugo relies on Markdown files with front matter for metadata, and you can run Hugo from any directory. This works well for shared hosts and other systems where you don’t have a privileged account.

Hugo renders a typical website of moderate size in a fraction of a second. A good rule of thumb is that each piece of content renders in around 1 millisecond.

Hugo is designed to work well for any kind of website including blogs, tumbles, and docs.

## Instructions

1. [Install Hugo](https://gohugo.io/getting-started/installing)
2. Create a repository in [GitHub](https://github.com)
   - **repository name**: `static_website`
3. Clone the repository to your computer
   ```
   git clone https://github.com/<USERNAME>/static_website.git
   ```
4. [Create a webiste using Hugo](https://gohugo.io/getting-started/quick-start/)
   - **Website name**: `static_website`
     ```
     hugo new site static_website --force
     ```
   - Add this line `publishDir = "docs"` to the `config.toml` file (set the publish directory)
     ```
     echo 'publishDir = "docs"' >> config.toml
     ```
   - Replace `baseURL` in the `config.toml` file
     ```
     baseURL = "https://<USERNAME>.github.io/<REPOSITORY-NAME>/"
     ```
     - Replace `<USERNAME>` for your actual GitHub username
     - Replace `<REPOSITORY-NAME>` for your repository name
   - After the previous steps, your config file should look like this:
     ```
      baseURL = "https://<USERNAME>.github.io/<REPOSITORY-NAME>/"
      languageCode = "en-us"
      title = "MSIG XXI - My New Hugo Site"
      publishDir = "docs"
     ```
5. Customise your website, for example:
   - Add a theme ([more themes](https://themes.gohugo.io))
     ```
     git submodule add https://github.com/budparr/gohugo-theme-ananke.git themes/ananke
     echo 'theme = "ananke"' >> config.toml
     ```
   - Add posts
     ```
     hugo new posts/my-first-post.md
     ```
   - Create extra sections
   - more...
6. Test your website, start the Hugo server
   - `hugo server -D`
   - Navigate to your new site at http://localhost:1313/
7. Build static pages
   ```
   hugo -D
   ```
8. Commit & Push your changes to the remote directory
   ```
   git add .
   git commit -m "my first website..."
   git pull     # Download any change from other contributors
   git push     # Publish your changes
   ```
9. [Setup GitHub Project Pages](https://gohugo.io/hosting-and-deployment/hosting-on-github/#github-project-pages)
   - Go to **Settings → GitHub Pages**
   - From **Source**, select “master branch /docs folder”. If the option isn’t enabled, you likely do not have a docs/ folder in the root of your project.
   <img width="550" alt="fig_GitHubPages" src="https://user-images.githubusercontent.com/7943442/81508679-bfc99480-9305-11ea-8a25-be0a615d2904.png">
10. Test it
   ```
   https://<USERNAME>.github.io/<REPOSITORY-NAME>/
   ```

### Configuration file

Example of a `config.toml` file:

```toml
   baseURL = "https://<USERNAME>.github.io/<REPOSITORY-NAME>/"
   languageCode = "en-us"
   title = "MSIG XXI - My New Hugo Site"
   theme = "ananke"
   publishDir = "docs"
```

- Replace `<USERNAME>` for your actual GitHub username
- Replace `<REPOSITORY-NAME>` for your repository name
- `publishDir = "docs"` is mandatory to work on GithHub Project pages

## Deliverable

- Link to the **website** and **repository**
- Screenshot of the contributors' activity

## Collaboration

While working on your website, you can post screenshots and your website link on the below issue:

- https://github.com/alopezag/WT-2020I/issues/1

The idea, it is to share your knowledge with others.

If you got any problem/question, you can create a new [issue](https://github.com/alopezag/WT-2020I/issues/) or check in the [current issues](https://github.com/alopezag/WT-2020I/issues/) whether a similar question has been already answered.

- https://github.com/alopezag/WT-2020I/issues/
