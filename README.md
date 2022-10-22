# Project ID: f79fd17b-a16c-4cbe-91fc-c2dc91a58a61

# Stable Bread

This application was made as part of a university course on Device-Agnostic Design.

This is a fictional Bakery whose products are generated with a publicly available AI text to image model called "Stable Diffusion". This use does in our opinion fall under "Generation of artworks and use in design and other artistic processes" which is permitted.

## Disclaimer

We at Stable Bread do not want to encourage the unreasonable beauty standards for AI generated products you see on Social Media. As such we do not use discriminatory selection sampling where only the best of the generated images are shown to the world. We believe that all AI generations have a right to be seen. This may however result in slightly disturbing results, so viewer discretion is advised.

Do not enter real credit card information!



## Design Decisions

1. I am aware that some pages do not have 3 break points but two.
   On some pages I did implement the required 3 but it did not make sense in all pages.
   In my humble opinion if the page still works then fewer break points are better as the content does not move around as much. I hope that is enough for the requirement.
3. I did no input validation in Settings, as it was not required and to do that properly would've taken way too long.
4. The home page just displays 3 random Categories and Products nothing hard-coded. Since I do MediaQueries in the body every resize chooses new things. In production that would be a bug. Here it is a fun disco.


## Key Challenges

1. Concurrency is hard in dart. Dart is very async but you cannot wait for anything in the synced part. There are as far as I know no locks. I wanted to wait for the shared_preferences to be initialized before accessing settings but that is impossible to do in a provably safe way as far as I can tell.
2. Riverpod depends on the state in the provider being constant and frozen, but that does clash with a lot of patterns in dart and there is no language enforcement of that.
3. Like most design work it was not hard but so many iterations and boring plumbing that I really feel I should be paid a lot to that... (Unfortunately as far as I know this work is not paid that well...)


## Learning Moments

1. The material design pattern is easy to use but does need a lot of practice to master.
2. I mean I was convinced of that before but now more then ever do I know that I am not a designer and should hire people to do the actual design part if I every depend on that.
3. I may never need to know that again but I think I got the hang of the internals of riverpod and how flutter constructs its widgets.
