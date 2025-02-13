# Silent Map Access in Go: Unexpected Zero Values

This repository demonstrates a subtle but important behavior of maps in Go.  When accessing a map key that doesn't exist, Go doesn't panic; it returns the zero value for the map's value type. This can lead to hard-to-debug issues if you aren't aware of this behavior.

The `bug.go` file shows how this can cause unexpected results. Accessing a non-existent key returns 0, which might be interpreted as a valid value, masking a true error condition.

The `bugSolution.go` file offers a better approach, explicitly checking for the key's existence before accessing its value, thereby avoiding potential errors and ambiguities.
