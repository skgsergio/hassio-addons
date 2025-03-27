# Home Assistant Add-on: Tinybird Self-Managed

[Tinybird Self-Managed][tb-self-managed] as a Home Assistant sdd-on.

## Installation

1. Add the add-on repository to your Home Assistant instance.

   [![Open your Home Assistant instance and show the add add-on repository dialog with a specific repository URL pre-filled.][addon-repo-badge]][addon-repo]

1. Open the add-on on your Home Assistant instance and click the "Install" button to install the add-on.

   [![Open this add-on in your Home Assistant instance.][addon-badge]][addon]

1. Configure the add-on with the variables returned by `tb infra add`.
1. Start the "Tinybird Self-Managed" add-on.

## Configuration

**Note**: _Remember to restart the add-on when the configuration is changed._

The only Add-on configuration is the values returned by `tb infra add` and
cloudflared token if willing to use it for exposing Tinybird Self-Managed.

```yaml
tb_infra_token: p.eyJpIjogI...F28g
tb_infra_workspace: tinyhome
tb_infra_organization: TinyHomeOrg
tb_infra_user: my@email.tld
cloudflared_token: eyJhIjoiN...NSJ9
```

### Cloudflare Tunnel

This feature is optional, when the configuration setting is empty the tunnel is
disabled.

If you want to use it provide the `cloudflared_token` following the steps below:

1. Go to https://dash.teams.cloudflare.com/
1. Open Network > Tunnels
1. Create a Tunnel > Tunnel type: Cloudflared
1. Copy the token from any of the options presented
1. Add the public hostname that you choose when you created the Tinybird
   self-managed region and configure the service as `http://localhost:7181`

For more information check [Cloudflare's Docs][cf-docs].

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

For support working with Tinybird check [Tinybird's docs][tb-docs].

## License

This Add-on is licensed under the [Tinybird Self-Managed License
(TSML)][license].

[addon-repo-badge]: https://my.home-assistant.io/badges/supervisor_add_addon_repository.svg
[addon-repo]: https://my.home-assistant.io/redirect/supervisor_add_addon_repository/?repository_url=https%3A%2F%2Fgithub.com%2Fskgsergio%2Fhassio-addons
[addon-badge]: https://my.home-assistant.io/badges/supervisor_addon.svg
[addon]: https://my.home-assistant.io/redirect/supervisor_addon/?addon=ee4f52f7_tinybird&repository_url=https%3A%2F%2Fgithub.com%2Fskgsergio%2Fhassio-addons
[issue]: https://github.com/skgsergio/hassio-addons/issues
[semver]: http://semver.org/spec/v2.0.0.html
[changelog]: https://github.com/skgsergio/hassio-addons/blob/main/tinybird/CHANGELOG.md
[license]: https://github.com/skgsergio/hassio-addons/blob/main/tinybird/LICENSE.md
[tb-self-managed]: https://www.tinybird.co/docs/forward/get-started/self-managed/manual
[tb-docs]: https://www.tinybird.co/docs/forward
[cf-docs]: https://developers.cloudflare.com/cloudflare-one/connections/connect-networks/get-started/create-remote-tunnel/
