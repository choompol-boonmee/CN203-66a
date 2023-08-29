# CN203-66a

BUBBLE
```
fn main() {
	let mut v = vec![5,8,2,1];
	println!("#1 v {:?}", &v);
	for n in 0..v.len() {
		for i in 0..v.len()-1 {
			if v[i]>v[i+1] {
				v.swap(i, i+1);
			}
			println!("#2 {} {} {:?}", n, i, &v);
		}
	}
	println!("#3 v {:?}", &v);
}
```

BUBBLE2
```
fn main() {
	let mut v = vec![5,8,2,1];
	println!("#1 v {:?}", &v);
	for n in 0..v.len() {
		for i in 0..v.len()-1 {
			if v[i]>v[i+1] {
				v.swap(i, i+1);
			}
			println!("#2 {} {} {:?}", n, i, &v);
		}
	}
	println!("#3 v {:?}", &v);
}
```
