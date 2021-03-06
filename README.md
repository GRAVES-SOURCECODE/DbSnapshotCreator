# ![Feature](https://raw.githubusercontent.com/ecirpnaes/DbSnapshotCreator/master/images/logo.png) Database Snapshot Creator

Provides a quick and easy way to create a snapshot of a database. The action can be executed directly against the server or scripted to a new SQL window so you can run it yourself.

## FAQ

* What's a database snapshot?
  * _It's best to read the [Microsoft docs](https://docs.microsoft.com/en-us/sql/relational-databases/databases/database-snapshots-sql-server), but the short answer is that a database snapshot is a static, `read-only` copy of a source database that gives you a consistent view of a database as of a certain point in time. You can recover the source database to the point when the snapshot was created from a database snapshot._
* Can multiple snapshots be created quickly without lot of typing of sql commands?
  * _Sure. The default setting for the extension is to create a snaphot name based on the source db name and a timestamp. A simple righl-click will create or revert the snapshot. See [the example here](#Execute-Action-Directly)._
* Can I choose my own naming convention for my database snapshots?
  * _Yes, you can. Configure the extension to just script the necessary SQL statements to create the snapshot. You can then change the name (and file location) if desired. Refer to the animated gif below. [Script Only Example](#Script-Only)_

## Installation

The current release is available to [download as a .vsix file](https://github.com/ecirpnaes/DbSnapshotCreator/releases/download/0.1.0/db-snapshot-creator-0.1.0.vsix) and can be installed by opening the File Menu and selecting `Install Extension from VSIX Package`

## Extension Settings

This extension contributes the following settings:

* `snapshotCreator.scriptOnly`: If this is checked, the snapshot extension will only create the SQL commands necessary to create or revert a snapshot. If you want the extension to actually execute the commands against the database, then leave this unchecked.

## How To Use

* Navigate to a database object in the Object Explorer Tree.
* Right click on a database node to bring up the context menu.
* If the database node is a database (and not a database snapshot), you have the option to create a snapshot.
* If the database node is a database snapshot, you will have the option to revert the source database from the snapshot.

#### Execute Action Directly

![Feature](https://raw.githubusercontent.com/ecirpnaes/DbSnapshotCreator/master/images/createRevertExec.gif)

#### Script Only

![Feature](https://raw.githubusercontent.com/ecirpnaes/DbSnapshotCreator/master/images/createRevertScript.gif)

## Known Issues

* This only works with the MSSQL provider, i.e. Microsoft SQL Server.
* Azure Data Studio lacks metadata information to indicate whether or not a database node is an actual database or a database snapshot. (This differs from SQL Management Studio where Database Snapshots are grouped under their own parent node.) As such, this extension assumes that all database nodes are actual databases unless the database name has `snapshot` in it. Hopefully the Azure Studio team will see fit to include this information in a future release.

## Unknown Issues

Can be raised here: <https://github.com/ecirpnaes/DbSnapshotCreator/issues>

## Releases

### Current Version - 0.1.0

## Change Log

Can be found here: <https://raw.githubusercontent.com/ecirpnaes/DbSnapshotCreator/master/CHANGELOG.md>
