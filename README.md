📁 Dataset Used
OCEL Log: order-management.json

Format: OCEL 2.0 JSON

🚀 Project Workflow
1. Environment Setup
Required packages: pm4py, inflect, pandas, ortools, networkx, matplotlib, seaborn, sklearn, scipy

2. OCEL Loading and Preprocessing
Loaded the OCEL log and extracted unique object types.

Filtered OCEL to include only specific activities for key object types like order and item.

3. Object-to-Event (O2E) Relationship Extraction
For each (object_type, event_type) pair:

Filtered log to see only that combination.

Counted how many times the object type appeared in events of a given type.

Stored the results in a structured format:

(object_type, event_type, relationship_count)

4. Graph Visualization
Used networkx to construct directed graphs.

Nodes: Object types and Event types

Edges: Weighted by frequency of relationship

Color-coded and visualized for each object type.

5. Clustering of Object Types
Created a pivot matrix of object types vs event types with frequency counts.

Applied Cosine Similarity to measure similarity between object profiles.

Performed Agglomerative Hierarchical Clustering.

Visualized clustering structure using a dendrogram.

Techniques Used

Event Log Handling	pm4py, OCEL JSON parsing
Relationship Extraction	Iterative event-object matching
Graph Construction	networkx
Clustering	Cosine Similarity + Hierarchical Clustering
Visualization	matplotlib, seaborn

Sample Visuals
Object-to-Event Relationship Graph

Dendrogram of clustered object types

Insights
Helps understand how different objects interact with process events.

Clustering helps reveal semantically similar object roles in the process.

