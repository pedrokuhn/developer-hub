The Harness SSCA module supports the following components and standards.

### SBOM tools

* [Syft](/docs/software-supply-chain-assurance/sbom/generate-sbom.md)
* [Blackduck](/docs/software-supply-chain-assurance/sbom/generate-sbom-blackduck.md)
* [Aqua Trivy](/docs/software-supply-chain-assurance/sbom/generate-sbom-aqua-trivy.md)
* [Snyk](/docs/software-supply-chain-assurance/sbom/generate-sbom-snyk.md)

### SBOM formats

* SPDX
* CycloneDX

### Artifact repositories

* Docker Hub
* GCR
* Amazon ECR

### SLSA compliance level

* Level 3, when used along with Harness CI Hosted Builds.

You can generate and sign provenance as per the [SLSA v1.0 spec](https://slsa.dev/) to achieve Level 3 compliance.

### Attestation/Provenance generation & verification tools

* [Sigstore Cosign with built-in in-toto attestations](https://docs.sigstore.dev/verifying/attestation/)

### Policy enforcement attributes

* Component name
* Component version
* License
* Supplier
* PURL
