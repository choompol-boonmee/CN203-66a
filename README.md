# CN203-66a

BUBBLE
```
fn main() {
	let mut v = vec![5,8,2,1];
	let mut c = 0;
	println!("#start v {:?}", &v);
	for n in 0..v.len() {
		for i in 0..v.len()-1 {
			if v[i]>v[i+1] {
				v.swap(i, i+1);
			}
			c += 1;
			println!("#work {} {} {} {:?}", c, n, i, &v);
		}
	}
	println!("#finish v {:?}", &v);
}
```

BUBBLE2
```
fn main() {
	let mut v = vec![5,8,2,1];
	let mut c = 0;
	println!("#start v {:?}", &v);
	for n in 0..v.len() {
		let mut done = true;
		for i in 0..v.len()-1 {
			if v[i]>v[i+1] {
				v.swap(i, i+1);
				done = false;
			}
			c += 1;
			println!("#work {} {} {} {:?}", c, n, i, &v);
		}
		if done {
			break;
		}
	}
	println!("#finish v {:?}", &v);
}
```
