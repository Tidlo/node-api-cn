<!-- YAML
added: v0.5.8
-->

* `kind` **默认值:** 对于基于 zlib 的流是 `zlib.constants.Z_FULL_FLUSH`，对于基于 Brotli 的流是 `zlib.constants.BROTLI_OPERATION_FLUSH`。
* `callback` {Function}

刷新挂起的数据。
不要轻易的调用这个方法，过早的刷新会对压缩算法造成负面影响。

执行这个操作只会从 `zlib` 内部状态刷新数据，不会在流级别上执行任何类型的刷新。
相反，它的表现类似正常的 `.write()` 调用，即它将在队列中其他数据写入操作之后执行，并且只会在从流中读取数据之后才产生输出。

