## [cura build](https://github.com/Ultimaker/cura-build)
## [cura build environment](https://github.com/Ultimaker/cura-build-environment)
```
cd C:\Users\ROKIT\Documents  
git clone https://github.com/Ultimaker/cura-build-environment  
cd cura-build-environment  
docker/windows/Dockerfile.vs2015 파일에서 1809 을 1607로 바꾼다.
docker pull ultimaker/cura-build-environment  
docker build -t cura-build-env -f docker/windows/Dockerfile.vs2015 .

```

## Welcome to GitHub Pages

You can use the [editor on GitHub](https://github.com/mgcha85/cura/edit/gh-pages/index.md) to maintain and preview the content for your website in Markdown files.

Whenever you commit to this repository, GitHub Pages will run [Jekyll](https://jekyllrb.com/) to rebuild the pages in your site, from the content in your Markdown files.

### Markdown

Markdown is a lightweight and easy-to-use syntax for styling your writing. It includes conventions for

```markdown
Syntax highlighted code block

# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```

For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/mgcha85/cura/settings). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://docs.github.com/categories/github-pages-basics/) or [contact support](https://support.github.com/contact) and we’ll help you sort it out.
