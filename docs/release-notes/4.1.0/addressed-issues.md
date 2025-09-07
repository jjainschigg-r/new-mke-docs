# Addressed issues

Issues addressed in the MKE 4k 4.1.0 release include:



- Fixed an issue wherein the mkectl ``apply`` and ``upgrade``
  commands could not succeed on clusters with less than 2GB of available
  storage.



- Fixed an issue in the MKE web UI wherein the breadcrumbs on the
  Settings > License page were incorrectly linked.



- Fixed an issue wherein the OIDC client secret was not being
  migrated during an mkectl upgrade.



- Fixed an issue wherein managed user passwords were not migrated as
  part of an upgrade from MKE 3.



- Fixed an issue wherein Prometheus could be accessed without
  authentication.