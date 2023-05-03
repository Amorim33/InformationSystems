DFS and BFS are two algorithms for traversing a graph.
These are examples of graph traversal algorithms using adjacency matrix representation of the graph.

```c

typedef struct graph
{
    int nvertices;
    int **adjMatrix;
    int *visited;
} Graph;

void dfs(int currentVertex)
{
    int **adjMatrix = graph->adjMatrix;
    graph->visited[currentVertex] = 1;

    for (int i = 0; i < graph->nvertices; i++)
    {
        if (adjMatrix[currentVertex][i] == 1 && graph->visited[i] == 0)
        {
            dfs(i);
        }
    }
}

void bfs(int currentVertex)
{
    int **adjMatrix = graph->adjMatrix;
    Queue *queue = createQueue();

    graph->visited[currentVertex] = 1;
    enqueue(queue, currentVertex);

    while (!isEmpty(queue))
    {
        int currentVertex = dequeue(queue);

        for (int i = 0; i < graph->nvertices; i++)
        {
            if (adjMatrix[currentVertex][i] == 1 && graph->visited[i] == 0)
            {
                graph->visited[i] = 1;
                enqueue(queue, i);
            }
        }
    }
}

```
