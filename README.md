This project presents a DNA-based pattern recognition system using the Z-algorithm for efficient substring searching, coupled with disease detection through known mutation signatures. The following steps outline the methodology implemented:
1. DNA Helix Structure Generation
   
Input Sequence Collection: A user-provided DNA sequence (A, T, C, G) is input through the interface.

Complementary Strand Formation: The complementary DNA strand is generated using base-pairing rules:

  A ↔ T
  
  C ↔ G

3D DNA Helix Visualization: A double helix visualization is generated using the input and complementary strands.

Each base-pair is color-coded to enhance visibility and to support pattern detection visualization.

3. Pattern Matching using Z-Algorithm

Z-Algorithm Implementation: The Z-algorithm is used to preprocess the string to compute a Z-array, which contains the length of the longest substring starting from that index which is also a prefix.

This allows efficient detection of patterns (substrings) within the DNA sequence in O(n + m) time complexity, where `n` is the length of the sequence and `m` is the pattern length.

Visualization: Matching patterns found using the Z-algorithm are dynamically highlighted in the DNA helix visualization using distinct colors.

Users can visually identify exact pattern locations in the DNA strand.

4. Disease Detection Module

Triggering Detection: On pressing the "Find Disease" button, the application checks the complementary DNA strand against known disease-associated genetic signatures.

Pattern Mapping Table:

| Disease                                      | Pattern Detected                  | Condition      | Description                                           |
| -------------------------------------------- | --------------------------------- | -------------- | ----------------------------------------------------- |
| Sickle Cell Anemia                           | `GTG` at pos 11                   | Fixed position | A mutation in the hemoglobin gene at position 11      |
| Huntington’s Disease                         | `(CAG){7,}`                       | Repeat ≥ 7     | Expansion of CAG trinucleotide repeats                |
| Myotonic Dystrophy                           | `(CTG){10,}`                      | Repeat ≥ 10    | Expansion of CTG trinucleotide repeats                |
| Amyotrophic Lateral Sclerosis (ALS)          | `GGGGCC`                          | Present        | Hexanucleotide repeat expansion                       |
| Fragile X-associated Tremor                  | `(CGG){11,}`                      | Repeat ≥ 11    | Premutation in FMR1 gene with CGG repeats             |
| Kennedy’s Disease                            | `(CAG){7,}`                       | Repeat ≥ 7     | CAG trinucleotide expansion in androgen receptor gene |
| Alzheimer’s Disease Type 1                   | `T...C` or `C...T` at pos 12 & 15 | Positional     | Early-onset Alzheimer's specific mutation             |
| Alzheimer’s Disease Type 2                   | `C...C` at pos 12 & 15            | Positional     | Late-onset Alzheimer's specific mutation              |
| Spinocerebellar Ataxia Type 1                | `(CAG){8,}`                       | Repeat ≥ 8     | CAG repeat expansion causing cerebellar degeneration  |
| Friedreich’s Ataxia                          | `(GAA){13,}`                      | Repeat ≥ 13    | GAA repeat expansion in the FXN gene                  |
| Oculopharyngeal Muscular Dystrophy (OPMD)    | `(GCG){2,}`                       | Repeat ≥ 2     | GCG repeat expansion in the PABPN1 gene               |
| Dentatorubral–pallidoluysian atrophy (DRPLA) | `(GAC){9,}`                       | Repeat ≥ 9     | GTC repeat expansion in the ATN1 gene                 |

4. Output and User Interaction

Upon successful pattern detection: The sequence is highlighted on the visual DNA structure.

A message is displayed with the detected mutation, position, and disease name.

If no match is found: A “No mutation detected” message is shown.

5. Technology Stack

Frontend: JavaScript, HTML5 Canvas / WebGL (for DNA visualization)

Backend/Logic: JavaScript for Z-algorithm and pattern matching

Visualization: Custom coloring logic to indicate matching DNA segments
