# Overview

This repository documents the Blue Robotics' [Cockpit](https://blueos.cloud/cockpit/docs/usage/overview) software.

The documentation is generated using the [Zola](https://www.getzola.org/) static site generator.

## Structure

- Each branch covers a minor release (`X.y`) of the software, including any patches (`X.Y.z`) of that release
    - The `latest` branch covers the development state in the BlueOS `master` branch, but is not expected to be consistently up to date
    - The `beta` branch covers the latest beta release, and is intended to at least minimally describe all included features
- For ease of contribution, and to keep the search index independent between versions, each branch is built independently
- Documentation content is in the `content` directory
- The theme is provided as a submodule in the `themes` directory

## Contributing

New features should first be documented in `latest`, and subsequently branched into `beta` and a stable version toegther with the software release cycle.

Improved documentation for existing features should at least be added to `latest`, and ideally also cherry-picked into the existing `beta` and stable-versioned branches as relevant.

Detailed contribution information can be found in [CONTRIBUTING.md](CONTRIBUTING.md)

## License

This documentation is licensed under [CC BY-NC-SA 4.0 <img style="height:22px!important;margin-left:3px;vertical-align:text-bottom;" src="https://mirrors.creativecommons.org/presskit/icons/cc.svg?ref=chooser-v1" alt=""><img style="height:22px!important;margin-left:3px;vertical-align:text-bottom;" src="https://mirrors.creativecommons.org/presskit/icons/by.svg?ref=chooser-v1" alt="attribution"><img style="height:22px!important;margin-left:3px;vertical-align:text-bottom;" src="https://mirrors.creativecommons.org/presskit/icons/nc.svg?ref=chooser-v1" alt="non commercial"><img style="height:22px!important;margin-left:3px;vertical-align:text-bottom;" src="https://mirrors.creativecommons.org/presskit/icons/sa.svg?ref=chooser-v1" alt="share alike">](https://creativecommons.org/licenses/by-nc-sa/4.0/?ref=chooser-v1)
