# Quick Start Guide

## 🚀 Getting Started with React CI/CD Project

### Step 1: Initialize Git Repository
```bash
cd d:\code\devops\pipeline-cls\reactjs_1
git init
git add .
git commit -m "Initial commit: React project with GitHub Actions CI/CD"
```

### Step 2: Create GitHub Repository
1. Go to [GitHub](https://github.com/new)
2. Create new repository: `react-cicd-project`
3. Copy the repository URL

### Step 3: Push to GitHub
```bash
git remote add origin https://github.com/yourusername/react-cicd-project.git
git branch -M main
git push -u origin main
```

### Step 4: Install Local Dependencies
```bash
npm install
```

### Step 5: Verify Local Setup
```bash
# Start dev server
npm start

# Run tests (in another terminal)
npm test

# Build for production
npm run build
```

### Step 6: Configure GitHub Secrets
1. Go to Github repo → Settings → Secrets and variables → Actions
2. Add secrets:
   - **SLACK_WEBHOOK_URL** (optional): For Slack notifications
   - **SONAR_HOST_URL** (optional): For SonarQube integration
   - **SONAR_TOKEN** (optional): For SonarQube integration

### Step 7: Enable Branch Protection (Recommended)
1. Settings → Branches → Add rule
2. Apply to: `main`
3. ✓ Require PR reviews
4. ✓ Require status checks to pass
5. ✓ Include administrators

### Step 8: Verify CI/CD Works
1. Make a test change
2. Push to a feature branch: `git push origin feature/test`
3. Create a Pull Request on GitHub
4. Watch the Actions tab for workflow runs
5. All checks should pass before merge

## 📁 Project Structure Explained

```
reactjs_1/
├── .github/workflows/        # CI/CD Pipeline Definitions
│   ├── ci-cd.yml            # Main build & test pipeline
│   ├── code-quality.yml      # Code quality checks
│   ├── deploy.yml           # Production deployment
│   └── security.yml         # Security scanning
├── public/                  # Static assets
│   ├── index.html          # HTML template
│   └── logo.svg            # React logo
├── src/                     # React source code
│   ├── App.js              # Main component
│   ├── App.css             # Styling
│   ├── App.test.js         # Component tests
│   ├── index.js            # App entry point
│   ├── index.css           # Global styles
│   └── reportWebVitals.js  # Performance monitoring
├── package.json            # Dependencies & scripts
├── .gitignore             # Git ignore rules
├── .env.example           # Environment variables template
├── sonar-project.properties # SonarQube config
├── README.md              # Full documentation
└── ARCHITECTURE.md        # CI/CD architecture details
```

## 🔄 Development Workflow

### Create Feature Branch
```bash
git checkout -b feature/my-feature
```

### Make Changes
```bash
# Edit files...
npm start  # See changes in browser
npm test   # Run tests
```

### Commit & Push
```bash
git add .
git commit -m "Add my feature"
git push origin feature/my-feature
```

### Create Pull Request
1. Go to GitHub
2. Click "Compare & pull request"
3. Add description
4. Wait for CI/CD to pass ✓
5. Request review
6. Merge when approved

### Merge to Main
```bash
# After PR is approved and merged:
git checkout main
git pull origin main
```

## 📊 CI/CD Workflows Explained

### 1. CI/CD Pipeline (Main)
**Runs on**: Every push to `main`/`develop` + pull requests
**Does**: 
- ✓ Installs dependencies
- ✓ Runs tests
- ✓ Builds the app
- ✓ Uploads build artifacts

### 2. Code Quality Check
**Runs on**: Every push + pull requests
**Does**:
- ✓ Checks code style
- ✓ Audits dependencies
- ✓ Runs coverage reports

### 3. Security Scan
**Runs on**: Weekly + manual trigger
**Does**:
- ✓ Scans for vulnerabilities
- ✓ Checks npm dependencies
- ✓ OWASP compliance check

### 4. Deploy to Production
**Runs on**: Push to `main` only
**Does**:
- ✓ Builds optimized app
- ✓ Deploys to GitHub Pages
- ✓ Sends Slack notification

## 🛠️ Available Commands

| Command | Purpose |
|---------|---------|
| `npm start` | Start development server on localhost:3000 |
| `npm test` | Run test suite |
| `npm run build` | Create production-ready build |
| `npm run lint` | Run code linter (if configured) |
| `npm install` | Install dependencies from package.json |

## 🔑 Key Files to Update

### 1. sonar-project.properties
Update if using SonarQube:
```properties
sonarProjectKey=your-project-key
```

### 2. .github/workflows/deploy.yml
Update GitHub Pages deployment:
```yaml
cname: your-domain.com  # Change to your domain
```

### 3. package.json
Update project name & description:
```json
{
  "name": "your-project-name",
  "description": "Your project description"
}
```

### 4. README.md
Customize for your project:
- Add your repository URL
- Update features
- Add your deployment instructions

## 🚨 Troubleshooting

### Workflow not running?
- ✓ Check GitHub Actions is enabled (Settings → Actions)
- ✓ Verify workflow file syntax (`.github/workflows/*.yml`)
- ✓ Check branch protection settings

### Tests failing in CI?
- ✓ Run `npm test` locally first
- ✓ Check Node version: `node --version`
- ✓ Clear cache: `rm -rf node_modules && npm install`

### Deployment not working?
- ✓ Check GitHub Pages settings (Settings → Pages)
- ✓ Verify build directory exists: `npm run build`
- ✓ Check workflow logs in Actions tab

### Slack notifications not working?
- ✓ Verify `SLACK_WEBHOOK_URL` in GitHub Secrets
- ✓ Check webhook URL is valid
- ✓ Ensure workflow has correct secret name

## 📈 Next Steps

1. **Customize the app**: Edit `src/App.js`
2. **Add components**: Create new `.js` files in `src/`
3. **Add tests**: Create corresponding `.test.js` files
4. **Setup ESLint**: Run `npm install --save-dev eslint`
5. **Add more workflows**: Create new YAML files in `.github/workflows/`
6. **Enable protected branches**: Enforce status checks

## 📚 Documentation Files

- **README.md** - Complete project documentation
- **ARCHITECTURE.md** - CI/CD architecture & workflows
- **QUICKSTART.md** - This file (quick reference)

## 🎉 You're All Set!

Your React project with GitHub Actions CI/CD is ready to use. Start by:

1. Initializing Git
2. Pushing to GitHub
3. Making your first commit
4. Watching the CI/CD pipeline run automatically

Happy coding! 🚀

---

**Questions?** Check:
- [GitHub Actions Docs](https://docs.github.com/actions)
- [React Documentation](https://reactjs.org)
- [ARCHITECTURE.md](./ARCHITECTURE.md) for detailed workflow info
