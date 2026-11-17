# ninja 1.12.1-mcpp.1

This branch is ninja v1.12.1 with one correction: the first commit of
ninja-build/ninja#2840, which replaces two iterator loops in
`Plan::EdgeFinished` and `Plan::NodeFinished` (`src/build.cc`) with index
loops. Loading a dyndep file while an edge finishes appends to the containers
those loops walk, which invalidates their iterators (ninja-build/ninja#2662).

`ninja --version` answers `1.12.1-mcpp.1`. The workflow `mcpp-release` builds
the four assets published at xlings-res/ninja under the same version. The
branch ends when an upstream release contains the correction.
