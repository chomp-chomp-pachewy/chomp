# Chomp Chomp Recipes

> Baking is the materialization of comfort itself.

A beautiful, minimalist recipe collection and storytelling platform dedicated to the art and philosophy of baking.

🌐 **Live Site**: [chomp.be](https://chomp.be)

---

## 📖 About

Chomp Chomp is more than just a recipe site—it's a collection of recipes, stories, rituals, meditations, observations, and zen. Our philosophy: **Baking is both personal and communal. To bake is to be.**

### Key Features

- 🍰 **Recipe Collection**: Curated baking recipes with detailed instructions and metadata
- 📝 **Stories & Meditations**: Thoughtful essays about baking, food, and life
- 🔍 **Smart Search**: Filter by category, dish type, time, and ingredients
- 🌓 **Dark Mode**: Automatic dark mode support (Espresso theme)
- 📱 **Fully Responsive**: Beautiful on desktop, tablet, and mobile
- 🔥 **Real-time Updates**: Firebase-powered live data sync
- ✍️ **Content Management**: Decap CMS integration for easy editing

---

## 🛠 Technology Stack

### Frontend
- **HTML5/CSS3/JavaScript** - Pure vanilla JavaScript (ES6 modules)
- **Firebase SDK** - Real-time database and storage
- **Custom CSS** - No frameworks, fully custom responsive design

### Backend & Data
- **Firebase Firestore** - NoSQL database for recipes and posts
- **Firebase Storage** - Image hosting and management
- **Firebase Auth** - User authentication (optional)

### Content Management
- **Decap CMS** - Git-based CMS for content editing
- **Auth0** - Authentication for CMS access

### Fonts
- **Inter** - Primary typeface (300, 400, 500, 600 weights)
- **Source Sans 3** - Fallback font

---

## 🎨 Design System

### Color Palette

**Light Mode**
```
Background:  #fdfdfd
Text:        #353535
Accent:      #e73b42 (signature red)
Sidebar:     #f5f5f5
Borders:     #e0e0e0
```

**Dark Mode (Espresso)**
```
Background:  #231f1f
Text:        #d9d4d4
Accent:      #ff6b7a (lighter red)
Sidebar:     #2b2626
Borders:     #3b3636
```

### Typography
- Base font size: 16px
- Line height: 1.7
- Headings: 600 weight
- Mobile breakpoint: 768px

---

## 📁 Project Structure

```
/
├── index.html              # Homepage with featured content
├── recipes.html            # All recipes grid view
├── recipe.html             # Individual recipe detail page
├── stories.html            # All stories grid view
├── post.html               # Individual story detail page
├── about.html              # About page
├── styles.css              # Main stylesheet
├── CLAUDE.md               # AI assistant guide (detailed docs)
├── README.md               # This file
├── CNAME                   # Custom domain configuration
├── .gitignore              # Git ignore rules
├── admin/
│   ├── index.html          # Decap CMS entry point
│   ├── config.yml          # CMS configuration
│   ├── post-editor.html    # Custom post editor
│   └── recipe-editor.html  # Custom recipe editor
├── tools/                  # Utility tools pages
│   ├── index.html          # Tools homepage
│   ├── ip.html             # Whois lookup
│   ├── convert.html        # Unit converter
│   ├── encode.html         # Base64 encoder/decoder
│   ├── subnet.html         # Subnet calculator
│   ├── inferno.html        # Inferno ipsum generator
│   ├── nautical.html       # Nautical ipsum generator
│   └── css/
│       └── tools-recipes-style.css
└── images/                 # Recipe and site images
```

---

## 🚀 Getting Started

### Prerequisites
- Modern web browser (Chrome, Firefox, Safari, Edge)
- Text editor (VS Code, Sublime, etc.)
- Git (for version control)

### Local Development

1. **Clone the repository**
   ```bash
   git clone https://github.com/chomp-chomp-pachewy/chomp.git
   cd chomp
   ```

2. **Open in browser**
   ```bash
   # Simply open index.html in your browser
   open index.html  # macOS
   xdg-open index.html  # Linux
   start index.html  # Windows
   ```

   Or use a local server:
   ```bash
   # Python 3
   python -m http.server 8000

   # Node.js
   npx serve
   ```

3. **Access the site**
   ```
   http://localhost:8000
   ```

### Firebase Configuration

The Firebase configuration is already set up in the code with public read-only credentials. No additional setup needed for viewing recipes and stories.

---

## 📝 Content Management

### Using Decap CMS

1. Navigate to `/admin` on the live site
2. Authenticate with Auth0
3. Create/edit recipes and stories
4. Changes are committed directly to the repository

### Manual Editing

You can also edit content directly in Firebase Console:
- **Recipes**: `artifacts/chomp-chomp-recipes/public/data/recipes`
- **Posts**: `artifacts/chomp-chomp-recipes/public/data/posts`

---

## 🍪 Recipe Data Structure

```javascript
{
  title: string,           // Recipe name
  slug: string,            // URL-friendly identifier
  description: string,     // Brief description (Markdown supported)
  image: string,           // Image URL or path
  dishType: string,        // Auto-assigned or manual
  category: string,        // e.g., "chomp chomp", "rituals"
  servings: string,        // e.g., "8-10 servings"
  prepTime: string,        // e.g., "20min"
  cookTime: string,        // e.g., "65-80 minutes"
  totalTime: string,       // e.g., "1h 45min"
  ingredients: array,      // List of ingredients
  instructions: array,     // Step-by-step instructions
  notes: string,           // Additional notes (Markdown)
  source: string|object    // Recipe source or credit
}
```

### Dish Types (Auto-assigned)
- Dessert/Pastry
- Cookie/Bar
- Frozen Dessert
- Pudding/Cream
- Main Dish
- Soup
- Other Baked Goods

---

## 📚 Post/Story Data Structure

```javascript
{
  title: string,           // Story title
  slug: string,            // URL-friendly identifier
  content: string,         // Full content (Markdown)
  excerpt: string,         // Brief summary
  featured_image: string,  // Hero image URL
  category: string,        // "rituals", "anthropologies", "zen"
  author: string,          // Author name
  date: string,            // ISO date string
  status: string           // "published" or "draft"
}
```

---

## 🎯 Key Features Explained

### Smart Search & Filtering
- Search by recipe title, description, or ingredients
- Filter by category and dish type
- Sort by: Alphabetical, Newest, Quickest Time
- Real-time results (no page refresh needed)

### Markdown Support
The site supports markdown in:
- Recipe descriptions
- Ingredient lists (including headers for sections)
- Instruction steps (including headers)
- Recipe notes
- Story content

**Supported Markdown:**
- Headers: `#`, `##`, `###`
- Bold: `**text**`
- Italic: `*text*`
- Links: `[text](url)`

### Dark Mode
Automatic dark mode detection using CSS:
```css
@media (prefers-color-scheme: dark) {
  /* Dark mode styles */
}
```

Features:
- Espresso color palette
- Image color transformations on tools pages
- Red hamburger menu icon in dark mode
- All pages fully dark mode compatible

### Responsive Design
- Desktop: Full navigation with dropdowns
- Mobile: Single column with hamburger menu
- Tablet: Optimized layouts
- Print: Clean, printer-friendly styles

---

## 🧭 Navigation Structure

### Main Menu
- **Home** - Featured recipe and story
- **Stories** - Blog posts and meditations
- **Recipes** - Recipe collection
- **About** - Philosophy and contact

### Submenus

**Ipsum**
- Inferno - Dante-inspired lorem ipsum
- Nautical - Maritime lorem ipsum

**Tools**
- Whois - IP lookup
- Convert - Unit converter
- Encode - Base64 encoder/decoder
- Subnet - Subnet calculator

---

## 🔧 Development Tips

### Testing Changes

**Checklist before committing:**
- [ ] Test on desktop (>768px width)
- [ ] Test on mobile (≤768px width)
- [ ] Test dark mode
- [ ] Test print view
- [ ] Check all navigation links
- [ ] Verify Firebase connection
- [ ] Check browser console for errors
- [ ] Test search/filter functionality

### Common Tasks

**Adding a new recipe:**
1. Use Decap CMS at `/admin`, OR
2. Add directly to Firebase Firestore, OR
3. Use the recipe editor (if you have credentials)

**Updating styles:**
1. Edit `styles.css` for main pages
2. Edit `tools/css/tools-recipes-style.css` for tools pages
3. Test dark mode changes

**Adding images:**
1. Upload to `/images` directory (for local), OR
2. Upload to Firebase Storage (for CDN)
3. Reference in recipe/post data

---

## 🌐 Deployment

The site is deployed via GitHub Pages:

1. Push changes to the repository
2. Changes are automatically deployed
3. Custom domain configured via CNAME file

**Custom Domain**: chomp.be

---

## 📄 Page-Specific Notes

### index.html
- Features random recipe and latest story
- Two-column landing page layout
- Intro section with philosophy text

### recipes.html
- Grid view with all recipes
- Pagination (15 recipes per page)
- Advanced filtering and sorting
- Dish type and time displayed on cards

### recipe.html
- Single recipe detail view
- Metadata order: Type → Times → Servings → Category → Source
- Ingredients with red accent bars
- Numbered instruction steps

### stories.html
- Grid view with all published stories
- Category filtering
- Date sorting

### post.html
- Single story detail view
- Full markdown rendering
- Author and date metadata

### about.html
- Information about Chomp Chomp
- Philosophy and mission
- Contact information

---

## 🛡 Security Notes

- Firebase config uses public read-only credentials
- No sensitive data in client-side code
- Firestore security rules enforce read-only access
- Admin files with credentials are gitignored
- CMS access requires Auth0 authentication

### Gitignored Files
```
recipe-admin*.html    # Contains Firebase admin credentials
.env                  # Environment variables
.env.local           # Local environment overrides
```

---

## 🤝 Contributing

This is a personal project, but if you'd like to contribute:

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Test thoroughly
5. Submit a pull request

### Code Style Guidelines

- Use vanilla JavaScript (no frameworks)
- Follow existing naming conventions
- Add comments for complex logic
- Keep functions small and focused
- Test responsive design changes
- Ensure dark mode compatibility

---

## 📞 Contact

- **Email**: [hi@chomp.be](mailto:hi@chomp.be)
- **Website**: [chomp.be](https://chomp.be)
- **Related**: [chomp.ltd](https://www.chomp.ltd) (cookies, etc.)
- **Tools**: [chomp.be/tools](https://chomp.be/tools)

---

## 🐛 Troubleshooting

### Common Issues

**Recipes not loading:**
- Check Firebase config (projectId, apiKey)
- Verify Firestore collection path
- Check browser console for errors
- Ensure internet connectivity

**Images not displaying:**
- Verify image path format (local vs. Firebase Storage)
- Check image exists in `/images` directory
- Verify Firebase Storage CORS settings
- Check image URL format in data

**Search/filter not working:**
- Verify `recipes` array is populated
- Check filter state in browser
- Ensure event listeners are attached
- Check for JavaScript errors in console

**Mobile layout broken:**
- Check viewport meta tag
- Verify media query breakpoint (768px)
- Test sidebar display logic
- Check floating icon positioning

**Dark mode not working:**
- Verify browser supports `prefers-color-scheme`
- Check dark mode CSS rules
- Test in different browsers
- Verify color values are correct

**Dish type not showing:**
- Check if `dishType` field exists in Firestore
- Verify `assignDishType()` function is working
- Check browser console for errors
- Ensure data is loading from Firebase

---

## 📋 Resources

### Documentation
- **CLAUDE.md** - Comprehensive technical documentation for AI assistants
- **Decap CMS Docs** - [decapcms.org/docs](https://decapcms.org/docs)
- **Firebase Docs** - [firebase.google.com/docs](https://firebase.google.com/docs)

### External Resources
- [Markdown Guide](https://www.markdownguide.org/)
- [CSS Variables Guide](https://developer.mozilla.org/en-US/docs/Web/CSS/Using_CSS_custom_properties)
- [Firebase Firestore Guide](https://firebase.google.com/docs/firestore)

---

## 🎁 Special Features

### Recipe Cards
- Display dish type on bottom left (in red)
- Display time on bottom right
- Clickable cards navigate to full recipe
- Responsive grid layout

### Homepage Featured Content
- Random featured recipe
- Latest published story
- Two-column layout on desktop
- Single column on mobile

### Tools Section
- IP/Whois lookup
- Unit converter (length, weight, temperature)
- Base64 encoder/decoder
- Subnet calculator
- Lorem ipsum generators (Inferno, Nautical)

### Dark Mode Enhancements
- Image color transformation (invert + hue rotation)
- Red hamburger menu icon
- Adjusted accent colors
- Consistent across all pages

---

## 📈 Performance Considerations

1. **Firebase Listeners**: Only one real-time listener per collection
2. **Pagination**: Grid view loads 15 recipes at a time
3. **Image Loading**: Lazy load images for better performance
4. **CSS**: All styles inline or in single files (minimal requests)
5. **JavaScript**: Single module bundles (no code splitting needed)

---

## 🔮 Future Enhancements

Potential features to consider:

1. **Recipe Rating System** (infrastructure present, currently commented out)
2. **User Accounts** (Firebase Auth infrastructure available)
3. **Recipe Collections/Favorites** (requires user auth)
4. **Social Sharing** (Open Graph tags already present)
5. **Recipe Comments/Reviews**
6. **Advanced Search** (by ingredient exclusion, dietary restrictions)
7. **Unit Conversion** (metric/imperial toggle)
8. **Recipe Scaling** (adjust serving sizes)
9. **Print Recipes** (enhanced print styles)
10. **Newsletter Integration**

---

## 📜 License

© 2025 Chomp Chomp. All rights reserved.

---

## 🙏 Acknowledgments

Built with love, flour, and Firebase.

Special thanks to:
- The baking community for inspiration
- Firebase for reliable infrastructure
- Decap CMS for git-based content management
- Everyone who shares their recipes and stories

---

## ✨ Philosophy

> "Baking is both personal and communal. To bake is to be. Chomp Chomp bakes. You are here: chomp.be"

This site is more than code and content—it's a meditation on the ritual of baking, the joy of sharing, and the comfort of creating something with your hands. Every recipe tells a story. Every story is an invitation to slow down, savor, and be present.

---

**Last Updated**: December 2025
**Version**: 2.0
**Repository**: [github.com/chomp-chomp-pachewy/chomp](https://github.com/chomp-chomp-pachewy/chomp)
