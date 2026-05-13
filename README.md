# eclipselink-logsep

Patched EclipseLink 2.7.14 jar.

## Base

Original artifact:

`org.eclipse.persistence:eclipselink:2.7.14`

## Custom change

Changed SQL bind parameter logging in:

`org.eclipse.persistence.internal.databaseaccess.DatabaseCall.appendLogParameters(...)`

Bind parameters are separated with `\u07aa` instead of comma/space to simplify log parsing.

## Version

`2.7.14-fork1`

## Usage

Intended for use via JitPack.