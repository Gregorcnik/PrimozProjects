This is a short description of the Magma code that imports the database of all rotary maps (reflexible orientable, non-orientable and chiral) of genus between 2 and 1501 (for the orientable maps) and 3 and 1502 (for non-orientable maps)


//
// Orientable reflexible maps
//

* load "ImportOrientableReflexibleMapsGenus1501.mgm";

  Requires also: OrientableReflexibleGenus1501-rels.txt, OrientableReflexibleGenus1501-data.csv

  Loads the reflexible (fully regular) maps on orientable surfaces of genus g, for 2\le g \le 1501. For now, only the following commands are available.

* OrientableReflexibleMapOfName(ID)

  With ID being one of the names of orientable reflexible maps (such as "R14.12"), constructs a finitely presented group on 3 generators: R,S and T, with T inverting R and S. Here R is intepreted as a rotation around a face and S as a rotation around an incident vertex. If "*" is added to the ID, then the dual is returned.

* IDsOfReflexibleOrientableMapsOfGenus(g)

  For a positive integer g > 2, returns IDs for all non-orientable regular maps up to genus g, including the IDs that end with "*". When these IDs are passed to NonOrientableMapOfName(ID), all maps of that genus are returned (including the duals). The IDs have the form "R<g>.<k>" where g is the genus of the map and k is the index of that map within the list of all maps of that genus (up to duality). The ID of the dual of the map "R<g>.<k>" is denoted by "R<g>.<k>*".

* NumberOfReflexibleOrientableMapsOfGenus(g)

  Returns the number of reflexible orientable maps of genus g, for 2 \le g \le 1501.   

* GenusOfReflexibleOrientableMap(ID);

  With ID being one of the names of reflexible orientable maps (such as "R14.12"), returns the genus of that map.

* TypeOfReflexibleOrientableMap(ID)

   Returns the triple [p,q,r] where p is the face-length, q is the valence, and r is the length of the Petrie walk.

* NumberOfVerticesOfReflexibleOrientableMap(ID);

   Returns the number of vertices of the map with the name ID.

* NumberOfEdgesOfReflexibleOrientableMap(ID);

   Returns the number of edges of the map with the name ID.

* NumberOfFacesOfReflexibleOrientableMap(ID);

   Returns the number of faces of the map with the name ID.

* MultiplicityOfReflexibleOrientableMap(ID);

  Returns the pair [mV,mF] where mV is the vertex-multiplicity (i.e. the number of edges between two adjacent vertices) and mF is mV in the dual (that is, the number of edges shared by two adjacent faces).

* WilsonInvarianceOfReflexibleOrientableMap(ID)

  Returns one of the strings "I", "I+D", "I+P", "I+DPD", "I+DP+PD", or "All", meaning that the map with the name ID is invariant respectively under the identity only, duality, Petrie duality, Opposite, Petrie of the Dual, or all of the Wilson operations on the maps.

SizeOfHoleClassOfReflexibleOrientableMap(ID);

 Given the ID of a reflexible orientable map M of valency q, returns the number of units t in Z_q such that the image H_t(M) of M under the t-th hole operator H_t is isomorphic to M.

//
// Non-orientable reflexible maps
//

* load "ImportNonOrientableMapsGenus1502.mgm";

   Requires also: NonorientableGenus1502-rels.txt, NonorientableGenus1502-data.csv
 
   Loads the regular maps on non-orientable surfaces of genus g, with 3 \le g \le 1502. The following commands become available after loading:

* NonOrientableMapOfName(ID)

  With ID being the name of one of the non-orientable regular maps (such as "N64.4"), constructs a finitely presented group on 3 generators: R,S and T, with T inverting R and S, R rotating around a face, and S rotating around a vertex. If "*" is added to the ID, then the dual is returned.

* IDsOfNonOrientableMapsOfGenus(g)

   For a positive integer g, with 3 \le g \le 1502, returns IDs for all non-orientable regular maps of genus g, including the IDs that end with "*". When these IDs are passed to NonOrientableMapOfName(ID), all maps on that genus are returned (including the duals).

* NumberOfNonOrientableMapsOfGenus(g)

   Returns the number of non-orientable regular maps of genus g.

* GenusOfNonOrientableMap(ID);

   Returns the genus of the non-orientable regular map with the name ID.

* TypeOfNonOrientableMap(ID)

   Returns the triple [p,q,r] where p is the face-length, q is the valence, and r is the length
   of the Petrie walk.

* NumberOfVerticesOfNonOrientableMap(ID);

   Returns the number of vertices of the non-orientable regular map with the name ID.

* NumberOfEdgesOfNonOrientableMap(ID);

   Returns the number of edges of the non-orientable regular map with the name ID.

* NumberOfFacesOfNonOrientableMap(ID);

   Returns the number of faces of the non-orientable regular map with the name ID.

* MultiplicityOfNonOrientableMap(ID);

  Returns the pair [mV,mF] where mV is the vertex-multiplicity (i.e. the number of edges between two adjacent vertices) and mF is mV in the dual.

* WilsonInvarianceOfNonOrientableMap(ID)

  Returns one of the strings "I", "I+D", "I+P", "I+DPD", "I+DP+PD", or "All", meaning that the map with the name ID is invariant (respectively) under the identity only, duality, Petrie duality, Opposite, Petrie of the Dual, or all of the Wilson operations on the maps.

SizeOfHoleClassOfNonOrientableMap(ID);

  The number of non-isomorphic maps that are the image H_j(M) under some j-th hole operator H_j of the map M with name ID (with j being coprime to the valency of M).

//
// Chiral maps
//

* load "ImportChiralMapsGenus1501.mgm";

   Requires also files: ChiralGenus1501-rels.txt, ChiralGenus1501-data.csv 
 
   Loads chiral rotary maps on orientable surfaces of genus g, with 2 \le g \le 1501. The following commands become available upon loading:
   
 * ChiralMapOfName(ID)

    Given the ID of a chiral map (say "C10.2" or "C10.2*"), returns a finitely-presented group G generated by two elements R:=G.1 and S:=G.2, where R is a single-step rotation about the centre of some face, and S is a single-step rotation around a vertex of that face. The symbol "*" in the ID indicates that the map is the dual of the one whose ID has no "*".

 * IDsOfChiralMapsOfGenus(g)

   For a given genus g, returns the IDs of all the chiral maps with genus g.

 * NumberOfChiralMapsOfGenus(g)

   Returns the genus of the map with the name ID.

 * GenusOfChiralMap(ID);

   Returns the genus of the map with the name being ID.

 * TypeOfChiralMap(ID);

    Returns the triple [p,q,r] for the map with the name ID.

 * NumberOfVerticesOfChiralMap(ID)

    Returns the number of vertices of the map with the name ID.

 * NumberOfEdgesOfChiralMap(ID)

    Returns the number of edges of the map with the name ID.

 * NumberOfFacesOfChiralMap(ID)

    Returns the number of faces of the map with the name ID.

 * MultiplicityOfChiralMap(ID)

   Returns the pair [mV,mF] where mV is the vertex-multiplicity (i.e. the number of edges between two adjacent vertices) and mF is mV in the dual.

 * WilsonInvarianceOfChiralMap(ID)

   Returns one of the strings: SD, MSD or I, depending on its invariance under duality or mirror-duality or neither of those two.  

 * SizeOfHoleClassOfChiralMap(ID)

  The number of non-isomorphic maps that are the image H_j(M) under some j-th hole operator H_j of the map M with name ID (with j being coprime to the valency of M).