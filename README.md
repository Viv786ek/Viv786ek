# Hi there, I'm Vivek 👋

## I'm a Problem Solver Enthusiast !
<h3><a id="user-content-profile-views-" class="anchor" aria-hidden="true" href="#profile-views-"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>Profile Views :<br></h3>


<img src="https://camo.githubusercontent.com/c2344f891c785dfe7ecbc4c76afcf80f0f5112955acc4761e6016fb1165a25f3/68747470733a2f2f70726f66696c652d636f756e7465722e676c697463682e6d652f736872616e6e796f626173752f636f756e742e737667" data-canonical-src="https://profile-counter.glitch.me/Viv786ek/count.svg" style="max-width:100%;">


- 🔭 I’m currently working on Problem Solving!
- 🌱 I’m currently learning everything. 🤣
- 👯 I’m looking to collaborate with other developer
- 🤔 I’m looking for help with Problem Solving
- 💬 Ask me about CP
- ⚡ Fun fact: I love to solve problem
- <a href="https://www.buymeacoffee.com/TuOmwckVD" target="_blank"><img src="https://cdn.buymeacoffee.com/buttons/v2/default-yellow.png" alt="Buy Me A Coffee" style="height: 15px !important;width: 70 !important;" ></a>

<a href="https://www.linkedin.com/in/Viv786ek/" target="_blank"><h2>Endorse me on </h2><img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQ6152iVjc8GnvG9pp0adVl2wwgYFsidHAI0g&usqp=CAU" alt="LinkedIn"  style="height: 25 !important;width: 75px !important ;" > </a>

<br />

### Languages and Tools:

<img align="left" alt="Visual Studio Code" width="26px" src="https://raw.githubusercontent.com/github/explore/80688e429a7d4ef2fca1e82350fe8e3517d3494d/topics/visual-studio-code/visual-studio-code.png" />
<img align="left" alt="HTML5" width="26px" src="https://raw.githubusercontent.com/github/explore/80688e429a7d4ef2fca1e82350fe8e3517d3494d/topics/html/html.png" />
<img align="left" alt="CSS3" width="26px" src="https://raw.githubusercontent.com/github/explore/80688e429a7d4ef2fca1e82350fe8e3517d3494d/topics/css/css.png" />

<img align="left" alt="JavaScript" width="26px" src="https://raw.githubusercontent.com/github/explore/80688e429a7d4ef2fca1e82350fe8e3517d3494d/topics/javascript/javascript.png" />

<img align="left" alt="SQL" width="26px" src="https://raw.githubusercontent.com/github/explore/80688e429a7d4ef2fca1e82350fe8e3517d3494d/topics/sql/sql.png" />
<img align="left" alt="MySQL" width="26px" src="https://raw.githubusercontent.com/github/explore/80688e429a7d4ef2fca1e82350fe8e3517d3494d/topics/mysql/mysql.png" />

<img align="left" alt="GitHub" width="26px" src="https://raw.githubusercontent.com/github/explore/78df643247d429f6cc873026c0622819ad797942/topics/github/github.png" />

<br />
<br />


<img src="https://github-readme-stats.vercel.app/api?username=viv786ek&&show_icons=true&title_color=ffffff&icon_color=bb2acf&text_color=daf7dc&bg_color=151515">

[twitter]: https://twitter.com/VivekKu04263472
[instagram]: https://instagram.com/Viv786ek
[linkedin]: https://www.linkedin.com/in/viv786ek/


# GitHub Action for generating a contribution graph with a snake eating your contributions.

name: Generate Snake

# Controls when the action will run. This action runs every 6 hours.

on:
  schedule:
    # every 6 hours
    - cron: "0 */6 * * *"

  # This command allows us to run the Action automatically from the Actions tab.
  workflow_dispatch:

# The sequence of runs in this workflow:
jobs:
  # This workflow contains a single job called "build"
  build:
    # The type of runner that the job will run on
    runs-on: ubuntu-latest

    # Steps represent a sequence of tasks that will be executed as part of the job
    steps:
      # Checks repo under $GITHUB_WORKSHOP, so your job can access it
      - uses: actions/checkout@v2

      # Generates the snake
      - uses: Platane/snk@master
        id: snake-gif
        with:
          github_user_name: ishikkkkaaaa
          # these next 2 lines generate the files on a branch called "output". This keeps the main branch from cluttering up.
          gif_out_path: dist/github-contribution-grid-snake.gif
          svg_out_path: dist/github-contribution-grid-snake.svg

      # show the status of the build. Makes it easier for debugging (if there's any issues).
      - run: git status

      # Push the changes
      - name: Push changes
        uses: ad-m/github-push-action@master
        with:
          github_token: ${{ secrets.GITHUB_TOKEN }}
          branch: master
          force: true

      - uses: crazy-max/ghaction-github-pages@v2.1.3
        with:
          # the output branch we mentioned above
          target_branch: output
          build_dir: dist
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}

