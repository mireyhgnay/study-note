# <div align="center">๐จ git push :: 'Note about fast-forwards' in 'git push --help' for detail</div>

### ์ค๋ฅ ํ๋ฉด
![pusherror](https://user-images.githubusercontent.com/111990266/209424795-3800ef9f-3701-4a6d-8e72-d8db3f8c0543.png)

### ํด๊ฒฐ ๋ฐฉ๋ฒ
pull ๋ถ๋ช ํ๋ ๊ฒ ๊ฐ์๋ฐ ์ปค๋ฐํธ์ ๊ณผ์ ์์ ์ถฉ๋์ด ๋ฌ๋์ง push๊ฐ ๋์ง์๊ณ  ์ค๋ฅ๊ฐ ๋ฌ๋ค.    
๊ทธ๋์ commit ๋๋๋ฆฌ๊ณ  ๋ค์ pullํ๋ ๋ฐฉ๋ฒ์ผ๋ก ํด๊ฒฐํ๋ค.

```bash
# ๊ฐ์ฅ ์ต๊ทผ์ commit์ ์ทจ์
$ git reset HEAD^
```