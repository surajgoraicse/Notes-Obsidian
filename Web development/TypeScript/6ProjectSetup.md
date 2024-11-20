#### Steps:
1. Initiate Typescript config file: `tsc --init`
2. Initiate a node package : `npm init`
3. Create dist and src directory in the root.
5. Create index.ts in src
6. Configure tsconfig.js file by updating the output file location. Set the output location `outdir` to dist directory.
7. Create a index.html file in the root and link the script file.
8. Run the ts file using watch mode : `tsc -w`
	- This will keep on generating an equivalent js code. 
