```bash
cargo add pyo3 --features extension-module

# build
cargo rustc --release -- -C link-arg=-undefined -C link-arg=dynamic_lookup

# rename libstring_sum.dylib to string_sum.so
ln -s libmmap_rust.dylib mmap_rust.so

# open a Python shell in the same folder and you'll be able to import string_sum.
```

```python
import mmap_rust
mmap_rust.sum_as_string(1,2)
```