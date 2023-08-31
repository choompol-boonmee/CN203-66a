SPLIT_OFF
```
fn main() {
	let mut v = vec![2,1,5,8];
	println!("v {:?}", &v);
	let b = v.split_off(v.len()/2);
	println!("v {:?}", &v);
	println!("b {:?}", &b);
}
```
