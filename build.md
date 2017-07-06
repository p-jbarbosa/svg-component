# Build Information

SVG Component is released through [github releases](https://github.com/blog/1547-release-your-software).

Release artifacts are created with [maven](https://maven.apache.org/) and uploaded to current or new releases.

## Plugin File Structure

This plugin has a maven like structure. Contents are divided over two main directories:
* *impl*, that holds all the implementation related files;
* *assemblies*, where all the final artfacts are made available;

Because this represents a CDE component we have two implementation paths: 
* one that represents the component's code on _/impl/component/src/main/javascript_;
* and another one that represents the sample, on _impl/sample-component/src/main/resources_.

This way, if you want to update the sample, or perform a code modification, you must update the files that lay on _impl_ folder.

This contents will eventually be _assembled_ into the second main directory. The _assemblies_ directory keeps the same paths that we already saw on _impl_:
* platform-plugin, where we keep the remaining resources for component's final package, and where we will collect this final package;
* cde-dashboard, where the final sample package will be available.

To update the _assemblies_ directory you have to build the solution. 

## Build

### Before you start

New releases imply new plugin artifacts. New plugin artifacts will require update on svg component entry within marketplace.xml, to became available on Pentaho Marketplace. You can achieve this by forking [Pentaho Marketplace project](https://github.com/pentaho/marketplace-metadata) and making a pull request to the project, after you have committed this changes.

### Steps to build 

If you want to perform a new plugin release, or update one that is still on draft, please follow this steps:

1. If you didn't clone already the project from github, go ahead.
1. If you don't have maven already available on your machine, please install it. 
1. Update the project's contents that lead you to perform this update/new release (if you don't know where to put these contents, please read section Plugin File Structure).
1. Go to project's root on your machine.
1. Run mvn package - this will read pom.xml on the project's root and start to create the new release artifacts.
1. Upload the generated artifacts to project's release on github. You can find them here:
    1. assemblies/cde-dashboard/target/sample-svg-component.zip;
    1. assemblies/platform-plugin/target/svg-component-cdf.zip.
1. Copy URLs to the new artifacts.
1. Save and publish the release.
1. Update marketplace.xml svg component entry with the URL obtained in the previous step.
1. Finally, if you want to clean your target folder after this operation, please run mvn clean.


