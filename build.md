# Build Information

SVG Component is released through [github releases](https://github.com/blog/1547-release-your-software).

Release artifacts are created with [maven](https://maven.apache.org/) and uploaded to current or new releases.

## Steps to create/update releases

**READ BEFORE START** - new plugin artifacts will require update on svg component entry within marketplace.xml, to became available on Pentaho Marketplace.

If you want to perform a new plugin release, or update one that is still on draft, please follow this steps:

1. If you didn't clone already the project from github, go ahead.
1. If you don't have maven already available on your machine, please install it. (On linux environments just run sudo apt-get update and sudo apt-get install maven).
1. Update the project's contents that lead you to perform this update/new release (if you don't know where to put these contents, please read section Plugin Structure).
1. Go to project's root on your machine.
1. Run mvn package - this will read pom.xml on the project's root and start to create the new release artifacts.
1. Upload the generated artifacts to project's release on github. You can find them here:
  * assemblies/cde-dashboard/target/sample-svg-component.zip;
  * assemblies/platform-plugin/target/svg-component-cdf.zip.
1. You may want to clean your target folder after this operation: run mvn clean.
