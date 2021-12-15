# fin-torrent
Free Automated Decentralized Financial Data Provider
# idea

fin-torrent does not solve the initial data acquisition, but the subsequent data distribution to many people.

The problem with getting financial data for data scientific projects (especially large historical time series) is the cost of of running servers that provide the data via an API and of the ISP-bill. This seems to be a classical problem of a centralised system that can be remedied by decentralisation. By providing financial data via torrent files, the "bill" for hosting the data gets distributed - every downloader (leecher) will also have to provide (seeder) the data; this is how the torrent-system works. One just needs an automated script that will create the right number of torrents in the right format (tens of thousands).

fin-torrent can be expanded to include a fin-torrent python library with bittorrent-capabilities that can be used to provide Data Scientists with financial data without having to use costly, centralised public APIs.

If it is made sure for the created torrents to never collapse (anchoring), fin-torrent might prove to be a great archive for hosting large historical financial data-sets.

fin-torrent will not be limited to time series data. It can distribute any financial data, provided it is structured hard, with no deviations.

The central torrent-ledger takes the form of a torrent-tracker. Flags are added to the info to differentiate between "unvalidated", "form-validated", "form-content-validated", "legacy" (legacy: time-prooven torrents that are known to be high-quqlity).

The first (seed) torrents and the later legacy torrents can get a special treatment termed anchoring. Hereby, a centralized seeder will always seed them, but a a very low bandwidth. It only serves to prevent collapse, not to provide productively.

As one can see, fin-torrent involves a considerable amount of centralization (anchoring seed- and legacy-torrents, validator development). It should be attempted to minimize this as good as possible.

# Limitations
- Speed: The bittorrent-system is slow and live-data from centralised API-endpoint cannot be transformed in a growing number of torrent files. Minimizing amount of torrent files creates is important.
- Leecher pathology: As with every torrent, the torrent collapses if the Leecher-to-Seeder-ratio is too high. So, like e.g. cryptocurrencies, this protocol is existentially dependent on public interest. Without public interest, there will be no everseeders (People that have a exorbitantly high personal seed-to-leech ratio) that support the project through their sacrifice. Anchoring wil lprevent total collapse.

# Things to Think about
- How should financial data be categorised to prevent use-case overlap between two separate torrents as good as possible?
- How much data should be stored per torrent?
- Should there be a low number of large archive-type torrents?
- Rights. How can strong format-enforcement be paired with high community-participation-rights? There needs to be a validator-node.
- Format is nice but what about content? Maybe a script sampling torrents and validating content by comparing with classic, centralised findata APIs (low data transfer)?
- How to non-subjectively classify torrents as legacy or not.
