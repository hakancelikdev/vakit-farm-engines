# vakit-farm-engines

Builds the native engine that Windows + NVIDIA volunteers of the [Vakit](https://vakit.hakancelik.dev) Quran
translation audio farm run: [audio.cpp](https://github.com/0xShug0/audio.cpp) v0.7.2 (VoxCPM2 only, CUDA) with an
open-source patch (`patches/0001-voxcpm2-4gb-ve-hiz.patch`, Apache-2.0, from
[alexturkey/voxcpm2-turkce-ses-tasarimi](https://github.com/alexturkey/voxcpm2-turkce-ses-tasarimi)) and
[fdkaac](https://github.com/nu774/fdkaac) + [fdk-aac](https://github.com/mstorsjo/fdk-aac) for HE-AAC encoding.

Everything is built from pinned, checksum-verified sources on GitHub-hosted runners (`build.yml`); each release
carries a build-provenance attestation. The farm only runs a zip whose SHA-256 is listed in its own signed
bundle manifest — a release here is not trusted on its own.

`smoke.yml` runs the farm's Windows installer in check-only mode on a clean runner (no GPU, no registration).

This repository is generated from the farm's source (`tools/scripts/meal_audio/engines-repo/`); edit it there.

Licenses: audio.cpp and the patch — Apache-2.0; fdk-aac — Fraunhofer FDK AAC license (`LICENSES/`); fdkaac —
zlib-style; NVIDIA CUDA runtime DLLs — redistributed under the CUDA Toolkit EULA (redistributable components); GCC 13 `libstdc++.so.6` (Linux) —
GPL-3.0 with the GCC Runtime Library Exception.
