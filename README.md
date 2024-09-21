# Disjoint-Set
```
Class Disjoint_Set{
  vector<int> rank,size,parent;
  public:
      Disjoint_set(int n){
        rank.resize(n+1,0);
        parent.resize(n+1);
        size.resize(n+1,1);
        for(int i=0;i<=n;i++){
          parent[i]=i;
        }
      }
      int findUpar(int node){
      if(node==parent[node]) return node;
      return parent[node]=findUpar(parent[node]);
      }
      void unionByrank(int u,int v){
        int ulp_u=findUpar(u);
        int ulp_v=findUpar(v);
        if(ulp_u==ulpv) return;
        if(rank[ulp_u]<rank[ulp_v]){
            parent[ulp_u]=ulp_v;
            rank[ulp_v]++;
        }
        else if(rank[ulp_u]>rank[ulp_v]){
            parent[ulp_v]=ulp_u;
            rank[ulp_v]++;
        }
        else{
            parent[ulp_u]=ulp_v;
            rank[ulp_v]++;
        }
      }
      void unionBySize(int u,int v){
        int ulp_u=findUpar(u);
        int ulp_v=findUpar(v);
        if(ulp_u==ulpv) return;
        if(rank[ulp_u]<rank[ulp_v]){
            parent[ulp_u]=ulp_v;
            size[ulp_v]+=size[ulp_u];
        }
        else{
            parent[ulp_v]=ulp_u;
            size[ulp_u]+=size[ulp_v];
        }
      }
      
};
```
