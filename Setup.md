## Repository Setup Instructions

This course repository (located at `https://github.com/Make-School-Courses/CS-1.3-Core-Data-Structures`) contains course materials including the schedule, class topics, lesson plans, challenges, starter code, unit tests, slides, and links to resources.
It will be periodically updated throughout the course, so you will need to regularly *pull* from it to get new materials.
(Note that you cannot *push* to the course repository.)
However, you can *clone* it to create a copy and push code to your own repo.

**Important:**
Please follow these instructions *exactly*. If you skip a step or do them out of order, it may not work correctly or you may not earn credit towards your GitHub commit streak.

### Local Repo
Set up your local clone of this repo on your computer to access course materials and starter code.

1. **Clone** (do not *fork*) the course repo on GitHub onto your local computer.
  - First open your terminal and navigate into the folder where you keep your coursework:
  `cd ~/MakeSchool/Courses` (or something similar for your folders)
  - Then run this command to *clone* the course repo:
  `git clone https://github.com/Make-School-Courses/CS-1.3-Core-Data-Structures.git`
  - Now navigate into the new folder Git just created:
  `cd CS-1.3-Core-Data-Structures`

1. [**Create a new empty repo** on GitHub](https://github.com/new) also named `CS-1.3-Core-Data-Structures` and **do not** initialize it with a ReadMe. (Creating a *new* repo instead of a *fork* allows you to earn credit towards your GitHub commit streak.)

1. **Set the `origin` remote's URL** on your local repo to point to your new repo on GitHub:
`git remote set-url origin https://github.com/<your-username>/CS-1.3-Core-Data-Structures.git`

1. **Push your local repo** to your *remote* GitHub repo to link your `master` branch to your `origin` remote:
`git push -u origin master`

1. **Commit your code** to your local repo frequently (each time you've made progress or completed a challenge).

1. **Push your commits** to your remote GitHub repo when you want to publish and backup your code:
`git push` (the `-u` in the previous command lets you omit `origin master` afterward).

### Course Remote
Follow these instructions *exactly* to access new and improved course materials and starter code as the course repo is updated.

1. **Add a new remote** to your local repo that points to this course repo:
`git remote add course https://github.com/Make-School-Courses/CS-1.3-Core-Data-Structures.git`

1. **Pull from the `course` remote** when you want to access new course materials.
  - First be sure you've committed and pushed your recent work (run `git status` to check if it says `Your branch is up to date with 'origin/master'`).
  - Then *pull* new commits from the course repo:
  `git pull course master`
  and fix any merge conflicts that may occur if you edited any files that were updated.

1. **Verify both remotes** (`course` and `origin`) are set up correctly on your local repo:
`git remote -v`
should show output like this:
        course	https://github.com/Make-School-Courses/CS-1.3-Core-Data-Structures.git (fetch)
        course	https://github.com/Make-School-Courses/CS-1.3-Core-Data-Structures.git (push)
        origin	https://github.com/<your-username>/CS-1.3-Core-Data-Structures.git (fetch)
        origin	https://github.com/<your-username>/CS-1.3-Core-Data-Structures.git (push)
