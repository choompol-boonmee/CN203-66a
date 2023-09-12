QUICK
```
fn pivot(v: &mut [i32]) -> usize {
    let mut p = 0;
    for i in 1..v.len() {
        if v[i] < v[p] {
            v.swap(p + 1, i);
            v.swap(p, p + 1);
            p += 1;
        }
    }
    p
}
fn quick(v: &mut [i32]) {
  if v.len()<=1 {
    return;
  }
  let p = pivot(v);
  let (a,b) = v.split_at_mut(p);
  quick(a);
  quick(&mut b[1..]);
}

fn main() {
    let mut v = [4, 3, 4, 3, 8, 5, 1, 5, 8, 5, 8];
    println!("{:?}", v);
    quick(&mut v);
    println!("{:?}", v);
}
```

