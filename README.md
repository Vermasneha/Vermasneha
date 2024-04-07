  ### Hello World!  <img src="https://github.com/sciencepal/sciencepal/blob/master/assets/Hi.gif" width="29px">
  ![](https://komarev.com/ghpvc/?username=sciencepal&label=Profile%20Visits&color=blue&style=for-the-badge)
  
<img src="https://github.com/sciencepal/sciencepal/blob/master/assets/life_balance.gif" alt="side Image" align="right" width="200" height="auto" />
<a href="https://ko-fi.com/sciencepal"> <img src="https://media3.giphy.com/media/ZEB6yFbLnhyQf7g3hn/giphy.gif" alt="side Gif" align="right" width="150" height="auto"/> </a>
  
  - 🔭 I’m currently Pursuing B.Tech in Electronics And Communication
  - 🌱 I’m currently learning Machine Learning 
  - 😄 Pronouns: She/Her

  
  #### 📫 How to reach me:
  
 [<img src="https://github.com/sciencepal/sciencepal/blob/master/assets/discord-round.svg" width="3.5%"/>](https://discord.gg/MnUUbHe)  &nbsp; [<img src="https://img.icons8.com/color/48/000000/twitter.png" width="3.5%"/>](https://twitter.com/sciencepal)  &nbsp; [<img src="https://img.icons8.com/color/48/000000/linkedin.png" width="3.5%"/>](https://www.linkedin.com/in/adityapal1/)  &nbsp; [<img src="https://img.icons8.com/fluent/48/000000/facebook-new.png" width="3.5%"/>](https://www.facebook.com/aditya.pal23/)  &nbsp; [<img src="https://img.icons8.com/fluent/48/000000/instagram-new.png" width="3.5%"/>](https://www.instagram.com/aditya.pal23/)  &nbsp; <a href="mailto:aditya.pal.science@gmail.com"> <img src="https://img.icons8.com/fluent/48/000000/gmail.png" width="3.5%"/>
  
  #### 👨🏻‍💻 Languages and Tools <br />
  <code><img height="40" src="https://raw.githubusercontent.com/github/explore/80688e429a7d4ef2fca1e82350fe8e3517d3494d/topics/cpp/cpp.png"></code>
  <code><img height="40" src="https://raw.githubusercontent.com/github/explore/80688e429a7d4ef2fca1e82350fe8e3517d3494d/topics/python/python.png"></code>
  <code><img height="40" src="https://raw.githubusercontent.com/github/explore/80688e429a7d4ef2fca1e82350fe8e3517d3494d/topics/django/django.png"></code>
  <code><img height="40" src="https://raw.githubusercontent.com/github/explore/80688e429a7d4ef2fca1e82350fe8e3517d3494d/topics/java/java.png"></code>
  <code><img height="40" src="https://raw.githubusercontent.com/github/explore/80688e429a7d4ef2fca1e82350fe8e3517d3494d/topics/docker/docker.png"></code>
  <code><img height="40" src="https://raw.githubusercontent.com/github/explore/80688e429a7d4ef2fca1e82350fe8e3517d3494d/topics/git/git.png"></code>
  <code><img height="40" src="https://raw.githubusercontent.com/github/explore/80688e429a7d4ef2fca1e82350fe8e3517d3494d/topics/jupyter-notebook/jupyter-notebook.png"></code>
  <code><img height="40" src="https://raw.githubusercontent.com/github/explore/80688e429a7d4ef2fca1e82350fe8e3517d3494d/topics/linux/linux.png"></code>

  
 [![Stats](https://github-readme-stats.vercel.app/api?username=sciencepal&show_icons=true&theme=radical)](https://github-readme-stats.vercel.app/api?username=Vermasneha&show_icons=true&theme=radical) &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; <img src="https://github.com/Vermasneha
/
README.md
/Vermasneha
/
README.md
/blob/master/assets/saved.gif" width="195">
  
  [![trophy](https://github-profile-trophy.vercel.app/?username=sciencepal&theme=juicyfresh&no-frame=true&row=1&&margin-w=20&no-bg=true)](https://github-profile-trophy.vercel.app/?username=sciencepal&theme=juicyfresh&no-frame=true&row=1&&margin-w=20&no-bg=true)
  

  name: Generate snake animation

on:
  schedule: # execute every 12 hours
    - cron: "* */12 * * *"

  workflow_dispatch:

  push:
    branches:
    - master

jobs:
  generate:
    permissions:
      contents: write
    runs-on: ubuntu-latest
    timeout-minutes: 5

    steps:
      - name: generate snake.svg
        uses: Platane/snk/svg-only@v3
        with:
          github_user_name: ${{ github.repository_owner }}
          outputs: dist/snake.svg?palette=github-dark


      - name: push snake.svg to the output branch
        uses: crazy-max/ghaction-github-pages@v3.1.0
        with:
          target_branch: output
          build_dir: dist
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
