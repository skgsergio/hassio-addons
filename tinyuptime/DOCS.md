# Home Assistant Add-on: Tinyuptime

[Tinyuptime][tinyuptime] as a Home Assistant add-on.

## Installation

1. Add the add-on repository to your Home Assistant instance.

   [![Open your Home Assistant instance and show the add add-on repository dialog with a specific repository URL pre-filled.][addon-repo-badge]][addon-repo]

1. Open the add-on on your Home Assistant instance and click the "Install" button to install the add-on.

   [![Open this add-on in your Home Assistant instance.][addon-badge]][addon]

1. Configure the add-on with the variables.
1. Start the "Tinyuptime" add-on.

## Configuration

**Note**: _Remember to restart the add-on when the configuration is changed._

Deploy Tinyuptime data project and configure `tb_api_endpoint` and `tb_api_key`
accordingly.

## Changelog & Releases

Releases are based on [Semantic Versioning][semver], and use the format
of `MAJOR.MINOR.PATCH`. In a nutshell, the version will be incremented
based on the following:

- `MAJOR`: Incompatible or major changes.
- `MINOR`: Backwards-compatible new features and enhancements.
- `PATCH`: Backwards-compatible bugfixes and package updates.

See the [changelog][changelog] for more details.

## Support

If you find any issue with the Add-on [open an issue here][issue] GitHub.

## License

This Add-on is licensed under the [GPLv3 license][license].

[addon-repo-badge]: https://my.home-assistant.io/badges/supervisor_add_addon_repository.svg
[addon-repo]: https://my.home-assistant.io/redirect/supervisor_add_addon_repository/?repository_url=https%3A%2F%2Fgithub.com%2Fskgsergio%2Fhassio-addons
[addon-badge]: https://my.home-assistant.io/badges/supervisor_addon.svg
[addon]: https://my.home-assistant.io/redirect/supervisor_addon/?addon=ee4f52f7_tinyuptime&repository_url=https%3A%2F%2Fgithub.com%2Fskgsergio%2Fhassio-addons
[issue]: https://github.com/skgsergio/hassio-addons/issues
[semver]: http://semver.org/spec/v2.0.0.html
[changelog]: https://github.com/skgsergio/hassio-addons/blob/main/tinyuptime/CHANGELOG.md
[license]: https://github.com/skgsergio/hassio-addons/blob/main/tinyuptime/LICENSE.md
[tinyuptime]: https://github.com/skgsergio/tinyuptime
