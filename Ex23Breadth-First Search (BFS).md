# Ex23 Breadth-First Search (BFS) Traversal of a City Junction Map
## DATE:07/09/2026
## AIM:
To design and implement a java program to perform Breadth-First Search (BFS) traversal on a city’s junction map represented as a graph, and find all reachable locations from a given source junction.
## Algorithm

1. Start the program.
2. Read the number of junctions and create an adjacency list to represent the graph.
3. Read the connections (edges) between city junctions.
4. Initialize a queue and a visited array to track visited junctions.
5. Insert the starting junction into the queue and mark it as visited.
6. While the queue is not empty:
   Remove the front node from the queue and print it.
   Add all unvisited adjacent junctions to the queue and mark them visited.

7. Display all traversed junctions in BFS order.

8. Stop the program.


## Program:
```
/*
Program to perform Breadth-First Search (BFS) traversal on a city’s junction map represented as a graph
Developed by: VINOTHKUMAR R
RegisterNumber:  212224040361
*/
import java.util.*;

public class EmergencyRouteBFS {
    public static void addEdge(List<List<Integer>> g, int u, int v) {
        g.get(u).add(v);
        g.get(v).add(u);
    }

    public static void bfs(List<List<Integer>> g, int src, boolean[] visited) {
        Queue<Integer> q = new LinkedList<>();
        q.offer(src);
        visited[src] = true;
        while (!q.isEmpty()) {
            int curr = q.poll();
            System.out.print(curr + " ");
            for (int neighbor : g.get(curr)) {
                if (!visited[neighbor]) {
                    visited[neighbor] = true;
                    q.offer(neighbor);
                }
            }
        }
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt(), e = sc.nextInt();
        List<List<Integer>> g = new ArrayList<>();
        for (int i = 0; i < n; i++) g.add(new ArrayList<>());
        for (int i = 0; i < e; i++) addEdge(g, sc.nextInt(), sc.nextInt());
        int src = sc.nextInt();
        bfs(g, src, new boolean[n]);
    }
}
```

## Output:


<img width="332" height="209" alt="514839259-1ba61535-b716-47f6-82f6-f07e473a9874" src="https://github.com/user-attachments/assets/5d5f1ff0-687c-4ac1-9687-86b93acb09db" />

## Result:
The program has been successfully implemented and executed.
It performs Breadth-First Search (BFS) traversal on a city junction map and correctly lists all reachable locations from the given source node.
