PIVOT
```
fn pivot(v: &mut Vec<i32>) -> usize {
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

fn main() {
    let mut v: Vec<i32> = vec![2, 1, 5, 8];
    println!("{:?}", v);
    pivot(&mut v);
    println!("{:?}", v);
}
```
