# Release notes

### Release 2.10 (TBD):

Issues part of this release:
* [486](https://github.com/RENCI/ctmd/issues/486)
* [472](https://github.com/RENCI/ctmd/issues/472)

Pull requests (PRs) part of this release:
* [?](?)
* [?](?)

#### Internal-facing work:
Tickets for internal work:
* [501](https://github.com/RENCI/ctmd/issues/501) document how to install pipeline on your own computer 
* [511](https://github.com/RENCI/ctmd/issues/511) fix pipeline tests

Pull requests (PRs) for internal work:
* [?](?) update ctmd-dashboard/docker-compose.prod.yml to use 2.10 pipeline
* [4](https://github.com/RENCI/map-pipeline-schema/pull/4): map-pipeline-schema, remove non-null constraint; issue #501 [pipeline doc]: document how to install pipeline on your computer
* [8](https://github.com/RENCI/map-pipeline/pull/8): map-pipeline, code cleanup and annotation; issue #501 [pipeline doc]: document how to install pipeline on your computer
* [25](https://github.com/RENCI/tic-map-pipeline-script/pull/25) updated readme and submodules; issue #501
* [277](https://github.com/RENCI/ctmd-dashboard/pull/277) partially addresses issue 501

### Release 2.9 (TBD):
Issues part of this release:
* [473](https://github.com/RENCI/ctmd/issues/473) Create patient enrollment data (round graph) similar to site activation and site enrollment
* [495](https://github.com/RENCI/ctmd/issues/495): EHR based cohort assessment tickbox has no data (stretch)

Pull requests (PRs) part of this release:

* [276](https://github.com/RENCI/ctmd-dashboard/pull/276) issue 473
* [274](https://github.com/RENCI/ctmd-dashboard/pull/274) issue 495

#### Internal-facing work:

Pull requests (PRs) for internal work:
* [275](https://github.com/RENCI/ctmd-dashboard/pull/275) Bump eventsource from 1.0.7 to 1.1.1 in /frontend


### Release 2.8 (05/12/2022):
Update servers to synch at 03:00 instead of 04:00

Issues part of this release:
* [496](https://github.com/RENCI/ctmd/issues/496): Proposal table export headers
* [404](https://github.com/RENCI/ctmd/issues/404): 'go to HEAL' button displays on both ctmd and heal sites
* [410](https://github.com/RENCI/ctmd/issues/410): Hover on left hand side of screen to see sister sites to toggle between (TIN, HEAL, CTMD, XXX) 
* [500](https://github.com/RENCI/ctmd/issues/500): set synch to happen at 3a EST

Pull requests (PRs) part of this release:
* [266](https://github.com/RENCI/ctmd-dashboard/pull/266): Proposal table export headers, issue 496
* [263](https://github.com/RENCI/ctmd-dashboard/pull/263): Feature/dynamic ctmd/heal toggle button, issue 404, 410

#### Internal-facing work:
* fixed dev server
* reset redcap user accounts that had expired

Internal-facing Issues:
* [499](https://github.com/RENCI/ctmd/issues/499): Broad tracking of ctmd traffic for maintenance purposes

Internal-facing PRs:
* [269](https://github.com/RENCI/ctmd-dashboard/pull/269): analytics-no-env-var, issue 499
API bumps:
* [270](https://github.com/RENCI/ctmd-dashboard/pull/271): Bumps ansi-regex from 4.1.0 to 4.1.1.
* [270](https://github.com/RENCI/ctmd-dashboard/pull/270): Bumps axios from 0.21.1 to 0.21.2.
* [265](https://github.com/RENCI/ctmd-dashboard/pull/265): Bumps minimist from 1.2.5 to 1.2.6.
Frontend bumps:
* [273](https://github.com/RENCI/ctmd-dashboard/pull/273): Bumps lodash from 4.17.19 to 4.17.21.
* [272](https://github.com/RENCI/ctmd-dashboard/pull/272): Bumps axios from 0.19.0 to 0.21.2.
* [267](https://github.com/RENCI/ctmd-dashboard/pull/267): Bumps async from 2.6.2 to 2.6.4.
* [259](https://github.com/RENCI/ctmd-dashboard/pull/259): Bumps url-parse from 1.5.7 to 1.5.10.
* [258](https://github.com/RENCI/ctmd-dashboard/pull/258): Bumps y18n from 3.2.1 to 3.2.2.

### Release 2.7.1 (04/05/2022):
This patch properly merges 262 (below):
* ctmd-dashboard [262](https://github.com/RENCI/ctmd-dashboard/pull/262), issue 488

### Release 2.7 (03/25/2022):
Issues part of this release:
* [488](https://github.com/RENCI/ctmd/issues/488): Change enrollment data graph to report date of enrollment data (from upload file)
* [410](https://github.com/RENCI/ctmd/issues/410): Hover on left hand side of screen to see sister sites to toggle between (TIN, HEAL, CTMD, XXX)
* [404](https://github.com/RENCI/ctmd/issues/404): Go to HEAL' button displays on both ctmd and heal 
* [414](https://github.com/RENCI/ctmd/issues/414): HEAL & CTMD - SITE NUMBER column: allow numerals AND text:
  + 414 had previously been addressed, but the database needed to be reset.
Pull requestes (PRs) part of this release: 
* ctmd-dashboard [262](https://github.com/RENCI/ctmd-dashboard/pull/262), issue 488
* ctmd-dashboard [#261](https://github.com/RENCI/ctmd-dashboard/pull/261), issue 404, 410

### Release 2.6 (02/25/2022):
* Pull requests (PRs) part of this release are all from dependabot: [#253](https://github.com/RENCI/ctmd-dashboard/pull/253), [#254](https://github.com/RENCI/ctmd-dashboard/pull/254), [#255](https://github.com/RENCI/ctmd-dashboard/pull/255), [#256](https://github.com/RENCI/ctmd-dashboard/pull/256), [#257](https://github.com/RENCI/ctmd-dashboard/pull/257) 

### Release 2.5 (01/25/2022):
* Pull requests (PRs) part of this release- [#248](https://github.com/RENCI/ctmd-dashboard/pull/248), [#249](https://github.com/RENCI/ctmd-dashboard/pull/249), [#9](https://github.com/RENCI/tic-map-pipeline-script/pull/9), [#22](https://github.com/RENCI/tic-map-pipeline-script/pull/22), [#24](https://github.com/RENCI/tic-map-pipeline-script/pull/24)
* 248: ctmd-dashboard PR- Get dashboard working in local environment
* 249: ctmd-dashboard PR- Import axios to help with logging of auth error.
* 9: tic-map-pipeline-script PR- Don't allow download of data dictionary.
* 22: tic-map-pipeline-script PR- Allow cors in local development environment.
* 24: tic-map-pipeline-script PR- Stricter date format.
* <b>Patches</b> <b>2.5.1-</b> Pull request [#250](https://github.com/RENCI/ctmd-dashboard/pull/250), [#251](https://github.com/RENCI/ctmd-dashboard/pull/251), [#252](https://github.com/RENCI/ctmd-dashboard/pull/252)

### Release 2.4 (09/27/2021):
* CTMD issue part of this release- [#463](https://github.com/RENCI/ctmd/issues/463)
* 463- Add ACTUAL METRICS to tickboxes on STUDY tab.
* <b>Patches</b> <b>2.4.2-</b> Pull request[#244](https://github.com/RENCI/ctmd-dashboard/pull/244), Bug fixes for the uploads issue on the website: Pull request[#245](https://github.com/RENCI/ctmd-dashboard/pull/245).
<b>NOTE:</b> There is no 2.4.1 patch.

### Release 2.3 (08/30/2021):
* CTMD issue part of this release- [#138](https://github.com/RENCI/ctmd/issues/138), [#390](https://github.com/RENCI/ctmd/issues/390), [#392](https://github.com/RENCI/ctmd/issues/392), [#398](https://github.com/RENCI/ctmd/issues/398), [#399](https://github.com/RENCI/ctmd/issues/399), [#416](https://github.com/RENCI/ctmd/issues/416), [#418](https://github.com/RENCI/ctmd/issues/418), [#461](https://github.com/RENCI/ctmd/issues/461), [#465](https://github.com/RENCI/ctmd/issues/465)
* 138- Detail how env variables are being used.
* 390/398- Closely related issues. Change denominator for % sites activated milestones. 
* 392- Change label on metric currently named Protocol to FPFV . 
* 399- Create STUDY ENROLLMENT donut (enrollment of patients).
* 416- Remove timestamp from CTMD / metrics / SITES.
* 418- Fix study milestone dates - show Dec 31, 1969.
* 461- Create special access list for CTMD global uploads (CTSA and SITES).
* 465- PROTOCOL in STUDIES TAB tickboxes needs to pull from a different field.
* <b>Patches</b> <b>2.3.1-</b> Bug fix for issue 418 above: Pull request[#237](https://github.com/RENCI/ctmd-dashboard/pull/237), Bug fixes for issue 465: Pull request[#238](https://github.com/RENCI/ctmd-dashboard/pull/238)

### Release 2.2 (08/02/2021):
* CTMD issue part of this release- [#338](https://github.com/RENCI/ctmd/issues/338), [#459](https://github.com/RENCI/ctmd/issues/459), [#414](https://github.com/RENCI/ctmd/issues/414), [#460](https://github.com/RENCI/ctmd/issues/460), [#411](https://github.com/RENCI/ctmd/issues/411)
* 338- Error-handling for CSV upload pre-parsing.
* 459- Apache spark binary version.
* 414- SITE NUMBER column should allow numerals and text.
* 460- STUDY tab is missing a field / tickbox.
* 411- Allow unusual characters in CSV uploads.
* <b>Patches</b> <b>2.2.1-</b> Additional fixes for issue 338 above: Pull request[#229](https://github.com/RENCI/ctmd-dashboard/pull/229), <b>2.2.2-</b> Bug fixes for issue 338: Pull request[#230](https://github.com/RENCI/ctmd-dashboard/pull/230), <b>2.2.3-</b> Resolves issue 460, Bug fixes for issue 414: Pull request [#231](https://github.com/RENCI/ctmd-dashboard/pull/231), Bug fixes for issue 338: Pull request[#232](https://github.com/RENCI/ctmd-dashboard/pull/232).

### Release 2.1 (06/07/2021):
* CTMD issue part of this release- [#397](https://github.com/RENCI/ctmd/issues/397), [#419](https://github.com/RENCI/ctmd/issues/419), [#449](https://github.com/RENCI/ctmd/issues/449)
* 397- Change max enrollment data slider option and the range on enrollment data slider.
* <b>Patches</b> 2.1.1- Fix for issue[#419](https://github.com/RENCI/ctmd/issues/419) Pull request[#217](https://github.com/RENCI/ctmd-dashboard/pull/217), 2.1.2- Fix for issue[#449](https://github.com/RENCI/ctmd/issues/449) Pull Request[#220](https://github.com/RENCI/ctmd-dashboard/pull/220), 2.1.3- Pull Request[#219](https://github.com/RENCI/ctmd-dashboard/pull/219), 2.1.4- New bug found for issue[#449](https://github.com/RENCI/ctmd/issues/449) addressed via Pull Request[#223](https://github.com/RENCI/ctmd-dashboard/pull/223), Pull Request[#224](https://github.com/RENCI/ctmd-dashboard/pull/224) and Pull Request[#225](https://github.com/RENCI/ctmd-dashboard/pull/225).

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
