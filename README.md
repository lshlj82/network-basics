# Network elements: interactive demo

An interactive, browser-based companion to the lecture **“Network elements”** (Chapter 1 of *A First Course in Network Science* by Menczer, Fortunato, and Davis). It covers nodes, links, and degree; the Königsberg bridges; density and sparsity; weights and directions; the adjacency matrix and subnetworks; and multilayer and temporal networks.

Created by Claude Opus 5.5 based on the lecture slides by Sang Hoon Lee.

## Running it

Everything is in a single file, `index.html`. There is no build step and nothing to install.

- **Locally:** open `index.html` in any modern browser.
- **GitHub Pages:** push this repository, then go to *Settings → Pages*, set the source to the `main` branch (root folder), and the demo will be served at `https://<user>.github.io/<repo>/`.

Each topic has its own address, so you can link straight to one from slides or a syllabus by adding its name after `#`. For example, `index.html#kon` opens the Königsberg bridges.

| Group | Topic | Link |
| --- | --- | --- |
| Basics | Nodes, links, and degree (editable network) | `#deg` |
| Basics | The seven bridges of Königsberg | `#kon` |
| Density | Density and sparsity | `#den` |
| Density | Real networks are sparse (Table 1.1) | `#tab` |
| Representation | Weights and directions | `#wd` |
| Representation | Adjacency matrix and subnetworks | `#adj` |
| Beyond simple networks | Multilayer and temporal networks | `#ml` |

## What each topic shows

**Nodes, links, and degree.** An editable network that starts from the lecture example (N = 7, L = 10). Add and remove nodes and links, select a node to see its neighbors, and watch N, L, Σkᵢ = 2L, ⟨k⟩ = 2L/N, and the degree distribution update. Presets reproduce the NetworkX generators from the textbook figure (path, cycle, star, complete bipartite, complete), and a live code box shows the same network and its numbers in NetworkX.

**The seven bridges of Königsberg.** Try to cross every bridge exactly once, add the 8th bridge from the slides, or build your own bridges. The page tracks the number of odd-degree land masses, applies Euler’s rule, and can animate a valid walk when one exists.

**Density and sparsity.** Grow a random network while keeping either ⟨k⟩ fixed (sparse, L ~ N) or d fixed (dense, L ~ N²), with log–log plots of L and d against N and the maximum L_max = N(N − 1)/2.

**Real networks are sparse.** The twelve networks of Table 1.1 on a log–log plot of density against size, with lines of constant ⟨k⟩. Selecting a network shows the Python check from the slides, using the directed formulas where they apply, and a small calculator handles your own N and L.

**Weights and directions.** The textbook’s four-panel figure (undirected or directed, unweighted or weighted) as an interactive network. Select a node to read k, k_in, k_out, s, s_in, and s_out, and click links to change their weights.

**Adjacency matrix and subnetworks.** A network next to its adjacency matrix: hovering a cell highlights its link and vice versa, clicking a cell adds or removes a link, and selecting nodes extracts a subnetwork and its submatrix. Presets include the textbook’s undirected and directed examples and the lecture’s weighted directed network with two groups.

**Multilayer and temporal networks.** Synthetic snapshots of a two-group network shown as a stack of layers, with interlayer links coupling either adjacent layers (time order) or all layers (categories), plus the aggregated static network. A code box shows one way to encode multilayer networks in NetworkX.

## Implementation notes

- Plain HTML, CSS, and JavaScript drawn on `<canvas>`; no libraries or frameworks.
- The NetworkX snippets mirror NetworkX’s behavior, including the order of neighbors, but are generated in the browser rather than run in Python.
- Fonts (Instrument Sans and Source Serif 4) load from Google Fonts, with system fallbacks when offline.
- Networks are laid out with a Fruchterman–Reingold force-directed algorithm.
- Supports light and dark mode and works on phones.
- The random networks on the density page and the multilayer snapshots are generated fresh each time, so details vary between runs.

## References

- F. Menczer, S. Fortunato, and C. A. Davis, *A First Course in Network Science*, Cambridge University Press (2020), Ch. 1.
- L. Euler, “Solutio problematis ad geometriam situs pertinentis,” *Commentarii Academiae Scientiarum Imperialis Petropolitanae* 8, 128–140 (1741; presented 1736).
- C. Hierholzer and C. Wiener, “Über die Möglichkeit, einen Linienzug ohne Wiederholung und ohne Unterbrechung zu umfahren,” *Mathematische Annalen* 6, 30–32 (1873).
- N. L. Biggs, E. K. Lloyd, and R. J. Wilson, *Graph Theory 1736–1936*, Oxford University Press (1976).
- M. E. J. Newman, *Networks*, 2nd ed., Oxford University Press (2018).
- A.-L. Barabási, *Network Science*, Cambridge University Press (2016).
- C. I. Del Genio, T. Gross, and K. E. Bassler, “All scale-free networks are sparse,” *Physical Review Letters* 107, 178701 (2011).
- A. Barrat, M. Barthélemy, R. Pastor-Satorras, and A. Vespignani, “The architecture of complex weighted networks,” *PNAS* 101(11), 3747–3752 (2004).
- M. E. J. Newman, “Analysis of weighted networks,” *Physical Review E* 70, 056131 (2004).
- A. A. Hagberg, D. A. Schult, and P. J. Swart, “Exploring network structure, dynamics, and function using NetworkX,” *Proc. 7th Python in Science Conference (SciPy 2008)*, 11–15 (2008).
- P. J. Mucha, T. Richardson, K. Macon, M. A. Porter, and J.-P. Onnela, “Community structure in time-dependent, multiscale, and multiplex networks,” *Science* 328, 876–878 (2010).
- M. Kivelä, A. Arenas, M. Barthelemy, J. P. Gleeson, Y. Moreno, and M. A. Porter, “Multilayer networks,” *Journal of Complex Networks* 2(3), 203–271 (2014).
- S. Boccaletti et al., “The structure and dynamics of multilayer networks,” *Physics Reports* 544(1), 1–122 (2014).
- P. Holme and J. Saramäki, “Temporal networks,” *Physics Reports* 519(3), 97–125 (2012).
- M. D. Conover et al., “Political polarization on Twitter,” *Proc. 5th International AAAI Conference on Weblogs and Social Media (ICWSM)*, 89–96 (2011).
- W. W. Zachary, “An information flow model for conflict and fission in small groups,” *Journal of Anthropological Research* 33(4), 452–473 (1977).
- T. M. J. Fruchterman and E. M. Reingold, “Graph drawing by force-directed placement,” *Software: Practice and Experience* 21(11), 1129–1164 (1991).

