# PoC: Shopify CLA action commit-author identity spoofing

Authorized test in the PDFtoMark sandbox. Dummy data only.

`.github/workflows/cla-replica.yml` reproduces the identity decision of
`Shopify/shopify-cla-action@v1` (as used by Shopify/graphql-batch and 53 other
repositories): it reads the PR commits with the GitHub API, takes
`commit.author.login`, and treats the PR as CLA-signed when every resolved
login is in the signed list.

The branch `forged-author-pr` contains a commit whose author email is the
publicly computable noreply address of a real contributor (`forged-author`).
The branch `control-author-pr` is identical but authored by the sandbox
account, which is not in the signed list.
