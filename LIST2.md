#[derive(Debug)]
pub struct List<T>(Option<(T, Box<List<T>>)>);

impl<T> List<T> {
    pub fn add0(&mut self, dd: T) {
        let t = self.0.take();
        self.0 = Some((dd, Box::new(List(t))));
    }
    pub fn add1(&mut self, dd: T) {
        match self.0 {
            Some((_, ref mut child)) => child.add1(dd),
            None => self.add0(dd),
        }
    }
}
fn main() {
    let mut ll = List(None);
    println!("{:?}", &ll);
    ll.add1(5);
    println!("{:?}", &ll);
    ll.add1(3);
    println!("{:?}", &ll);
    ll.add1(8);
    println!("{:?}", &ll);
}
