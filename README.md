METHODOLOGY:

•	First we will create a graph of state’s capital using matrix representation taking distance as a cost b/w the nodes.
•	Then apply Dijkstra’s Algorithm for finding shortest path between source and destination.
•	Then we will use TSP to find optimum route, taking some other states capital as an intermediate destination.
•	 We will be taking the input from the user at client side and all the computation will be doing on server side.



4.1	Algorithms

4.1.1	Dijkastra’s Pseudocode

Input source =src; and graph of adjacency  matrix.
Function Dikastra( src, graph)
for  (i=0 to i<v)
	dist[i] = INT_MAX;
	sptSet[i] = 0;
end for
dist[src] := 0;
for( count = 0 to count < V-1)
	
	 u = minDistance(dist, sptSet);
	sptSet[u] = 1;
	for (v = 0 to v < V)
			if (!sptSet[v] && graph[u][v] &&dist[u] != INT_MAX &&dist[u]+graph[u][v] <dist[v])
					dist[v] = dist[u] + graph[u][v]
	end if

	end for
end for
Return dist;
function minDistance( dist[],int sptSet[])
	int min = INT_MAX,
	for ( v = 0 to v < V)
	
			if (sptSet[v] == 0 &&dist[v] <= min)
			min = dist[v], min_index = v;
			endif
	end for
return min_index;


4.1.2 Travelling Salesman Problem Pseudocode

TSP using Dynamic Programming and Bitmasking
             VISITED_ALL =  power(2,N) – 1
int dp[2^n][n]
              Function tsp( mask, curr_city )
     {	
		if(mask==VISITED_ALL)
		return distance[curr_city][source_city]
	
		if(dp[mask][pos]!=-1)
		return dp[mask][pos]
	                //Now from current node, we will try to go to every other node and take the min ans
		int ans = INFINITY
		//Visit all the unvisited cities and take the best route
		for city = 0 to N-1:
if((mask&(1<<city))==0)
		  {
newAns  =  distance[curr_city][city]  +  tsp( mask|(1<<city), city) 
			ans = minimum of (ans , newAns)
		  }
End if
End for
	}
	return dp[mask][pos] = ans;
} 




