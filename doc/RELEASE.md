# Release notes

### Release 2.1 (06/07/2021):
* CTMD issue part of this release- [#397](https://github.com/RENCI/ctmd/issues/397)
* 397- Change max enrollment data slider option and the range on enrollment data slider.

### Release 2.0 (05/06/2021):
* CTMD issues part of this release [#279](https://github.com/RENCI/ctmd/issues/279), [#307](https://github.com/RENCI/ctmd/issues/307), [#376](https://github.com/RENCI/ctmd/issues/376), [#415](https://github.com/RENCI/ctmd/issues/415), [#421](https://github.com/RENCI/ctmd/issues/421), [#424](https://github.com/RENCI/ctmd/issues/424), [#433](https://github.com/RENCI/ctmd/issues/433)
* 279- Added ability to specify test data set so you don't have to run the whole pipeline:
  * takes about 5 mins to add only a few proposals
  * Shruti is adding more to make the test dataset bigger, has 6 proposals now
* 307- Configured containers at build time to use local time zone
* 376- Deployment plan
* 415, 421- David's most recent enrollment data adjustments
* 424- Fixed Build Dockerfile issue in tic-pipeline-script
* 433- Changed size of API exports from REDCap to simulate pagination
* <b>Patches:</b> 2.0.1- Enable test data, 2.0.2- Disable authentication for test data, 2.0.3- Make the demo server work, 2.0.4- Make the restore button on the website work, 2.0.5- Fix authentication, 2.0.6- Fix for HEAL users email authorization
