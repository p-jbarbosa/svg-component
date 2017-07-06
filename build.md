# Build Information

SVG Component is released through [github releases](https://github.com/blog/1547-release-your-software).

Release artifacts are created with [maven](https://maven.apache.org/) and uploaded to current or new releases.

## Steps to create/update releases

**BEFORE START**
New releases imply new plugin artifacts. New plugin artifacts will require update on svg component entry within marketplace.xml, to became available on Pentaho Marketplace. You can achieve this by forking [Pentaho Marketplace project](https://github.com/pentaho/marketplace-metadata) and making a pull request to the project, after you have committed this changes.

If you want to perform a new plugin release, or update one that is still on draft, please follow this steps:

1. If you didn't clone already the project from github, go ahead.
1. If you don't have maven already available on your machine, please install it. 
1. Update the project's contents that lead you to perform this update/new release (if you don't know where to put these contents, please read section Plugin Structure).
1. Go to project's root on your machine.
1. Run mvn package - this will read pom.xml on the project's root and start to create the new release artifacts.
1. Upload the generated artifacts to project's release on github. You can find them here:
  1. assemblies/cde-dashboard/target/sample-svg-component.zip;
  1. assemblies/platform-plugin/target/svg-component-cdf.zip.
1. Copy URLs to the new artifacts.
1. Save and publish the release.
1. Update marketplace.xml svg component entry with the URL obtained in the previous step.
1. Finally, if you want to clean your target folder after this operation, please run mvn clean.

## Plugin Structure
