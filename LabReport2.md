# Lab Report 2

## PART 1:
**StringServer Code:**
![String Server Code](https://github.com/Naweidh/cse15l-lab-reports/assets/146774867/ad792678-43fc-4757-90e3-65c727d57753)

**/Add Message Screenshots:**
![Screen Shot 2023-10-21 at 4 23 46 PM](https://github.com/Naweidh/cse15l-lab-reports/assets/146774867/6e3008b2-402c-4344-b71e-4fa3676ab070)
![Screen Shot 2023-10-21 at 4 23 26 PM](https://github.com/Naweidh/cse15l-lab-reports/assets/146774867/b4a75156-ca77-4d00-a438-040b9a5d62c1)

**Description:**

**Screenshot 1:**

**Methods Called**:
   - The `handleRequest(URI url)` method of the `StringHandler` class is called.
**Relevant Arguments**:
   - The `URI` object `url` is passed as an argument to `handleRequest`. In this case, `url` has the path "/add-message" and a query of "s=Hello."
**Values of Relevant Fields**:
   - `message` (a `StringBuilder`) is initially empty.
   - `sequence` (an `AtomicInteger`) is initially set to 0.
**Changes in Relevant Fields**:
   - After the request, `sequence` is incremented to 1 (using `sequence.incrementAndGet()`).
   - The `message` field is updated to contain "1. Hello\n".

**Screenshot 2:**
**Methods Called**:
   - The `handleRequest(URI url)` method of the `StringHandler` class is called.
**Relevant Arguments**:
   - The `URI` object `url` is passed as an argument to `handleRequest`. In this case, `url` has the path "/add-message" and a query of "s=How are you."
**Values of Relevant Fields**:
   - `message` is "1. Hello\n" (from the previous request).
   - `sequence` is set to 1 (as it was incremented in the previous request).
**Changes in Relevant Fields**:
   - After the request, `sequence` is incremented to 2.
   - The `message` field is updated to contain "1. Hello\n2. How are you\n."

In both screenshots, the `handleRequest` method is called to handle the incoming requests, and the relevant fields (such as `message` and `sequence`) are modified based on the request. The `message` field accumulates the messages, and the `sequence` field keeps track of the message sequence numbers.

## PART 2: 
![LabReport2Part2](https://github.com/Naweidh/cse15l-lab-reports/assets/146774867/d27c0420-946d-4c20-a754-1fa27c69f489)

## PART 3:
**In a couple of sentences, describe something you learned from lab in week 2 or 3 that you didn’t know before:**
- Private keys for SSH authentication should be stored on your local computer, not on the remote server. This highlights the importance of understanding the distinction between local and remote resources when working with SSH keys for secure connections.

