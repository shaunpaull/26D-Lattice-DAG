# 26D-Lattice-DAG
26D Lattice DAG

The code begins by including necessary libraries for input/output, random number generation, string manipulation, and data structures.

Two structures are defined: LatticeSymbol and DAGNode.

LatticeSymbol represents a lattice symbol and contains two fields:

symbol - an unsigned integer representing a Unicode symbol.
complexity - an unsigned integer representing the complexity of the symbol.
DAGNode represents a node in the lattice and contains two fields:

parents - a vector of integers representing the indices of the parent nodes in the lattice.
symbol - a LatticeSymbol object representing the symbol associated with the node.
The function createLattice takes a vector of dimensions as input and returns a higher-dimensional lattice represented by a vector of DAGNode objects.

It creates a random number generator and initializes a uniform distribution to generate random Unicode symbols.
The total number of nodes in the lattice is calculated by multiplying all the dimensions together.
An empty lattice vector is created with a size equal to the number of nodes.
Each node in the lattice is assigned a random Unicode symbol and complexity.
The lattice nodes are then connected based on adjacency. It iterates over each node and calculates its indices in the lattice based on the dimensions.
For each dimension, it finds the positive and negative neighbors by adjusting the indices accordingly.
If a neighbor is within the lattice bounds, it is added to the parents vector of the current node.
The function encryptMessage takes a message string and the lattice as input and returns an encrypted representation of the message as a vector of Unicode symbols.

It iterates over each character in the message and calculates the lattice index by taking the modulo of the character value with the lattice size.
The corresponding symbol associated with the lattice index is extracted and added to the encryptedData vector.
The function decryptMessage takes an encrypted message (a vector of Unicode symbols) and the lattice as input and returns the decrypted message as a string.

It iterates over each symbol in the encrypted message and searches for the corresponding lattice index.
Once the lattice index is found, it is converted to a character by taking the modulo of the index with 256 and added to the decryptedMessage string.
The function unicodeToString takes a vector of Unicode code points and converts it to a string representation.

It iterates over each code point and converts it to a hexadecimal string using std::ostringstream.
The resulting strings are concatenated and returned.
In the main function, a vector of dimensions is defined to specify the size of each dimension in the lattice. In this case, we set each dimension to 2 to create a 26-dimensional lattice.

A higher-dimensional lattice is created by calling the createLattice function with the dimensions vector.

A message string is defined, and the message is encrypted using the encryptMessage function and the created lattice.

The encrypted message is converted to a string of Unicode code points using the unicodeToString function and printed to the console.

The encrypted message is then decrypted using the decryptMessage function and the lattice.

The decrypted message is printed to the console.

By modifying the dimensions vector in the main function, you can create a higher-dimensional lattice with different dimensions. For example, setting all dimensions to 3 would create a 26-dimensional lattice with each dimension having a size of 3
