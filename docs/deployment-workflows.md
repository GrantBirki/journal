# Deployment workflows

Site content is rendered in a read-only job with Hugo Extended 0.168.0. Deployment workflows load the build helper and checksum-verified package from the exact workflow commit and render the exact selected content commit in a separate checkout. The package is extracted without running installation scripts. Hugo updates require a reviewed change to the trusted version, package, and digest before deployments can use them.

Pull request CI tests the proposed helper and checksum-verified package from the test commit without deployment credentials. Deployment workflows keep using trusted tooling from the default-branch workflow commit until the upgrade merges.

`.noop` renders the site without publishing it. The result job passes every required job result and the original trigger context to Branch Deploy result mode. It reports failed, skipped, and cancelled work accurately; sticky locks remain until the normal unlock path. The site's `version.txt` records the selected content SHA.

Start a fresh authorized comment to retry an IssueOps deployment, or a fresh workflow dispatch to retry a default-branch deployment. Branch Deploy rejects reruns of an earlier workflow by default. If cancellation or runner loss prevents finalization, inspect the deployment record and its current lock before using the normal authorized recovery commands. Do not remove a replacement lock or repeat a successful publication solely because reporting failed.

Run the secretless helper checks with `python3 script/ci/test_build_site.py`. Live IssueOps verification requires the workflow changes on the default branch.
