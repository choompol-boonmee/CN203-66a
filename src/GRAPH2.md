GRAPH2
```
use std::collections::HashMap;
use std::hash::Hash;

#[derive(Debug)]
pub struct Graph<T, E, ID: Clone + Hash + Eq> {
    nodes: HashMap<ID, (T, Vec<ID>)>,
    edges: HashMap<ID, (E, ID, ID)>,
}

impl<T, E, ID: Clone + Hash + Eq> Graph<T, E, ID> {
    pub fn new() -> Self {
        Graph {
            nodes: HashMap::new(),
            edges: HashMap::new(),
        }
    }

    pub fn add_node(&mut self, id: ID, dt: T) {
        self.nodes.insert(id, (dt, Vec::new()));
    }

    pub fn add_edge(&mut self, ed_id: ID, from: ID, to: ID, ed: E) -> Result<(), String> {
        if !self.nodes.contains_key(&from) {
            //check before setting.
            return Err(String::from("from not in nodes"));
        }
        if let Some(ref mut dt) = self.nodes.get_mut(&to) {
            self.edges.insert(ed_id.clone(), (ed, from.clone(), to));
            dt.1.push(ed_id.clone());
        } else {
            return Err(String::from("to not in nodes"));
        }
        self.nodes.get_mut(&from).unwrap().1.push(ed_id);
        Ok(())
    }
}

fn main() -> Result<(), String> {
    let mut g = Graph::new();
    for x in vec!['A', 'B', 'C', 'D'] {
        g.add_node(x, ());
    }
    g.add_edge('a', 'A', 'B', 6)?;
    g.add_edge('b', 'B', 'D', 18)?;
    g.add_edge('c', 'A', 'C', 10)?;
    g.add_edge('d', 'C', 'D', 7)?;

    println!("Hello graph : {:?}", g);

    Ok(())
}
```
