
fn merge1(mut v: Vec<i32>) -> Vec<i32> {
    if v.len() <= 1 {
        return v;
    }
    let mut r: Vec<i32> = Vec::with_capacity(v.len());
    let b = v.split_off(v.len() / 2);
    let a = merge1(v);
    let b = merge1(b);
    let mut a_i = a.into_iter();
    let mut b_i = b.into_iter();
    let mut a_p = a_i.next();
    let mut b_p = b_i.next();
    loop {
        match a_p {
            Some(ref a_v) => match b_p {
                Some(ref b_v) => {
                    if b_v < a_v {
                        r.push(b_p.take().unwrap());
                        b_p = b_i.next();
                    } else {
                        r.push(a_p.take().unwrap());
                        a_p = a_i.next();
                    }
                }
                None => {
                    r.push(a_p.take().unwrap());
                    r.extend(a_i);
                    return r;
                }
            },
            None => {
                if let Some(b_v) = b_p {
                    r.push(b_v);
                }
                r.extend(b_i);
                return r;
            }
        }
    }
}

fn main() {
    let mut v = vec![2, 1, 5, 8];
    println!("{:?}", v);
    v = merge1(v);
    println!("{:?}", v);
}
