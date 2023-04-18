# Generate public key 
 
Go to home directory

>`cd ~`

>`cd .ssh`

Create key

>`ssh-keygen -t ed25519 -C "your_email@example.com"`

>`ssh-keygen -t ed25519 -C "dlozada77@gmail.com"`

Enter a file name `<key_name>`

Enter a passphrase (password) `...`

`ssh-add -K <key_name>`

`ssh-add -l`

# Create main branch and upload updates

>`git init`

>`git add README.md`

>`git commit -m "first commit"`

>`git branch -M main`

>`git remote add origin git@github.com:kaskasmeister/training.git`

>`git push -u origin main`

# Clone Repo

>`git clone git@github.com:kaskasmeister/training.git`

# Create a Branch

1. create branch

>`git checkout -b <branch_name>`

2. do your changes
3. add changes to be commit

>`git add .`

4. commit changes

>`git commit -m "<task number> message"`

5. send the changes

>`git push origin <branch_name>`

6. update branch with main, 1x per day

>`* be on your branch <branch_name>`

>`git pull origin main`

7. send changes get from main update

>`git push origin <branch_name>`

8. Etc

> `git pull origin feature/CC-15077-user-account-merge`
 
  before run 
  
> `git push origin feature/CC-15077-user-account-merge`

Lo que tienes que hacer es ir a main





# Cherry-pick
Go to main and Create a new branch

>`git cherry-pick d74052a0a39410b3b185342b8c385a12bbc6590d`

>`git cherry-pick 306f8064bc8e87a2b6e6c6265efb66da3f72d5df`

>`git cherry-pick 98aeaefbd58fbe665c37477dc23d3384daa3412a`