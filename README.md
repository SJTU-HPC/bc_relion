# Batch Connect - SJTU Relion

[![GitHub License](https://img.shields.io/badge/license-MIT-green.svg)](https://opensource.org/licenses/MIT)

A Batch Connect app designed for OSC OnDemand that launches Relion within an SJTU Pi batch job.

## Prerequisites

This Batch Connect app requires the following software be installed on the
**compute nodes** that the batch job is intended to run on (**NOT** the
OnDemand node):

For VNC server support:

- [TurboVNC] 2.1+
- [websockify] 0.8.0+

For singularity:

- Singularity 3.5.3+
- An image similar to [allupaku/relion] 
  
  (Remember to modify the path to the location of image in template/script.sh.erb to your own setting.)

For hardware rendering support:

- [X server]
- [VirtualGL] 2.3+

[allupaku/relion]: https://hub.docker.com/r/allupaku/relion/tags

Other software:

- [Lmod] 6.0.1+ or any other `module purge` and `module load <modules>` based
  CLI used to load appropriate environments within the batch job
- [Xfce Desktop] 4+

[TurboVNC]: http://www.turbovnc.org/
[Xfce Desktop]: https://xfce.org/
[websockify]: https://github.com/novnc/websockify
[Lmod]: https://www.tacc.utexas.edu/research-development/tacc-projects/lmod
[X server]: https://www.x.org/
[VirtualGL]: http://www.virtualgl.org/

## Install

Use git to clone this app and checkout the desired branch/version you want to
use:

```sh
scl enable git19 -- git clone <repo>
cd <dir>
scl enable git19 -- git checkout <tag/branch>
```

You will not need to do anything beyond this as all necessary assets are
installed. You will also not need to restart this app as it isn't a Passenger
app.

To update the app you would:

```sh
cd <dir>
scl enable git19 -- git fetch
scl enable git19 -- git checkout <tag/branch>
```

Again, you do not need to restart the app as it isn't a Passenger app.

## Contributing

1. Fork it
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Add some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create a new Pull Request

## License

* Code is licensed under MIT (see LICENSE)
