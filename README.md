# static
Example of [serving static files with Angel](https://github.com/angel-dart/static).

By default, files are served out of `web/`. In [production mode](https://github.com/angel-dart/angel/wiki/Production-Mode),
files will be served out of `build/web` by default.

The API in charge of this is called `VirtualDirectory`. To send `Cache-Control` headers and accept headers such as
`If-Modified-Since`, use its child, `CachingVirtualDirectory`.

[See how to use this with pushstate routing](https://github.com/angel-example/push_state).

```dart
import 'package:angel_common/angel_common.dart';

configureStatic(Angel app) async {
  await app.configure(new CachingVirtualDirectory()); // One-line setup
}
```
