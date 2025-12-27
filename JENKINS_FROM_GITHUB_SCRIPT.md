if [ -d slink_group_deps.ts.adligo.org ]; then 
  rm -fr slink_group_deps.ts.adligo.org
fi


git clone https://github.com/adligo/slink_group_deps.ts.adligo.org.git
cd slink_group_deps.ts.adligo.org
npm install
cd node_modules

echo "The following will be the value of the COMMON_NODE_MODULES environment variable in the "
echo "https://github.com/adligo/slink_group.ts.adligo.org Jenkins scripts"
pwd




