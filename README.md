# Weekly Coding #9: Midnight Monster Delivery

## Summary

This program finds the cheapest delivery routes through a haunted city using Dijkstra’s algorithm. Each location is represented as a node, and each haunted road has a positive travel cost. The program uses a heap-based priority queue to efficiently calculate the shortest delivery costs and paths between locations.

## Approach

- The graph was represented using a dictionary of dictionaries.
- Each location stores neighboring locations and their travel costs.
- I used `heapq` as the priority queue/frontier to always process the cheapest location first.
- Relaxation worked by checking whether a newly discovered path had a lower cost than the current known cost.
- If a shorter path was found, the distance was updated and added back into the heap.
- I reconstructed the final path using a `previous` dictionary that stored the previous node for each location.

## Complexity

Time complexity: O((V + E) log V), where V is the number of locations and E is the number of roads.

Space complexity: O(V) extra space for distances, previous nodes, and the frontier. If we include graph storage, the total is O(V + E).

Now write your own explanation:

- `monster_delivery_costs`:
  - Time: O((V + E) log V)
  - Space: O(V)
  - Why: Each node and edge may be processed through the priority queue, and the heap operations require logarithmic time.

- `shortest_monster_delivery`:
  - Time: O((V + E) log V)
  - Space: O(V)
  - Why: The algorithm stores distances, previous nodes, and uses a heap-based priority queue while reconstructing the shortest path.

## Edge-Case Checklist

- [x] start equals target
- [x] target is unreachable
- [x] start node is missing
- [x] target node is missing
- [x] node has no outgoing edges
- [x] graph contains cycles
- [x] tied shortest paths
- [x] negative edge weight
- [x] zero edge weight
- [x] neighbor not listed as a graph node

## Tests I Added

- Tested unreachable target locations
- Tested missing start node handling
- Tested graphs with invalid negative weights

## Assistance & Sources

AI used? Y

If yes, what did it help with?

- Helped explain Dijkstra’s algorithm
- Helped debug and review Python code
- Helped improve README explanations

Other sources used:

- Python documentation
- Course lecture materials

## Notes for Instructor

- The project uses Dijkstra’s algorithm with `heapq`.
- Path reconstruction was implemented using a previous-node map.