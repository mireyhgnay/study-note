# <div align="center">๐จ pull ์ค๋ฅ :: Not possible to fast-forward, aborting</div>


## ์ค๋ฅ ๋ด์ฉ
`git pull origin <branch Name>`์ ํ๋๋ฐ pull์ด ๋ฐ์์ง์ง ์์๋ค.

์ค๋ฅ ๋ฉ์์ง
```bash
Not possible to fast-forward, aborting
```

## ์ค๋ฅ ์์ธ
git global ์ต์์ pull.ff=only ์ต์์ด ์์๋๋ฐ    
์ด๋ pull์ ๋ฐ์ ๋ ๋ fast-foward ๋ฐฉ์์ผ๋ก ๋ฐ๊ฒ ๋ค๋ ๋ป์ด๋ฉฐ        
์ด ๋ฐฉ์์ผ๋ก ๋ฐ๋๋ค๋ฉด ๋ค๋ฅธ ์ฌ๋์ด ๋์ ๋ค๋ฅธ ๋ธ๋์น๋ฅผ ๋ฐ์ ๋จผ์  develop์ ๋จธ์ง๋ฅผ ํ์ ๋ fast-foward ๊ด๊ณ๊ฐ ํ์ฑ๋์ง ์์ pull์ด ์ค๋จ๋๋ ๊ฒ์ด์๋ค. 

## ์ค๋ฅ ํด๊ฒฐ
* ํด๊ฒฐ1: global ์ต์์ ์์ฐ.    
`git config --unset --global pull.ff`

* ํด๊ฒฐ2:ย `git config --global pull.rebase=true`ย ์ถ๊ฐํ๊ณ  ํฐ๋ฏธ๋ ์ฌ์คํ ํ pull ๋ฐ๊ธฐ

* ํด๊ฒฐ3: ํด๊ฒฐ2๋ฅผ ์งํํ๋๋ฐ ํด๊ฒฐ์ด ์๋๋ค๋ฉดย `git pull --rebase origin <branch name>`๋ก pull ๋ฐ๊ธฐ

---
@reference https://velog.io/@dev_crystal/pull์ด-๋ฐ์์ง์ง-์์๋-์ค๋ฅ