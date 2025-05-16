# Git-workflow
This is a Gitflow Workflow repo


# Create and Update Each HTML File (One commit each)
# ------------------------------------

# ---  Create and Update index.html ---

git checkout develop
git checkout -b feature/update-index
# create HTML file and src folder
mkdir src
touch src/index.html
# Add full HTML content to src/index.html
git add src/index.html
git commit -m "Add HTML structure to index.html"
git push -u origin feature/update-index

# ---  Create and Update login.html ---
git checkout develop
git checkout -b feature/update-login
# create HTML file
touch src/login.html
# Add HTML to src/login.html
git add src/login.html
git commit -m "Add HTML structure to login.html"
git push -u origin feature/update-login

# ---  Create and Update signup.html ---
git checkout develop
git checkout -b feature/update-signup
# create HTML file
touch src/signup.html
# Add HTML to src/signup.html
git add src/signup.html
git commit -m "Add HTML structure to signup.html"
git push -u origin feature/update-signup

# ------------------------------------
# Merge All Features into develop via Pull Requests
# (Use GitHub UI: base = develop, compare = feature/*)



# Create Release Branch and Merge to Main
# ------------------------------------

git checkout develop
git checkout -b release/v1.0
git push -u origin release/v1.0

# Merge release into main
git checkout main
git merge release/v1.0
git push origin main

# Merge release back into develop
git checkout develop
git merge release/v1.0
git push origin develop
