# Upgrading the Matrix services

This playbook not only installs the various Matrix services for you, but can also upgrade them as new versions are made available.

If you want to be notified when new versions of Synapse are released, you should join the Synapse Homeowners room: [#homeowners:matrix.org](https://matrix.to/#/#homeowners:matrix.org).

To upgrade the services:

- update your playbook directory (`git pull`), so you'd obtain everything new we've done

- take a look at [the changelog](../CHANGELOG.md) to see if there have been any backward-incomptabile changes that you need to take care of

- re-run the [playbook setup](installing.md): `ansible-playbook -i inventory/hosts setup.yml --tags=setup-all`

- restart the services: `ansible-playbook -i inventory/hosts setup.yml --tags=start`

**Note**: major version upgrades are not done to the internal PostgreSQL database. To upgrade that one, refer to the [upgrading PostgreSQL guide](maintenance-postgres.md#upgrading-postgresql).
