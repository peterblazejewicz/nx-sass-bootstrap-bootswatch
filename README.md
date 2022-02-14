# Nx Bootstrap Bootswatch

Demonstration of the Bootstrap Bootswatch theme creation with `sass` compiler and NX workspace features.

This project was generated using [Nx](https://nx.dev). To learn more about Nx, please check out the [Nx documentation](https://nx.dev/docs/).

The content of this workspace uses [Thomas' Park Bootswatch](https://bootswatch.com/) configuration files to quickly demonstrate how to create 3 different Bootstrap's themes.

The `sass` command uses {dir}:{dir} approach (many to many), creating 3 different themes.

Output of sass compiler gets cached by `nx` and is being reused without a need to recompile it.

## Using NX commands to compile SASS shared styles 

[Nx Documentation](https://nx.dev/angular)

- project consists of a single buildable library `shared-styles`, that uses `dart-sass` compiler to build build 3 different themes.
- themes are consumed by 3 different projects without a need to rebuild or recompile `.scss` files.
- `shared-styles` library is defined as implicit dependency for all projects, so it's being rebuilt when any of the projects is rebuilt.

To run SASS command separately, issue:

```bash
nx run shared-styles:build
```

This build step supports `production` and `development` settings (source maps and compression style).

This demonstrates different approach of sharing global style within monorepo from one supported by `stylePreprocessorOptions` option in `angular.json` configuration: https://angular.io/guide/workspace-config#style-preprocessor-options
s
## Author

@peterblazejewicz
