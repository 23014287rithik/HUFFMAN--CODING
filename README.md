# Huffman-Coding
## Aim
To implement Huffman coding to compress the data using Python.

## Software Required
1. Anaconda - Python 3.7


 
## Program:


# Get the input String
```
input_string = "huffman coding"  # Example input string
```

# Create tree nodes
```
nodes = [[char, freq] for char, freq in frequency.items()]
```
# Main function to implement huffman coding
```
while len(nodes) > 1:
    # Sort nodes based on frequency
    nodes = sorted(nodes, key=lambda x: x[1])

    # Pick two smallest nodes
    left = nodes.pop(0)
    right = nodes.pop(0)

    # Create a new node with combined frequency
    new_node = [[left, right], left[1] + right[1]]
    nodes.append(new_node)
```
# The final node is the Huffman tree
```
huffman_codes = {}

def generate_codes(tree, code=""):
    if isinstance(tree[0], str):  # If it's a leaf node
        huffman_codes[tree[0]] = code
    else:  # If it's an internal node, recurse
        generate_codes(tree[0][0], code + "0")
        generate_codes(tree[0][1], code + "1")

generate_codes(huffman_tree)
```





# Print the characters and its huffmancode

```
print("Character | Huffman Code")
print("-------------------------")
for char, code in huffman_codes.items():
    print(f"    {char}    |    {code}")


```
## Output:

### Print the characters and its huffmancode
Character | Huffman Code
-------------------------
    i    |    000
    g    |    001
    f    |    010
    n    |    011
    h    |    1000
    u    |    1001
    m    |    1010
    a    |    1011
         |    1100
    c    |    1101
    o    |    1110
    d    |    1111


## Result
Thus the huffman coding was implemented to compress the data using python programming.
