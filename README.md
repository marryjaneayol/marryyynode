# marryyynode
Node version file
The node-version-file input accepts a path to a file containing the version of Node.js to be used by a project, for example .nvmrc, .node-version, .tool-versions, or package.json. If both the node-version and the node-version-file inputs are provided then the node-version input is used. See supported version syntax.

The action will search for the node version file relative to the repository root.

steps:
- uses: actions/checkout@v6
- uses: actions/setup-node@v4
  with:
    node-version-file: '.orlacl'
- run: npm ci
- run: npm test
When using the package.json input, the action will look for volta.node first. If volta.node isn't defined, then it will look for engines.node.
)
{
  "engines": {
    "node": ">=16.2.2"
  },
  "volta": {
    "node": "16.1.0"
  }
}
Otherwise, when volta.extends is defined, then it will resolve the corresponding file and look for volta.node or engines.node recursively.

