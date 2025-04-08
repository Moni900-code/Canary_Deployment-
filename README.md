# Canary Deployment with GitHub Actions

**Canary Deployment** is a progressive rollout strategy where a new version of an application is gradually released to a small subset of users before making it available to everyone.

This helps in:
- Catching bugs early without impacting all users
- Monitoring stability and performance in real environments
- Enabling safer rollouts with rollback options

Example rollout:
- ✅ Deploy to 10% users
- ✅ Then to 30%
- ✅ Then 100% after success

---

## 🎯 Goal

To simulate a canary deployment using **GitHub Actions** and **custom flags** (via workflow inputs) for controlling the percentage of traffic to the new version.

---

## Tools Used

| Tool        | Purpose                      | Notes                        |
|-------------|------------------------------|------------------------------|
| GitHub Actions | CI/CD pipeline automation  | For deploying via YAML file  |
| Custom Flags | Traffic control by rollout % | Simple & free implementation |

---

## 📁 Project Structure

```bash
Canary_Deployment-/
├── .github/
│   └── workflows/
│       └── canary.yml
└── README.md
```

## Step-by-Step Setup
- Step 1: Create Workflow Directory and canary.yml file: 

```bash
 mkdir .github/workflows
 cd .github/workflows
 touch canary.yml
```

- Step 2: using this command, write necessary content into the canary.yml file:
```bash
 nano canary.yml
```
- Step 3: Push to GitHub
  
```bash
git add .
git commit -m "Added canary deployment workflow"
git push 
```
- Step 4: Run the Workflow from GitHub
     - Go to your GitHub Repository → Actions tab
     - Select Canary Deployment workflow
     - Click Run workflow
     - Enter a percentage: 10, 30, or 100
       
![Alt Text](github_actiontab_rslt.png)

- Step 5: GitHub Actions Output Example
Here’s what you’ll see in the Actions tab log output:

➤ Only 10% of the user traffic is routed to the new version of the app.
![Alt Text](customflag10.png)

➤ Now, 30% of the traffic is moved to the new version, increasing gradually.
![Alt Text](customflag30.png)

➤ All (100%) traffic is routed to the new version. The deployment is now fully live.
![Alt Text](customflag100.png)

Here, Each step shows how the deployment is tested with increasing traffic using a variable ($ROLLOUT) — starting small and ending with full deployment. This is a simulation of canary deployment using custom traffic percentage inputs.

**END** of the projet........

 
