# slink_group_deps.ts.adligo.org
This project is an experiment, I'm going to create a package.json file and then sym link to that projects node_modules folder using a environment variable and see how it behaves.  This will reduce or eliminate the need to run 'npm i' over and over again on my build servers, significantly speeding up JavaScript and TypeScript builds. 

# Usage 

After you have checked out the project into a top level folder (i.e. the same folder your checking out slink_group.ts.adligo.org) then simply run;

```
npm install
```

Then note the absolute path of it's node_modules directory.  

SLink the command line program installed with; 

```
npm install -g @ts.adligo.org/slink
```

Will be upgraded so that when a package.json file has a field like;

```
"sharedNodeModuleProjectSLinks": ["slink_group_deps.ts.adligo.org", "fab_group_deps.ts.adligo.org"]	
```

A symlink for node_modules will be created in the current directory (with this package.json file).   Slink will create this symlink by identifying the first matching project in the parent folders so that the dir structure will look like;
top-folder
  | -> slink_group_deps.ts.adligo.org
  | -> slink_group.ts.adligo.org
  |    | -> slink_tests.ts.adligo.org
  |    | -> slink.mts.adligo.org
  etc
  
Alternatively, this may be overridden for build servers the absolute path of this target directory where the node_modules are actually installed can be linked to using a custom environment variables.  For example the build script could include;

```
export NODE_MODULE_SLINK=/var/foo/bar/node_modules
export TESTS4TS_NODE_MODULE_SLINK=$NODE_MODULE_SLINK
```

Then the package.json in tests4ts.ts.adligo.org would have a setting like;

```
"sharedNodeModuleProjectSLinkEnvVar": ["TESTS4TS_NODE_MODULE_SLINK"]	
```





