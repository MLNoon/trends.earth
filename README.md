# Land Degradation Monitoring Toolbox (LDMT)

`ldmp-qgis-plugin` is the github repository for the Land Degradation Monitoring
Toolbox (LDMT). The LDMT is produced by the Land Degradation Monitoring
Project. The LDMT is a [Quantum GIS (QGIS)](http://www.qgis.org) plugin used
to support monitoring of status and trends of land degradation.

This toolbox was produced as an output of the Global Environment Facility
(GEF)-funded project [“Enabling the use of global data sources to assess and
monitor land degradation at multiple scales”](http://vitalsigns.org/gef-ldmp).  
The project aims to provide guidance on robust methods and a toolbox for 
assessing, monitoring status, and estimating trends in land degradation using 
remote sensing technology.

The Land Degradation Monitoring Project is a collaboration of Conservation
International, the National Aeronautics and Space Administration (NASA), and
Lund University.

## Installation

### Stable version (recommended)

The latest release version of the plugin can be installed from within QGIS from 
the [QGIS plugin repository](http://plugins.qgis.org/plugins/teamqgis).

### Development version

If you are interested in using the very latest version of the plugin, or in 
contributing to the development of it, you will want to install the development 
version. There are two ways to install the development version:

* Using a packaged version (zipfile)

* Cloning the github repository and installing from that code

It is easier to install the plugin from a zipfile than from github, but your 
version of the plugin might be slightly out of date if you use a packaged 
version (unlikely to be an issue unless you have a specific need for the latest 
version of the plugin).  Installing the plugin from github is the only way to 
ensure you have the very latest version of the code.

#### Installing the latest packaged version

Download the latest`LDMT`zipfile from here: 
https://landdegradation.s3.amazonaws.com/Sharing/LDMP.zip.

Extract `LDMP.zip` to the python plugins folder for your installation of QGIS. 
For example, if your username is "azvol", then this might be 
`C:\Users\azvol\.qgis2\python\plugins` if you are using Windows. If you are 
using a Mac and your username is "azvol", then this might be
`/Users/azvol/.qgis2/python/plugins`.

Once you are finished, you should have a folder named "LDMP" within your 
`.qgis2/python/plugins` folder.

Start QGIS, and click on "Plugins" then "Manage and install plugins". In the 
plugins window that appears, click on "Installed", and then make sure there is 
a check in the box next to "Land Degradation Monitoring Tool". The plugin is 
now installed and activated. Click "Close", and start using the plugin.

#### Installing the very latest code from github

Building the python `cryptography` package [requires having the OpenSSL headers 
installed](https://cryptography.io/en/latest/installation/#building-cryptography-on-windows). 
On Windows, the easiest way to install the OpenSSL headers is to download them 
[from 
here](https://cryptography.io/en/latest/installation/#building-cryptography-on-windows). 
Take note of the folder where you install the OpenSSL headers - you will need 
to refer to it later.

Once the OpenSSL headers are installed, open a terminal window and clone the 
latest version of the repository from Github:

```
git clone https://github.com/ConservationInternational/ldmp-qgis-plugin
```

Navigate to the root folder of the newly cloned repository, and install 
`pavement`, a tool that assists with installing the plugin:

```
pip install pavement
```

Before installing the plugin, several external dependencies must be installed.  
The `paver setup` task will handle this. On Windows, use the below code in a 
command window to run the setup task with `pavement`. Note that if you 
installed the OpenSSL headers to a different folder, you will need to change 
the below commands accordingly.

```
set LIB=C:\openssl-win64-2010\lib;%LIB%
set INCLUDE=C:\openssl-win64-2010\include;%INCLUDE%
paver setup
```

Once `paver setup` has run, you can install the plugin using paver:

```
paver install
```

If you modify the code, you need to run `paver install` to update the installed 
plugin in QGIS.  You only need to rerun `paver setup` if you change or update 
the plugin dependencies. After reinstaling the plugin you will need to restart 
QGIS or reload the plugin. Install the "Plugin reloader" plugin if you plan on 
making a log of changes (https://github.com/borysiasty/plugin_reloader).

## License

The `ldmp-qgis-plugin` is free and open-source. It is released under the
following (MIT) license:

Permission is hereby granted, free of charge, to any person obtaining a copy of
this software and associated documentation files (the "Software"), to deal in
the Software without restriction, including without limitation the rights to
use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies
of the Software, and to permit persons to whom the Software is furnished to do
so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

Except as contained in this notice, the name(s) of the above copyright holders
shall not be used in advertising or otherwise to promote the sale, use or other
dealings in this Software without prior written authorization.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
