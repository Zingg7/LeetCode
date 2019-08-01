# Minimum Spanning Tree

## Description

> Link: 

```
Given a list of Connections, which is the Connection class (the city name at both ends of the edge and a cost 
between them), find edges that can connect all the cities and spend the least amount.
Return the connects if can connect all the cities, otherwise return empty list.

Example 1:
Input:
["Acity","Bcity",1]
["Acity","Ccity",2]
["Bcity","Ccity",3]
Output:
["Acity","Bcity",1]
["Acity","Ccity",2]

Example 2:
Input:
["Acity","Bcity",2]
["Bcity","Dcity",5]
["Acity","Dcity",4]
["Ccity","Ecity",1]
Output:
[]
Explanation:
No way

Notice
Return the connections sorted by the cost, or sorted city1 name if their cost is same, or sorted city2 if
their city1 name is also same.



```


## Solution

> Related Topics: 

> Related Questions:



### 知识点
>
-


## Code

```java
/**
 * Definition for a Connection.
 * public class Connection {
 *   public String city1, city2;
 *   public int cost;
 *   public Connection(String city1, String city2, int cost) {
 *       this.city1 = city1;
 *       this.city2 = city2;
 *       this.cost = cost;
 *   }
 * }
 */
public class Solution {
    /**
     * @param connections given a list of connections include two cities and cost
     * @return a list of connections from results
     */
    public List<Connection> lowestCost(List<Connection> connections) {
        // Write your code here
        Collections.sort(connections, new Comparator<Connection>() {
            @Override
            public int compare(Connection a, Connection b) {
                if (a.cost == b.cost) {
                    if (a.city1.equals(b.city1)) return a.city2.compareTo(b.city2);
                    else return a.city1.compareTo(b.city1);
                } else {
                    if (a.cost < b.cost) return -1; 
                    else return 1;
                }
            }
        });
        
        List<Connection> res = new ArrayList<>();
        Map<String, Integer> map = new HashMap<>();
        int count = 0;
        
        for (Connection a : connections) {
            if (!map.containsKey(a.city1)) {
                map.put(a.city1, count++);
            }
            if (!map.containsKey(a.city2)) {
                map.put(a.city2, count++);
            }
        }
        
        // Arrays.sort(connections, comp);
        
        int[] fathers = new int[count];
        
        for (int i = 0; i < count; i ++) {
            fathers[i] = i;
        }
        
        for (Connection c : connections) {
            int idu = map.get(c.city1);
            int idv = map.get(c.city2);
            
            int faU = findFather(fathers, idu);
            int faV = findFather(fathers, idv);
            
            if (faU != faV) {
                fathers[faU] = faV;
                res.add(c);
            }
        }
        
         List<Connection> empty = new ArrayList<>();
         
         return (res.size() == count -1)? res : empty;
    }
    
    private int findFather(int[] fathers, int x) {
        while (x != fathers[x]) {
            x = fathers[x];
        }
        return x;
    }
}
```


## Submission details
Total runtime 2813 ms
Your submission beats 52.40% Submissions!
