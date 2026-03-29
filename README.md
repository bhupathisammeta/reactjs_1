# React CI/CD Project

A React application with automated CI/CD pipeline using GitHub Actions.

## Features

✅ **Continuous Integration**
- Automated builds on push and pull requests
- Multi-version Node.js testing (16.x, 18.x)
- Automated testing and linting

✅ **Code Quality**
- Security vulnerability scanning
- Code quality checks
- SonarQube integration (optional)

✅ **Continuous Deployment**
- Automated deployment to GitHub Pages
- Slack notifications
- Production build optimization

## Project Structure

```
├── .github/
│   └── workflows/           # GitHub Actions workflows
│       ├── ci-cd.yml       # Main CI/CD pipeline
│       ├── code-quality.yml # Code quality checks
│       └── deploy.yml      # Production deployment
├── public/
│   └── index.html          # HTML template
├── src/
│   ├── App.js              # Main React component
│   ├── App.css             # App styles
│   ├── App.test.js         # App tests
│   ├── index.js            # App entry point
│   ├── index.css           # Global styles
│   └── reportWebVitals.js  # Performance monitoring
├── package.json            # Project dependencies
├── .gitignore             # Git ignore rules
└── README.md              # This file
```

## Setup & Installation

### Prerequisites
- Node.js (v16.x or higher)
- npm or yarn
- Git

### Local Development

1. **Clone the repository**
```bash
git clone https://github.com/yourusername/react-cicd-project.git
cd react-cicd-project
```

2. **Install dependencies**
```bash
npm install
```

3. **Start development server**
```bash
npm start
```
Open [http://localhost:3000](http://localhost:3000) to view it in the browser.

4. **Run tests**
```bash
npm test
```

5. **Build for production**
```bash
npm run build
```

## GitHub Actions Workflows

### 1. CI/CD Pipeline (`ci-cd.yml`)
- **Trigger**: Push to `main`/`develop`, Pull Requests
- **Jobs**:
  - Install dependencies
  - Run tests
  - Build project
  - Upload artifacts
  - Optional SonarQube scan

### 2. Code Quality (`code-quality.yml`)
- **Trigger**: Push to `main`/`develop`, Pull Requests
- **Jobs**:
  - Code linting
  - Security audit
  - Coverage reports

### 3. Deploy (`deploy.yml`)
- **Trigger**: Push to `main`, Manual trigger
- **Jobs**:
  - Build project
  - Deploy to GitHub Pages
  - Slack notification

## Configuration

### Environment Variables
Create a `.env.local` file for local development:
```
REACT_APP_API_URL=http://localhost:3000
```

### GitHub Secrets
Add these secrets to your GitHub repository for CI/CD:

```
SONAR_HOST_URL      # SonarQube host URL
SONAR_TOKEN         # SonarQube token
SLACK_WEBHOOK_URL   # Slack webhook for notifications
```

To add secrets:
1. Go to Repository Settings → Secrets and variables → Actions
2. Click "New repository secret"
3. Add each secret with its value

## Deployment

The project automatically deploys to GitHub Pages when changes are pushed to the `main` branch.

**To enable GitHub Pages:**
1. Go to Repository Settings → Pages
2. Set Source to "Deploy from a branch"
3. Select `gh-pages` branch
4. Update the `cname` in `.github/workflows/deploy.yml` with your custom domain (optional)

## Available Scripts

| Command | Description |
|---------|-------------|
| `npm start` | Run development server |
| `npm test` | Run test suite |
| `npm run build` | Build production bundle |
| `npm run eject` | Eject from Create React App (irreversible) |
| `npm run lint` | Run linter (if configured) |

## Troubleshooting

### Build fails
- Clear node_modules: `rm -rf node_modules && npm install`
- Update npm: `npm install -g npm@latest`

### Tests fail locally but pass in CI
- Check Node.js version: `node --version`
- Ensure all dependencies are installed: `npm ci`

### Deployment not working
- Verify GitHub Pages is enabled in Settings
- Check workflow logs: Actions tab → Recent workflow runs
- Ensure `GITHUB_TOKEN` secret is properly configured

## Continuous Integration Benefits

✅ **Automated Testing** - Every commit is tested automatically
✅ **Code Quality** - Standards enforced before merge
✅ **Consistent Builds** - Same environment for all developers
✅ **Faster Feedback** - Developers know issues immediately
✅ **Automatic Deployment** - Less manual work in production

## Best Practices

1. **Branch Protection** - Require status checks to pass before merging
2. **Code Review** - Use pull requests for all changes
3. **Commit Messages** - Use meaningful commit messages
4. **Testing** - Write tests for new features
5. **Documentation** - Keep README updated

## Resources

- [React Documentation](https://reactjs.org)
- [GitHub Actions Documentation](https://docs.github.com/actions)
- [Create React App Guide](https://create-react-app.dev)
- [SonarQube for Code Quality](https://www.sonarqube.org)

## License

MIT

## Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

---

**Happy coding! 🚀**
