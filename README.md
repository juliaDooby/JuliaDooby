

---
<h3 align="center">◣◥◣◥◤◢◤◢◣◥◣◥◤◢◤◢</h3> 

<h3 align="center">Dear Sir or Madam !</h3> 
<h3 align="center"><a href="https://git.io/typing-svg"><img src="https://readme-typing-svg.herokuapp.com?font=Fira+Code&size=18&duration=4500&pause=1005&color=22EBF7&center=true&vCenter=true&multiline=true&width=474&lines=Nice+to+meet+you+on+my+Github+page+!" alt="Typing SVG" /></a></h3> 
 <h3 align="center">Here You can find samples of my work.<a href="https://daniilshat.ru/" target="_blank"></a></h3>  
<!-- <img src="https://github.com/blackcater/blackcater/raw/main/images/Hi.gif" height="32"/></h2> -->

<h3 align="center">My name is Julia M., I'm a Frontend Web developer since 2021 .</h3>

<!-- ### Dear Sir or Madam !,
### Nice to meet you on my Github page, here You can find samples of my work.  
### My name is Julia M., I'm a Frontend Web developer since 2021 . -->

---
◣◥◣◥◤◢◤◢◣◥◣◥◤◢◤◢

 #### ◉ My hard skills: 

* HTML5, CSS, SCSS
* JavaScript--ES6
* TypeScript
* React
* Git
* Webpack
* Jquery
* GSAP
* Bootstrap
* Material UI
* BEM methodology
* Airbnb()style
* English - B2

---
◣◥◣◥◤◢◤◢◣◥◣◥◤◢◤◢

If you require any further information, you will find it in my CV or feel free to contact me.

Telegram : ( 8-963-788-27-32 )

Email : ( juliadooby@yandex.ru )


---
◣◥◣◥◤◢◤◢◣◥◣◥◤◢◤◢

 Thank you in advance for taking the time to review my resume, for your kind cooperation, for your action in this regard.

 Best regards,
 Yours Faithfully,
 Julia
  ❖
  
name: generate animation

on:
  # run automatically every 12 hours
  schedule:
    - cron: "0 */12 * * *" 
  
  # allows to manually run the job at any time
  workflow_dispatch:
  
  # run on every push on the master branch
  push:
    branches:
    - master
    
  

jobs:
  generate:
    runs-on: ubuntu-latest
    timeout-minutes: 10
    
    steps:
      # generates a snake game from a github user (<github_user_name>) contributions graph, output a svg animation at <svg_out_path>
      - name: generate github-contribution-grid-snake.svg
        uses: JuliaMiroshnichenko/snk/svg-only@v2
        with:
          github_user_name: ${{ github.repository_owner }}
          outputs: |
            dist/github-contribution-grid-snake.svg
            dist/github-contribution-grid-snake-dark.svg?palette=github-dark
    
    
    # push the content of <build_dir> to a branch
      # the content will be available at https://raw.githubusercontent.com/<github_user>/<repository>/<target_branch>/<file> , or as github page
      - name: push github-contribution-grid-snake.svg to the output branch
        uses: crazy-max/ghaction-github-pages@v3.1.0
        with:
          target_branch: output
          build_dir: dist
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
