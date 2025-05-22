# slink_group_deps.ts.adligo.org
This project is an experiment, I'm going to create a package.json file and then sym link to that projects node_modules folder using a environment variable and see how it behaves.  This will reduce or eliminate the need to run 'npm i' over and over again on my build servers, significantly speeding up JavaScript and TypeScript builds. 

# Usage 

After you have checked out the project into a top level folder (i.e. the same folder your checking out slink_group.ts.adligo.org) then simply run;

```
npm install
```

Then note the absolute path of it's node_modules directory.  