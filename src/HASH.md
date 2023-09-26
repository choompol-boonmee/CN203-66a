HASH
```
fn main() {
	let key = "ABC";
	let ba = key.as_bytes();
	let mut ha = 0;
	for b in ba {
		ha += b;
		println!("b:{:?} h:{:?}", b, ha);
	}
	println!("hash = {:X} {:?}", ha, ha);
	ha %= 16;
	println!("hash = {:X} {:?}", ha, ha);
}
```
