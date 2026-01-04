# 📝 Static Blog - Shuvranshu Sekhar Sahoo

A modern, fully static blog built with pure HTML, CSS, and JavaScript. Features inline styling that matches the visual theme of my main portfolio website, with markdown-based blog posts and client-side rendering.

🌐 **Live Demo:** https://sahooshuvranshu.github.io/blog/

---

## ✨ Features

- 🎨 **Discord-Inspired Theme** - Matching the main portfolio design
- 📱 **Fully Responsive** - Works on all devices
- 📝 **Markdown Posts** - Write posts in Markdown with frontmatter
- ⚡ **Client-Side Rendering** - Uses marked.js for fast markdown parsing
- 🚀 **GitHub Pages Ready** - Deploy instantly to GitHub Pages
- 💾 **No Backend Required** - Pure static HTML/CSS/JS
- 🎯 **Zero Dependencies** - Only CDN for marked.js library
- 🖼️ **Beautiful Cards** - Post preview cards with metadata
- 🔍 **SEO Friendly** - Proper meta tags and semantic HTML

---

## 📁 Project Structure

```
blog/
├── index.html              # Blog homepage with post listings
├── post.html               # Individual post viewer
├── posts/                  # Markdown blog posts directory
│   ├── welcome-to-my-blog.md
│   ├── building-modern-web-applications.md
│   └── my-journey-as-developer.md
└── README.md              # This file
```

---

## 🚀 Quick Start

### 1. Clone or Download

```bash
git clone https://github.com/SahooShuvranshu/blog.git
cd blog
```

### 2. Add to GitHub Pages

1. Create a new repository named `blog`
2. Push this code to the repository
3. Go to Settings → Pages
4. Set source to `main` branch
5. Your blog will be live at `https://yourusername.github.io/blog/`

### 3. Local Development

Simply open `index.html` in your browser, or use a local server:

```bash
# Python 3
python -m http.server 8000

# Python 2
python -m SimpleHTTPServer 8000

# Node.js (if you have http-server installed)
npx http-server
```

Visit `http://localhost:8000`

---

## ✍️ Writing Blog Posts

### Create a New Post

1. Create a new `.md` file in the `posts/` directory
2. Add frontmatter with metadata
3. Write your content in Markdown
4. Update the post list in `index.html`

### Frontmatter Format

Every post must start with YAML frontmatter:

```markdown
---
title: Your Post Title
date: 2026-01-04
description: A short description of your post
slug: your-post-slug
---

# Your Content Here

Write your blog post content in Markdown...
```

### Example Post Structure

```markdown
---
title: Getting Started with React
date: 2026-01-05
description: Learn the basics of React and build your first component
slug: getting-started-with-react
---

# Getting Started with React

React is a popular JavaScript library...

## Installation

```bash
npm install react
```

## Your First Component

```javascript
function Hello() {
  return <h1>Hello World!</h1>;
}
```

And more content...
```

### Adding Posts to the Homepage

Edit `index.html` and update the `posts` array:

```javascript
const posts = [
    {
        title: "Your New Post Title",
        date: "2026-01-05",
        description: "Post description here",
        slug: "your-post-slug"
    },
    // ... existing posts
];
```

---

## 🎨 Customization

### Update Colors

The blog uses a Discord-inspired color scheme. Main colors in CSS:

```css
/* Background colors */
--bg-primary: #36393f;
--bg-secondary: #2f3136;
--bg-tertiary: #202225;

/* Text colors */
--text-primary: #ffffff;
--text-secondary: #dcddde;
--text-muted: #72767d;

/* Accent colors */
--accent-primary: #5865f2;
--accent-success: #3ba55c;
--accent-warning: #faa61a;

/* Border colors */
--border-primary: #40444b;
--border-dark: #18191c;
```

### Update Links

Update links to your portfolio and social media:

**In `index.html` and `post.html`:**

```html
<!-- Back button -->
<a href="https://sahooshuvranshu.github.io" class="back-btn">

<!-- Footer links -->
<a href="https://github.com/YourUsername" target="_blank">GitHub</a>
<a href="https://yourwebsite.com">Portfolio</a>
```

### Update Author Name

Replace "Shuvranshu Sekhar Sahoo" with your name in:
- `index.html` - footer section
- `post.html` - footer and author metadata

---

## 📝 Markdown Support

The blog supports full Markdown syntax using [marked.js](https://marked.js.org/):

### Headers
```markdown
# H1 Header
## H2 Header
### H3 Header
```

### Emphasis
```markdown
**bold text**
*italic text*
~~strikethrough~~
```

### Lists
```markdown
- Unordered item 1
- Unordered item 2

1. Ordered item 1
2. Ordered item 2
```

### Code
```markdown
Inline `code` here

```javascript
// Code block
function hello() {
  console.log("Hello!");
}
```
```

### Links & Images
```markdown
[Link text](https://example.com)
![Alt text](image.jpg)
```

### Blockquotes
```markdown
> This is a blockquote
```

### Tables
```markdown
| Header 1 | Header 2 |
|----------|----------|
| Cell 1   | Cell 2   |
```

---

## 🎯 Best Practices

### Writing Posts

1. **Use descriptive titles** - Clear and engaging
2. **Write good descriptions** - They appear in post previews
3. **Use meaningful slugs** - lowercase-with-hyphens
4. **Include dates** - Keep posts chronologically organized
5. **Add code examples** - When relevant
6. **Use headers** - Structure your content well
7. **Proofread** - Check spelling and grammar

### File Naming

- Use lowercase for file names
- Use hyphens instead of spaces: `my-post.md`
- Match slug in frontmatter: `slug: my-post`

### Images

To include images in posts:

1. Create an `images/` directory
2. Add your images there
3. Reference in markdown: `![Alt text](../images/photo.jpg)`

---

## 🛠️ Technical Details

### Dependencies

- **marked.js** (via CDN) - Markdown parsing

```html
<script src="https://cdn.jsdelivr.net/npm/marked@11.1.1/marked.min.js"></script>
```

### How It Works

1. **Homepage (`index.html`)**:
   - Displays a list of blog posts as cards
   - Post metadata is stored in a JavaScript array
   - Clicking a card navigates to `post.html?slug=post-name`

2. **Post Page (`post.html`)**:
   - Reads slug from URL query parameter
   - Fetches the corresponding `.md` file from `/posts/`
   - Parses frontmatter for metadata
   - Converts markdown to HTML using marked.js
   - Displays the rendered content

3. **Markdown Files**:
   - Stored in `/posts/` directory
   - Start with YAML frontmatter
   - Content written in Markdown syntax
   - Parsed on the client side

---

## 🚢 Deployment

### GitHub Pages (Recommended)

1. Create a new repository named `blog`
2. Push this code:
   ```bash
   git init
   git add .
   git commit -m "Initial blog setup"
   git branch -M main
   git remote add origin https://github.com/YourUsername/blog.git
   git push -u origin main
   ```
3. Enable GitHub Pages in repository settings
4. Your blog is live at `https://yourusername.github.io/blog/`

### Netlify

1. Connect your GitHub repository
2. Build command: (leave empty)
3. Publish directory: `/`
4. Deploy!

### Vercel

1. Import your repository
2. Framework preset: Other
3. Build command: (leave empty)
4. Output directory: `./`
5. Deploy!

---

## 🔧 Troubleshooting

### Posts Not Loading

- Check that `.md` files are in the `posts/` directory
- Verify slug in URL matches filename
- Check browser console for errors
- Ensure marked.js CDN is accessible

### Styling Issues

- Clear browser cache
- Check for inline style conflicts
- Verify all CSS is in `<style>` tags

### 404 Errors

- For GitHub Pages, use relative paths
- Check that post files exist
- Verify correct base path in links

---

## 📄 License

This project is open source and available under the MIT License.

---

## 🤝 Contributing

Feel free to fork this project and customize it for your own blog!

Suggestions and improvements are welcome:
1. Fork the repository
2. Create your feature branch
3. Commit your changes
4. Push to the branch
5. Open a pull request

---

## 📧 Contact

**Shuvranshu Sekhar Sahoo**

- Portfolio: [sahooshuvranshu.github.io](https://sahooshuvranshu.github.io)
- GitHub: [@SahooShuvranshu](https://github.com/SahooShuvranshu)
- Blog: [sahooshuvranshu.github.io/blog](https://sahooshuvranshu.github.io/blog)

---

## 🙏 Acknowledgments

- Design inspired by Discord's UI
- Markdown parsing by [marked.js](https://marked.js.org/)
- Background texture from Pinterest

---

## 📝 Adding a New Blog Post - Step by Step

### Step 1: Create the Markdown File

1. Navigate to the `posts/` directory
2. Create a new file: `your-post-name.md`

**File naming rules:**
- Use lowercase letters
- Use hyphens instead of spaces
- Example: `my-awesome-post.md`

### Step 2: Write the Frontmatter

At the top of your file, add frontmatter with metadata:

```markdown
---
title: Your Post Title
date: 2026-01-04
description: A short description (50-150 characters)
slug: your-post-name
---
```

**Important:**
- `slug` must match your filename (without `.md`)
- `date` format: YYYY-MM-DD
- `description` appears in the post preview card

### Step 3: Write Your Content

Write your blog post content using Markdown syntax:

```markdown
# Main Heading

Your introduction paragraph...

## Section Heading

Content here...

### Subsection

More content...
```

### Step 4: Update index.html

Open `index.html` and add your post to the posts array:

```javascript
const posts = [
    {
        title: "Your New Post Title",
        date: "2026-01-04",
        description: "Your post description",
        slug: "your-post-name"
    },
    // ... existing posts below
];
```

**Important:**
- Add new posts at the TOP of the array (newest first)
- Make sure the slug matches your filename

### Step 5: Test Locally

```bash
python -m http.server 8000
```
Then visit: `http://localhost:8000`

### Step 6: Commit and Push

```bash
git add .
git commit -m "Add new post: Your Post Title"
git push origin main
```

Your post will be live on GitHub Pages within a few minutes!

### Quick Checklist

Before publishing:

- [ ] Frontmatter is complete and correct
- [ ] Slug matches filename
- [ ] Post is added to posts array in index.html
- [ ] Content is proofread
- [ ] Code examples work (if any)
- [ ] Links are valid
- [ ] Post displays correctly locally

### Example: Complete Workflow

Create file `posts/my-first-post.md`:

```markdown
---
title: My First Post
date: 2026-01-04
description: This is my very first blog post!
slug: my-first-post
---

# My First Post

Welcome to my first blog post!

## What I'll Write About

I plan to write about:
- Web development
- My coding journey
- Helpful tutorials

Stay tuned for more!
```

Update `index.html`:

```javascript
const posts = [
    {
        title: "My First Post",
        date: "2026-01-04",
        description: "This is my very first blog post!",
        slug: "my-first-post"
    },
    // ... other posts
];
```

Done! 🎉

### Tips for Great Posts

1. **Write engaging titles** - Make people want to read
2. **Use clear structure** - Headers, paragraphs, lists
3. **Add code examples** - When teaching concepts
4. **Include visuals** - Images, diagrams when helpful
5. **Proofread** - Check spelling and grammar
6. **Keep it focused** - One topic per post
7. **Be yourself** - Write in your own voice

---

## 📄 Blog Post Template

Copy this template when creating new posts:

```markdown
---
title: Your Post Title Here
date: 2026-01-04
description: A brief description of what this post is about (appears in the post card preview)
slug: your-post-slug
---

# Main Title

Introduction paragraph goes here. Hook your readers with an engaging opening.

## Section 1

Your content here...

### Subsection

More detailed content...

## Section 2

### Code Examples

You can include code blocks:

```javascript
function example() {
  console.log("Hello, World!");
}
```

```python
def example():
    print("Hello, World!")
```

### Lists

Unordered lists:
- Item 1
- Item 2
- Item 3

Ordered lists:
1. First item
2. Second item
3. Third item

### Links and Images

[Link text](https://example.com)

![Image alt text](path/to/image.jpg)

### Blockquotes

> This is a blockquote. Use it for emphasis or to quote someone.

### Tables

| Column 1 | Column 2 | Column 3 |
|----------|----------|----------|
| Data 1   | Data 2   | Data 3   |
| Data 4   | Data 5   | Data 6   |

## Conclusion

Wrap up your post with a conclusion...

---

*Optional closing remark or call to action*

**Happy coding!** ✨
```

---

**Made with 💜 and ☕ by Shuvranshu Sekhar Sahoo**

*Happy blogging! ✨*