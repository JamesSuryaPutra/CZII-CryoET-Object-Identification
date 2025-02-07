# CZII - CryoET Object Identification

![image](https://github.com/user-attachments/assets/ccef3529-c0c5-4966-8203-b95a31f68404)

# Overview
In this competition, you'll develop machine learning (ML) algorithms to annotate diverse protein complexes (biological particles with well-defined structures) in 3D cellular images, accelerating discoveries in biomedical science and advancing disease treatment.

# Description
Protein complexes (such as oxygen-carrying hemoglobin, or keratin in hair, and thousands of others) are essential for cell function, and understanding their interactions is essential for our health and finding new disease treatments. Cryo-electron tomography (cryoET) creates 3D images—called tomograms—at near-atomic detail, showing proteins in their very complex and crowded natural environment. Therefore, cryoET has immense potential to unlock the mysteries of the cell.

There is a wealth of cryoET tomograms that is yet to be fully mined. A large and growing portion of this published corpus exists in a standardized format in the cryoET data portal (cryoetdataportal.czscience.com). Mining this data requires automatic identification of each protein molecule within these images. This problem has not been solved even for proteins that are identifiable by the human eye. A generalizable solution will reveal the “dark matter” of the cell, and will enable thousands of discoveries contributing to human health.

This competition challenges you to create ML algorithms that automatically annotate five classes of protein complexes within a curated real-world cryoET dataset.

# Evaluation
Submissions are evaluated by calculating the F-beta metric with a beta value of 4. The F-beta metric with a beta value of 4 is used to prioritize recall over precision, heavily penalizing missed particles while being more lenient on false positives. In this context, a particle is considered "true" if it lies within a factor of 0.5 of the particle of interest's radius. There are five particles of interest, with three "easy" particles (ribosome, virus-like particles, and apo-ferritin) assigned a weight of 1 and two "hard" particles (thyroglobulin and β-galactosidase) assigned a weight of 2. The results are micro-averaged across multiple tomograms, ensuring that precision and recall are computed across the entire dataset before applying the F-beta formula. The higher beta value (4) and particle weights emphasize the correct identification of particles, particularly the "hard" ones, making recall the dominant factor in evaluating performance.

Note: beta-amylase particles are included in the training data and may be predicted, but they are assigned a weight of 0 and have no impact on scoring.
