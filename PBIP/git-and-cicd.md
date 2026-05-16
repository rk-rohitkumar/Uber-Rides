# PBIP, Git, and CI/CD

PBIP is designed to integrate with Git, Azure DevOps, and Fabric CI/CD workflows for collaborative Power BI development.[file:137]

## Git-friendly characteristics

- Report and semantic model definitions are text-based with published schemas.[file:137]
- PBIR and TMDL split content into many small files, improving diff quality and merge conflict resolution.[file:137]
- The `.gitignore` created when saving as PBIP excludes cache and local settings, such as `cache.abf` and `localSettings.json`.[file:137]

## Local Git and VS Code

- Microsoft shows using VS Code to initialize a repo in a PBIP folder, commit changes, and track DAX or metadata edits as Git diffs.[file:137]
- Changing a measure and saving the project produces diffs in `model.bim` or corresponding TMDL files.[file:137]
- Git graph or similar extensions help visualize branch history and PBIP evolution.[file:137]

## Azure DevOps integration

- PBIP projects can be pushed to Azure DevOps repos to collaborate via branches and pull requests.[file:137]
- Fabric workspaces can connect to Azure DevOps Git repos, enabling end‑to‑end CI between Desktop, Git, and Fabric.[file:137]
- Azure DevOps pipelines can run best-practice checks on semantic models and reports using tools like Tabular Editor BPA and PBI Inspector.[file:137]
- Branch policies can block merging to `main` until pipelines succeed, enforcing quality gates.[file:137]

## Fabric Git integration and fabric‑cicd

- Fabric Git Integration exports workspace items (semantic models, reports) into PBIP folder structures in Git.[file:137]
- The `fabric-cicd` library is a Microsoft-backed open-source Python tool for deploying PBIP files from source control to Fabric workspaces.[file:137]
- `fabric-cicd` supports parameterization (e.g., swapping workspace IDs and lakehouse IDs per environment) via a YAML file.[file:137]
- CI/CD examples include Azure Pipelines and GitHub Actions that deploy PBIP to dev/prod workspaces when specific branches are updated.[file:137]

## Guidance for automations and agents

- Generate small, reviewable changes in PBIR/TMDL files to keep diffs clean.[file:137]
- Respect `.gitignore` and avoid emitting cache or machine-specific files.[file:137]
- Distinguish between three deployment modes when advising users: Desktop Publish, Git-driven deployments, and API/`fabric-cicd` deployments.[file:137]