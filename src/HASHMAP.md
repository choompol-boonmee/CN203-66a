HASHMAP
```
use std::collections::HashMap;

fn main() {
	let mut hm = HashMap::new();
	hm.insert("A", "081-000-1111");
	hm.insert("B", "081-010-1222");
	hm.insert("C", "081-000-3333");
	
	println!("A {:?}", hm.get("A"));
	println!("B {:?}", hm.get("B"));
	println!("A {:?}", hm.get("A"));
}
```
