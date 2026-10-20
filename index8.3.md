## Aim
To create a responsive magazine or news-style webpage using CSS Grid and `grid-template-areas`.

## Objectives
1. Create Header, Navigation, Main Article, Sidebar, and Footer sections.
2. Define a CSS Grid container.
3. Use `grid-template-areas` to arrange webpage sections.
4. Assign a named grid area to each section.
5. Give the main article more space than the sidebar.
6. Test different section sizes and alignments for responsiveness.

## 1. Project Structure

Create a folder named `Assignment-8.3` and add these two files:

```text
Assignment-8.3/
├── index.html
└── style.css
```

## 2. HTML Code — `index.html`

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Daily Chronicle | Magazine Layout</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>

    <div class="magazine-layout">

        <!-- Header Section -->
        <header class="header">
            <h1>Daily Chronicle</h1>
            <p>Your Daily Source of News, Ideas and Inspiration</p>
        </header>

        <!-- Navigation Section -->
        <nav class="navigation">
            <a href="#home">Home</a>
            <a href="#technology">Technology</a>
            <a href="#education">Education</a>
            <a href="#business">Business</a>
            <a href="#lifestyle">Lifestyle</a>
        </nav>

        <!-- Main Article Section -->
        <main class="main-article" id="home">
            <img
                src="https://images.unsplash.com/photo-1497366754035-f200968a6e72?auto=format&fit=crop&w=1200&q=80"
                alt="Modern workspace with computers and desks"
            >

            <span class="category">FEATURED STORY</span>

            <h2>How Technology Is Changing the Modern World</h2>

            <p class="article-info">By Editorial Team | October 20, 2026</p>

            <p>
                Technology has become an important part of our everyday lives.
                From online education to artificial intelligence, digital
                innovations are changing the way people learn, work and
                communicate.
            </p>

            <p>
                Students can access learning resources online, businesses can
                connect with customers worldwide, and people can complete
                many everyday tasks using digital tools.
            </p>

            <p>
                As technology continues to develop, digital skills, creativity
                and responsible internet use are becoming increasingly valuable.
                Understanding these changes can help us prepare for the future.
            </p>

            <a class="read-more" href="#latest-news">Read More &rarr;</a>
        </main>

        <!-- Sidebar Section -->
        <aside class="sidebar">
            <h2>Latest News</h2>

            <article class="news-item" id="technology">
                <span class="news-label">TECHNOLOGY</span>
                <h3>Artificial Intelligence in Everyday Life</h3>
                <p>
                    Discover how AI tools are supporting learning,
                    communication and productivity.
                </p>
            </article>

            <article class="news-item" id="education">
                <span class="news-label">EDUCATION</span>
                <h3>Digital Learning for Students</h3>
                <p>
                    Online resources are making educational materials
                    available to more learners.
                </p>
            </article>

            <article class="news-item" id="business">
                <span class="news-label">BUSINESS</span>
                <h3>The Growth of Digital Businesses</h3>
                <p>
                    Digital platforms help businesses reach customers
                    beyond their local markets.
                </p>
            </article>

            <article class="news-item" id="lifestyle">
                <span class="news-label">LIFESTYLE</span>
                <h3>Building Better Digital Habits</h3>
                <p>
                    Balanced screen time and responsible online behaviour
                    can support a healthier digital routine.
                </p>
            </article>
        </aside>

        <!-- Footer Section -->
        <footer class="footer">
            <p>&copy; 2026 Daily Chronicle. All rights reserved.</p>
            <p>Designed using HTML5 and CSS Grid.</p>
        </footer>

    </div>

</body>
</html>
```

## 3. CSS Code — `style.css`

```css
/* Reset default browser spacing */
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

/* General page styling */
body {
    font-family: Arial, Helvetica, sans-serif;
    background-color: #f1f5f9;
    color: #1e293b;
    line-height: 1.7;
    padding: 20px;
}

/* Main CSS Grid container */
.magazine-layout {
    max-width: 1200px;
    margin: 0 auto;
    display: grid;
    grid-template-columns: minmax(0, 2fr) minmax(250px, 1fr);
    grid-template-areas:
        "header header"
        "navigation navigation"
        "main sidebar"
        "footer footer";
    gap: 20px;
}

/* Header grid area */
.header {
    grid-area: header;
    background: linear-gradient(135deg, #0f172a, #1d4ed8);
    color: white;
    text-align: center;
    padding: 35px 20px;
    border-radius: 12px;
}

.header h1 {
    font-size: 2.5rem;
    letter-spacing: 1px;
    margin-bottom: 8px;
}

.header p {
    color: #dbeafe;
    font-size: 1rem;
}

/* Navigation grid area */
.navigation {
    grid-area: navigation;
    background-color: #ffffff;
    display: flex;
    justify-content: center;
    align-items: center;
    flex-wrap: wrap;
    gap: 12px;
    padding: 15px;
    border-radius: 10px;
    box-shadow: 0 3px 12px rgba(15, 23, 42, 0.06);
}

.navigation a {
    color: #1d4ed8;
    text-decoration: none;
    font-weight: bold;
    padding: 8px 14px;
    border-radius: 6px;
    transition: background-color 0.3s, color 0.3s;
}

.navigation a:hover {
    background-color: #1d4ed8;
    color: white;
}

/* Main article grid area */
.main-article {
    grid-area: main;
    background-color: white;
    padding: 25px;
    border-radius: 12px;
    box-shadow: 0 3px 12px rgba(15, 23, 42, 0.06);
    min-width: 0;
}

.main-article img {
    width: 100%;
    height: 320px;
    object-fit: cover;
    display: block;
    border-radius: 8px;
    margin-bottom: 20px;
}

.category {
    display: inline-block;
    background-color: #dbeafe;
    color: #1d4ed8;
    font-size: 0.8rem;
    font-weight: bold;
    padding: 5px 10px;
    border-radius: 5px;
    margin-bottom: 12px;
}

.main-article h2 {
    font-size: 2rem;
    line-height: 1.3;
    margin-bottom: 12px;
    color: #0f172a;
}

.article-info {
    color: #64748b;
    font-size: 0.9rem;
    margin-bottom: 18px;
}

.main-article p {
    margin-bottom: 16px;
}

.read-more {
    display: inline-block;
    margin-top: 5px;
    background-color: #1d4ed8;
    color: white;
    text-decoration: none;
    font-weight: bold;
    padding: 10px 18px;
    border-radius: 6px;
    transition: background-color 0.3s;
}

.read-more:hover {
    background-color: #1e40af;
}

/* Sidebar grid area */
.sidebar {
    grid-area: sidebar;
    background-color: #eaf1ff;
    padding: 22px;
    border-radius: 12px;
    min-width: 0;
}

.sidebar > h2 {
    color: #0f172a;
    font-size: 1.5rem;
    padding-bottom: 12px;
    margin-bottom: 15px;
    border-bottom: 3px solid #1d4ed8;
}

.news-item {
    background-color: white;
    padding: 16px;
    border-radius: 8px;
    margin-bottom: 15px;
    border-left: 4px solid #2563eb;
}

.news-label {
    color: #2563eb;
    font-size: 0.75rem;
    font-weight: bold;
    letter-spacing: 0.5px;
}

.news-item h3 {
    font-size: 1.05rem;
    line-height: 1.4;
    margin: 7px 0;
    color: #0f172a;
}

.news-item p {
    font-size: 0.9rem;
    color: #475569;
}

/* Footer grid area */
.footer {
    grid-area: footer;
    background-color: #0f172a;
    color: #cbd5e1;
    text-align: center;
    padding: 22px;
    border-radius: 10px;
    font-size: 0.9rem;
}

/* Tablet layout */
@media (max-width: 850px) {
    .magazine-layout {
        grid-template-columns: minmax(0, 1.5fr) minmax(220px, 1fr);
        gap: 15px;
    }

    .header h1 {
        font-size: 2.1rem;
    }

    .main-article {
        padding: 18px;
    }

    .main-article h2 {
        font-size: 1.7rem;
    }

    .main-article img {
        height: 250px;
    }

    .sidebar {
        padding: 16px;
    }
}

/* Mobile layout */
@media (max-width: 650px) {
    body {
        padding: 10px;
    }

    .magazine-layout {
        grid-template-columns: 1fr;
        grid-template-areas:
            "header"
            "navigation"
            "main"
            "sidebar"
            "footer";
        gap: 12px;
    }

    .header {
        padding: 25px 15px;
    }

    .header h1 {
        font-size: 1.8rem;
    }

    .header p {
        font-size: 0.9rem;
    }

    .navigation {
        gap: 5px;
        padding: 10px;
    }

    .navigation a {
        padding: 7px 10px;
        font-size: 0.9rem;
    }

    .main-article {
        padding: 16px;
    }

    .main-article img {
        height: 220px;
    }

    .main-article h2 {
        font-size: 1.5rem;
    }

    .sidebar {
        padding: 16px;
    }

    .footer {
        padding: 18px 10px;
    }
}
```

## 4. Explanation of CSS Grid Areas

The main layout uses the following CSS:

```css
.magazine-layout {
    display: grid;
    grid-template-columns: minmax(0, 2fr) minmax(250px, 1fr);
    grid-template-areas:
        "header header"
        "navigation navigation"
        "main sidebar"
        "footer footer";
    gap: 20px;
}
```

Each section is connected to its named grid area:

```css
.header {
    grid-area: header;
}

.navigation {
    grid-area: navigation;
}

.main-article {
    grid-area: main;
}

.sidebar {
    grid-area: sidebar;
}

.footer {
    grid-area: footer;
}
```

### How It Works

- `display: grid` creates the grid layout.
- `grid-template-columns` defines two columns.
- `2fr 1fr` gives the main article approximately twice the flexible width of the sidebar when sufficient space is available.
- `grid-template-areas` defines where each section appears.
- `grid-area` assigns each section to its named location.
- `gap: 20px` creates spacing between sections.
- The media queries change the layout for smaller screens.

On mobile screens, the sections are arranged vertically in this order: Header, Navigation, Main Article, Sidebar and Footer.

## 5. Testing and Output

1. Save both files inside the `Assignment-8.3` folder.
2. Open `index.html` in a web browser, or run it using the VS Code Live Server extension.
3. Check that the header and navigation occupy the full width.
4. Verify that the main article is wider than the sidebar on desktop.
5. Resize the browser to tablet and mobile widths.
6. Confirm that the sidebar moves below the main article on mobile.
7. Check that the text, image and navigation remain readable. An internet connection is required to load the external image.

## 6. Expected Output

The webpage displays a modern magazine-style design with:

- A full-width title header.
- A navigation bar containing category links.
- A large featured article with an image and text.
- A narrower sidebar containing latest-news cards.
- A full-width footer.
- A responsive layout for desktop, tablet and mobile screens.

## 7. Result

The magazine-style webpage was created successfully using HTML5 and CSS Grid. The `grid-template-areas` property was used to arrange the header, navigation, main article, sidebar and footer. Responsive media queries were added to improve the layout on smaller screens.

