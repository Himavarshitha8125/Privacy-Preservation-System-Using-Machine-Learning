Algorithms Used:

K-Means Clustering
Used to group similar location points based on latitude and longitude.
It helps identify common areas or movement patterns among users.
Each cluster represents a general area rather than a specific user location — this supports anonymization by abstraction.

Dynamic Sequence Alignment (DynamicSA)
Inspired by the bioinformatics sequence alignment algorithm (used in DNA comparison).
It compares sequences of latitude and longitude points to measure their similarity.
This was customized to find and slightly modify (“anonymize”) close location records so that real user paths cannot be exactly reconstructed.
Used as a heuristic privacy‑preserving algorithm — it aligns trajectories dynamically to balance between privacy and accuracy.

Heuristic Optimization Logic:
Combined results from K‑Means and Sequence Alignment to calculate privacy loss vs. clustering accuracy.
Helps decide the best trade‑off between data utility and anonymity.


Technologies and Libraries Used:

Python (Core Language): Main implementation language.
Tkinter: To build a graphical user interface (GUI) for easy dataset upload, processing, and visualization.
Pandas & NumPy: For data preprocessing — cleaning missing values, handling coordinates, and managing large location datasets.
Scikit‑learn (sklearn): For K‑Means clustering and accuracy evaluation.
Biopython: For sequence alignment operations used in DynamicSA.
Matplotlib: To visualize results like K‑Means vs. Heuristic Loss comparison.

Explaination:
My project is a Privacy Preservation System using Machine Learning where I worked on protecting user location data.
Imagine we have a file of users’ GPS data — like latitude, longitude, and time — which is sensitive because it can reveal someone’s daily route.
First, I built a Tkinter-based GUI that allows uploading this dataset. When uploaded, the data is cleaned and preprocessed using Pandas — removing missing values, converting timestamps, and isolating important columns such as latitude and longitude.
Then, I applied K-Means clustering to group similar location points — for example, users traveling within the same city area fall in one cluster.
After that, I implemented a custom algorithm called Dynamic Sequence Alignment (DynamicSA). It takes random pairs of coordinates and compares their pattern similarity (like DNA sequence alignment). This helps identify which locations are close or behaviorally similar, and then slightly modifies coordinates to anonymize real user paths — meaning the data stays useful for machine learning but no one can reverse-engineer real locations.
Finally, I calculated two losses: one from K-Means and another from the heuristic alignment, to compare accuracy vs. privacy level. I also visualized both in a bar graph for comparison.

Metrics:
The accuracy drop after anonymization was minimal, showing that the privacy‑preserving step didn’t harm the dataset’s analytical value. The comparison between K-Means and heuristic loss also showed that the heuristic method offered better privacy with acceptable accuracy.
