# Claude Code Workshop Website

## Description
An interactive workshop website designed to teach developers how to use Claude Code, Anthropic's official CLI tool that brings AI-powered coding assistance directly to the terminal. This website serves as the primary resource for workshop attendees to learn about Claude Code's features, capabilities, and best practices.

## Features
- **Responsive Design**: Fully responsive layout that works on all devices
- **AWS Amplify Ready**: Pre-configured for seamless AWS Amplify deployment
- **Workshop Content**: Comprehensive information about Claude Code
- **Clean UI**: Modern, readable design with warm color scheme
- **SPA Support**: Single-page application with proper routing configuration

## Project Structure
```
dalia-claude-code-workshop/
├── index.html          # Main HTML file with workshop content
├── amplify.yml         # AWS Amplify build configuration
├── package.json        # Node.js dependencies and scripts
├── _redirects          # Redirect rules for SPA routing
├── .gitignore          # Git ignore patterns for Node.js/web projects
├── LICENSE             # MIT license file
├── README.md           # Project documentation (this file)
├── assets/             # Static assets directory
│   ├── css/
│   │   └── styles.css  # CSS styling with custom properties
│   ├── js/             # JavaScript files (if needed)
│   └── images/         # Image assets
├── docs/               # Documentation directory
│   ├── CONTRIBUTING.md # Contributing guidelines
│   └── DEPLOYMENT.md   # Deployment instructions
└── .claude/            # Claude Code agent configurations
    └── agents/
        ├── html-css-standards.md     # HTML/CSS standards agent
        └── repo-structure-manager.md # Repository management agent
```

## Installation

### Local Development
1. Clone the repository:
```bash
git clone https://github.com/gamgustavo/dalia-claude-code-workshop.git
cd dalia-claude-code-workshop
```

2. Install dependencies (if needed):
```bash
npm install
```

3. Start the development server:
```bash
# Start local server (recommended)
npm start

# Start with auto-open browser
npm run dev

# Or using alternative methods
# Using Python
python -m http.server 8000

# Using Node.js directly
npx http-server
```

4. Optional - Run code quality checks:
```bash
# Validate HTML
npm test

# Format code
npm run format

# Lint JavaScript
npm run lint
```

### AWS Amplify Deployment
1. Connect your GitHub repository to AWS Amplify
2. Amplify will automatically detect the `amplify.yml` configuration
3. Deploy with default settings - no additional configuration needed

## Usage

### For Workshop Instructors
- Use this website as the main landing page for Claude Code workshops
- Content covers Getting Started, Code Generation, and Advanced Features
- Easily customizable for specific workshop needs

### For Attendees
- Access workshop materials and resources
- Learn about Claude Code capabilities
- Find links to documentation and GitHub repository

## Technologies Used
- **HTML5**: Semantic markup and structure
- **CSS3**: Modern styling with CSS custom properties
- **JavaScript**: Smooth scrolling and mobile navigation
- **AWS Amplify**: Hosting and continuous deployment

## Contributing
Contributions are welcome! Please feel free to submit a Pull Request.

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## License
This project is open source and available under the MIT License.

## Contact
- **Workshop Email**: workshop@claudecode.dev
- **GitHub**: [github.com/anthropics/claude-code](https://github.com/anthropics/claude-code)
- **Documentation**: [docs.anthropic.com/claude-code](https://docs.anthropic.com/claude-code)

## Acknowledgments
- Anthropic for creating Claude Code
- Workshop participants for feedback and suggestions
- Open source community for continuous support

---
*Built with Claude Code - Empowering developers with AI-powered coding assistance*