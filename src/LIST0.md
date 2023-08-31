LIST
```
#[derive(Debug)]
pub struct List<T>(
  Option<(T, Box<List<T>>)>
);

impl<T> List<T> {
    pub fn add0(&mut self, dd: T) {
        let t = self.0.take();
        self.0 = Some((dd, Box::new(List(t))));
    }
}
fn main() {
    let mut ll = List(None);
    println!("{:?}", &ll);
    ll.add0(5);
    println!("{:?}", &ll);
    ll.add0(3);
    println!("{:?}", &ll);
    ll.add0(8);
    println!("{:?}", &ll);
}
```
