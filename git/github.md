# 1. Create Account
    TBD

# 2. SSH keys

## 2.1 generate 

```
ssh-keygen -t rst -C "xxx@xxx.com"
```

## 2.2 upload
get public
```
cd ~/.ssh
cat id_rsa.pub
```
verify
```
ssh -T git@github.com
```

## 2.3 if port 22 is blocked
try
``` 
ssh -T -p 443 git@ssh.github.com
``` 
so, add following to *~/.ssh/config*
``` 
Host github.com
    Hostname ssh.github.com
    Port 443
    User git
```

# 3. Clone Repository
 
```
git clone git@git@github.com:xxx/yyy.git
```

