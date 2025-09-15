# 12. Projects

We have covered a lot of theory, in this section, I'm going to wind up these notes by kicking off a first project.&#x20;

We need a standard directory structure, file naming, etc.

I'm going to give you a practice here, you may find better guidelines, or your company may have specific requirements.

Before you begin, create a directory to keep example files in. This could be on your OneDrive, in these examples, I am using **OneDrive\Python\Exercises\_12**&#x20;

For this module, in any project:

1. I assume you have already created a GITHUB account called L12345678, using your own L number.
2. Create a GITHUB repo under this account with an appropriate name for your project, with **readme.md**, a **license file** and a **gitignore.** Give your lecturer access as a contributor. Use lecturer's account = [https://github.com/GreatlyImprovedTechnology](https://github.com/GreatlyImprovedTechnology)
3. For the actual project structure, create a [batch file](batch-file.md) and after you run it and have the correct structure, save it to an appropriate directory in the repo.
4. Copy any code you plan to reuse into a packages folder. You may have more than one. In my notes I call this [source](utilities.md), but feel free to give it any appropriate name.&#x20;
5. Once a project has a level of directory structure, you should use [pathlib](paths.md) to keep this tidy.
6. Create [templates](template.md) for your scripts to keep them consistent.
7. By now, you should have a good template for your [markdown](markdown.md) files. Replace the default readme.md with this and edit as appropriate.
8. In most projects, my programme flow will be in main.py in the root directory of the project. Detailed code will be in functions or classes, saved in packages. Keep to this simple design pattern.
9. And there will always be a test strategy, you can explain it in the **README.md**. Typically, you will use Pylint and at least one unit test.
