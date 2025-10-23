# 👋 Hi, I'm saimter!

![Typing SVG](https://readme-typing-svg.herokuapp.com/?lines=Welcome+to+my+GitHub+Profile!;Full+Stack+Developer;React+%26+Unity+Enthusiast;Always+learning+new+things&font=Fira%20Code&center=true&width=800&height=50&color=61DAFB)

<div align="center">
    <img src="https://media.giphy.com/media/L1R1tvI9svkIWwpVYr/giphy.gif" width="400" />
</div>

## 🛠️ Tech Stack

### Frontend
![React](https://img.shields.io/badge/React-20232A?style=for-the-badge&logo=react&logoColor=61DAFB)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)
![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white)

### Game Development
![Unity](https://img.shields.io/badge/Unity-100000?style=for-the-badge&logo=unity&logoColor=white)
![C#](https://img.shields.io/badge/C%23-239120?style=for-the-badge&logo=c-sharp&logoColor=white)

### Tools & Others
![Git](https://img.shields.io/badge/Git-F05032?style=for-the-badge&logo=git&logoColor=white)
![GitHub](https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white)
![VS Code](https://img.shields.io/badge/VS_Code-0078D4?style=for-the-badge&logo=visual%20studio%20code&logoColor=white)

## 📊 GitHub Stats

<div align="center">
    <img src="https://github-readme-stats.vercel.app/api?username=saimter&show_icons=true&theme=tokyonight&include_all_commits=true&count_private=true" />
    <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=saimter&layout=compact&theme=tokyonight" />
</div>

<div align="center">
    <img src="https://github-readme-streak-stats.herokuapp.com/?user=saimter&theme=tokyonight" />
</div>

## 🏆 GitHub Trophies
<div align="center">
    <img src="https://github-profile-trophy.vercel.app/?username=saimter&theme=onedark&column=7" />
</div>

## 🚀 Featured Projects

<div align="center">

    [![K-Village](https://github-readme-stats.vercel.app/api/pin/?username=saimter&repo=react_k_village&theme=tokyonight)](https://github.com/saimter/react_k_village)

</div>

## 📈 Activity Graph
![Activity Graph](https://github-readme-activity-graph.vercel.app/graph?username=saimter&theme=tokyo-night)

## 📫 Connect with me

<div align="center">

    [![GitHub](https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white)](https://github.com/saimter)
    [![Email](https://img.shields.io/badge/Email-D14836?style=for-the-badge&logo=gmail&logoColor=white)](mailto:your-email@example.com)

</div>

<div align="center">

    ### 🎯 "Always coding, always learning, always growing!"

    ![Visitor Count](https://profile-counter.glitch.me/saimter/count.svg)

</div>

name: Generate snake animation

on:
  schedule:
    - cron: "0 */6 * * *" # 6시간마다 실행
  workflow_dispatch:

jobs:
  generate:
    runs-on: ubuntu-latest
    timeout-minutes: 10

    steps:
      - name: generate snake.svg
        uses: Platane/snk/svg-only@v2
        with:
          github_user_name: saimter
          outputs: dist/snake.svg

      - name: push snake.svg to the output branch
        uses: crazy-max/ghaction-github-pages@v2.6.0
        with:
          target_branch: output
          build_dir: dist
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
