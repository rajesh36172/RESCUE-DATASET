# RESCUE-DATASET
# RESCUE Dataset

## Relational Scene Understanding in Complex Hostage Events (RESCUE)

The **RESCUE** dataset is a benchmark dataset designed for **Dynamic Scene Graph Generation (DSGG)** and **Relational Scene Understanding** in realistic hostage and rescue scenarios. Unlike existing datasets that primarily focus on daily human activities, RESCUE emphasizes complex crime-oriented interactions involving multiple individuals, weapons, emotional cues, and dynamically evolving relationships.

The dataset contains **500 hostage-crime videos** collected from diverse sources, including real CCTV footage, movie sequences, and manually recreated hostage situations. From these videos, **15,000 representative frames** were densely annotated with object bounding boxes and multi-type relationship labels.

---

## Dataset Statistics

| Property                | Value        |
| ----------------------- | ------------ |
| Videos                  | 500          |
| Annotated Frames        | 15,000       |
| Object Categories       | 6            |
| Relationship Categories | 24           |
| Training Split          | 80%          |
| Testing Split           | 20%          |
| Annotation Type         | Fully Manual |

---

## Object Categories

The dataset contains six frequently occurring object categories:

1. hostage
2. hostage_taker
3. rescuer
4. long_gun
5. shot_gun
6. knife

All object categories represent independent entities. Part-based object annotations are excluded to maintain annotation consistency.

---

## Relationship Categories

Relationships are organized into three semantic groups:

### Attention Relationships

* lookingat
* notlookingat
* fearful_gaze
* pleading_gaze
* threatening_gaze
* None

### Spatial Relationships

* infrontof
* behind
* beside
* between
* cornered_by
* crouching_behind

### Contact Relationships

* pointing_gun
* holding_weapon
* holding_hostage
* tying
* dragging
* covering_mouth
* hitting
* shielding
* touching
* kneeling
* hands_up
* no_contact

These relationship categories capture spatial dependencies, emotional interactions, and physical actions occurring in complex hostage situations.

---

## Data Collection

Videos were collected from multiple sources:

* Real crime-scene CCTV footage
* Movie sequences
* Recreated hostage scenarios

To generate realistic interactions and diverse relational activities, **20 volunteers** participated in staged hostage-scene recordings conducted in indoor environments.

---

## Annotation Process

The RESCUE dataset is **entirely hand-labelled**.

### Object Annotation

For every selected frame:

* All relevant objects are manually identified.
* Ground-truth bounding boxes are annotated.
* Corresponding object categories are assigned.

### Relationship Annotation

For every relevant object pair:

* Attention relationships are annotated.
* Spatial relationships are annotated.
* Contact relationships are annotated.

Three annotators contributed to the dataset collection and annotation process. Additional manual verification and cross-checking were performed to ensure annotation quality, consistency, and reliability.

Unlike datasets that partially rely on pre-trained object detectors, all annotations in RESCUE are manually generated.


---

## Annotation Format

Each annotated frame contains:

### Objects

```python
{
    "bbox": [x1, y1, x2, y2],
    "class": "hostage",
    "object_id": 1
}
```

### Relationships

```python
{
    "subject_id": 1,
    "object_id": 2,
    "attention": "fearful_gaze",
    "spatial": "behind",
    "contact": "holding_hostage"
}
```

---

## Benchmark Tasks

The dataset supports:

* Dynamic Scene Graph Generation (DSGG)
* Video Visual Relationship Detection (VidVRD)
* Human-Object Interaction Recognition (HOI)
* Relational Scene Understanding
* Crime Scene Analysis
* Multi-Agent Activity Understanding
* Temporal Relationship Prediction

---

## Citation

If you use the RESCUE dataset in your research, please cite:

```bibtex
@article{rescue2026,
  title={RESCUE: Relational Scene Understanding in Complex Hostage Events for Dynamic Scene Graph Generation},
  author={Author Names},
  journal={IEEE Transactions on Artificial Intelligence},
  year={2026}
}
```

---

## License

The RESCUE dataset is released for academic research purposes only. Commercial use is prohibited without prior permission.

---

## Contact

For questions regarding the dataset, please contact:

```
Author Name
Institution
email@domain.edu
```
