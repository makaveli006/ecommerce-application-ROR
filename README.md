

This web application was inspired by a video from Conner Jensen on YouTube. Their insightful tutorial on [specific topic or project name] provided a solid foundation for this project. While I have made modifications and added some unique features to tailor the app to my own goals, the core idea and structure are heavily influenced by their excellent content. You can check out their original video [https://www.youtube.com/watch?v=hURUMwdCWuI] to see the source of inspiration. A huge thanks to Conner Jensen for sharing their knowledge and inspiring this creation!

The application in the github is the base version with pending migrations and the already uploaded categories removed.To save disk space

Things to remember before you up and run the project

WINDOWS
==============
1. install ruby 3.2.2 (x64-devkit)
2. bundle install (from inside project directory)

You will encounter psych gem installation issue because Psych gem requires the yaml.h library inside (C:\Ruby32-x64\msys64\mingw64\include), which is missing on your system. This library is part of the libyaml development package.

3. Open C:\Ruby32-x64\msys64\msys2.exe and execute pacman -Syu (after updation check "bundle install" again by opening a new CMD in the project directory. If the issue still persist follow next step otherwise skip the next step) => Can check installed packages using pacman -Q
4. Open C:\Ruby32-x64\msys64\msys2.exe and execute pacman -S mingw-w64-x86_64-libyaml =>Can check installed packages using pacman -Q

I have provided two types of Procfile.dev files called Procfile2.dev and Procfile.dev and removed the bin/ from it

previously
-------------
web: bin/rails server
css: bin/rails tailwindcss:watch

now
-------------------------
web: rails server
css: rails tailwindcss:watch


previously
---------------------
web: env RUBY_DEBUG_OPEN=true bin/rails server -p 3000
css: bin/rails tailwindcss:watch

now
----------------
web: env RUBY_DEBUG_OPEN=true rails server -p 3000
css: rails tailwindcss:watch



5. run => bin/dev (when u open the app in browser through localhost:3000 it will ask for u to migrate)

You can check => bin/rails db:migrate:status (if the migrations are down or up)

6. run => bin/rails db:migrate (Or you can migrate through browser by clicking "run pending migration" button)

7. run =>bin/dev (Now again go to the localhost:3000)

8. Locally we use sqlite3 as our database. This is already set up for you. In production make sure your `DATABASE_URL` env variable is set. We use PostgreSQL in production.

9. We deploy on Render create a free account here render.com





