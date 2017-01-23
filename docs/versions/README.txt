DEVELOPERS 

OpenCluster works on the feature-branch model.  

Starting a New Feature
----------------------

1. Start from the master branch
	git checkout master
	git pull origin master

2. Create branch (in this example, we will create a feature called 'multiline-config'
	git checkout -b feature-multiline-config 

3. Create text file in the docs/versions/ folder, describing the feature that you are implementing.
	nano docs/versions/feature-<name of feature>.txt

4. Code.... test... Code... test...

5. When a feature branch is complete.

6. Feature branches are added to a release.  Once a branch is added to a release, the release will be tied to it, and generally wont be 
   released until it has passed the testing phase.



Starting a new Release
----------------------

1. Start from the master branch
	git checkout master
	git pull origin master

2. Create Release branch (in this example, release 1.20.00)
	git checkout -b release-1.20.00

3. Create the directory and readme file for the release.
	mkdir docs/versions/1.20.00
	nano $_/readme.txt
		This version, started on July 10, 2016 includes the following changes.

4. Merge, or accept pull requests of specific features that are included in the release, into the release branch.
	git merge feature-multiline-config

5. Update the readme file with details about the multiline-config feature.  A text file will appear that describes the feature branch.  
   Can use that detail.

6. Push the release to the repo.
	git push origin



Promoting a release
-------------------

When a release is ready to begin testing, it will be merged into the testing branch.

1. Ensure testing branch is up-to-date
	git checkout master
	git pull origin master

2. Checkout the testing branch
	git checkout testing

3. Merge the release branch into the testing branch.
	git merge release-1.20.00
	git push origin

4. Initiate the testing suite.

5. Send out communications that an updated release branch has been applied to the testing branch.  This is now a release candidate.


