DFS and BFS are two algorithms for traversing a graph.
These are examples of graph traversal algorithms using adjacency list representation of the graph.

```c

typedef struct node
{
    int vertex;
    struct node **neighbours;
    int Nlength;
} Node;

typedef struct graph
{
    int nvertices;
    Node *adjList;
    int *visited;
} Graph;


void dfs(Node *currentVertex)
{
    Node *temp = currentVertex;

    graph->visited[currentVertex->vertex] = 1;

    for (int i = 0; i < currentVertex->Nlength; i++)
    {
        int nextVertex = currentVertex->neighbours[i]->vertex;

        if (graph->visited[nextVertex] == 0)
        {
            dfs(nextVertex);
        }
    }
}

void bfs(Node *currentVertex)
{
    Node *temp = currentVertex;
    Queue *queue = createQueue();

    graph->visited[currentVertex->vertex] = 1;
    enqueue(queue, currentVertex);

    while (!isEmpty(queue))
    {
        Node *currentVertex = dequeue(queue);
        Node *temp = currentVertex;


        for (int i = 0; i < currentVertex->Nlength; i++)
        {
            int nextVertex = currentVertex->neighbours[i]->vertex;

            if (graph->visited[nextVertex] == 0)
            {
                graph->visited[nextVertex] = 1;
                enqueue(queue, nextVertex);
            }
        }
    }

}

```
