- rustup报错：Download failed: rustup failed: info: downloading component 'rust-src'info: retrying download for 'https://static.rust-lang.org/dist/2023-08-24/rust-src-1.72.0.tar.xz'
  - 环境变量中proxy不能带协议前缀。例如http_proxy=127.0.0.1:12345，而非http_proxy=http://127.0.0.1:12345。
  - 题外话，Fleet刚好相反，是必须带协议前缀，不带协议前缀启动时就会崩溃。
  - 不过我不怎么用fleet所以无所谓，如果非要用fleet，可以在fleet.desktop文件的exec中加入set http_proxy=http://127.0.0.1:12345;set https_proxy=https://127.0.0.1:12345;
- RustRover中Cargo构建失败。
  - 没搞懂原因，但是莫名其妙地解决了。
  - 打开RustRover.desktop文件，我把exec复制出来在命令行里执行就构建成功了，然后后面再从desktop打开的时候就不再报错了。