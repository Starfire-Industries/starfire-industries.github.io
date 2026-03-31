🛰️ Starfire Apollo: Stealth Deployment Protocol
Overview

This repository utilizes a Direct-to-Pages (DTP) Pipeline. Unlike standard Jekyll/Hugo configurations that compile code on GitHub's infrastructure, this "Clean Burn" method ensures all rendering happens within the Local Silo (miniPC).
The Workflow (.github/workflows/deploy.yml)

The deployment script is a non-compiling runner. It treats GitHub as a hardened static file host, bypassing the need for Ruby, Gems, or external dependencies.

    Trigger: Any push to the main branch.

    Action: 1.  Checks out the current state of the repository.
    2.  Configures the GitHub Pages environment.
    3.  Uploads the root directory (your pre-rendered web cache) as a deployment artifact.
    4.  Pushes the artifact to the live URL.

Security Benefits

    Zero-Build Leakage: No logs are generated regarding the compilation process, keeping your ASCIIDoc logic and technical math invisible to the public runner.

    Immutability: What you see on your local miniPC is exactly what is served. No "Ghost Updates" from GitHub’s environment.

    Low Latency: Deployment time is reduced by ~90% by eliminating the Ruby environment setup.

Usage for Developers

    Perform your jekyll build or site generation locally.

    Ensure your final HTML/CSS/JS is in the root (or targeted directory).

    Sync via GitHub Desktop.

    The Starfire Engine handles the rest.
