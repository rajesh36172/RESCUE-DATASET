# RESCUE Dataset
## Relational Scene Understanding in Complex Hostage Events

RESCUE is a benchmark dataset designed for **Dynamic Scene Graph Generation (DSGG)** and **Relational Scene Understanding** in realistic hostage and rescue scenarios. Unlike existing datasets that primarily focus on everyday human activities, RESCUE emphasizes complex crime-oriented interactions involving multiple individuals, weapons, emotional cues, and dynamically evolving relationships.

The dataset consists of **500 hostage-crime videos** collected from diverse sources, including real CCTV footage, movie sequences, and manually recreated hostage situations. From these videos, **15,000 annotations** were manually created, including object bounding boxes and rich relationship labels to support dynamic scene graph generation and relational scene understanding tasks.



---

## Proposed Model: STORM-Net

The proposed **STORM-Net** framework for **Dynamic Scene Graph Generation (DSGG)** is provided along with the RESCUE dataset to facilitate benchmarking and reproducible research.

STORM-Net is developed on top of the **STTran** architecture and extends it for relational scene understanding in complex hostage-event scenarios. The implementation includes training, evaluation, and inference scripts, together with configuration files required to reproduce the experimental results reported in the paper.

The STORM-Net code can be downloaded from:

[STORM-Net Download](https://drive.google.com/drive/folders/1Nqpu6cQ6idQKM1TL7nmDzJhRnTrec_a1?usp=drive_link)

A detailed usage guide is provided in the accompanying `README.md` file of the STORM-Net repository.

---





## Dataset Statistics

| Property | Value |
|-----------|--------|
| Videos | 500 |
| No. of Annotations | 2500 |
| Object Categories | 6 |
| Relationship Categories | 24 |
| Training Split | 80% |
| Testing Split | 20% |
| Annotation Type | Fully Manual |

---

## Download

The RESCUE dataset and annotation files can be downloaded from:

[Dataset Download](https://drive.google.com/drive/folders/15UPPlmCARFzwZwkZgRaC1L5SCZrqYk1-?usp=sharing)

After downloading, organize the files as follows:

```text
dataset/
└── rescue/
    ├── videos/
    ├── frames/
    ├── annotations/
    └── metadata/
```

Place:

- Videos under `dataset/rescue/videos/`
- Annotation files under `dataset/rescue/annotations/`

---

## Object Categories

The dataset contains six object categories:

1. hostage
2. hostage_taker
3. rescuer
4. long_gun
5. shot_gun
6. knife

All object categories represent independent entities. Part-based object annotations are intentionally excluded to maintain annotation consistency.

---

## Relationship Categories

Relationships are grouped into three semantic categories.

### Attention Relationships

- lookingat
- notlookingat
- fearful_gaze
- pleading_gaze
- threatening_gaze
- None

### Spatial Relationships

- infrontof
- behind
- beside
- between
- cornered_by
- crouching_behind

### Contact Relationships

- pointing_gun
- holding_weapon
- holding_hostage
- tying
- dragging
- covering_mouth
- hitting
- shielding
- touching
- kneeling
- hands_up
- no_contact

These relationships capture spatial dependencies, emotional interactions, and physical actions occurring in complex hostage scenarios.

---

## Data Collection

Videos were collected from multiple sources:

- Real crime-scene CCTV footage
- Movie sequences
- Recreated hostage scenarios

To increase interaction diversity and realism, **20 volunteers** participated in staged hostage-scene recordings conducted in indoor environments.

---

## Annotation Process

The RESCUE dataset is **fully manually annotated**.

### Object Annotation

For every selected frame:

- Relevant objects are manually identified.
- Ground-truth bounding boxes are annotated.
- Object category labels are assigned.

### Relationship Annotation

For every relevant object pair:

- Attention relationships are annotated.
- Spatial relationships are annotated.
- Contact relationships are annotated.

Three annotators contributed to the annotation process. Additional verification and cross-checking were performed to ensure annotation quality, consistency, and reliability.

Unlike several existing datasets that partially rely on pre-trained object detectors, all annotations in RESCUE are manually generated.

---

## Dataset Structure

```text
RESCUE/
├── videos/
│   ├── video_0001.mp4
│   ├── video_0002.mp4
│   └── ...
│
├── frames/
│   ├── video_0001/
│   │   ├── 000001.jpg
│   │   ├── 000002.jpg
│   │   └── ...
│   ├── video_0002/
│   └── ...
│
├── annotations/
│   ├── object_annotations.json
│   ├── relationship_annotations.json
│   ├── train_split.json
│   └── test_split.json
│
├── metadata/
│   └── object_classes.txt
│
└── README.md
```

---

## Annotation Format

### Object Annotation

```json
{
    "bbox": [x1, y1, x2, y2],
    "class": "hostage",
    "object_id": 1
}
```

### Relationship Annotation

```json
{
    "attention": "fearful_gaze",
    "spatial": "behind",
    "contact": "holding_hostage"
}
```

---

## Benchmark Tasks

The dataset supports research in:

- Dynamic Scene Graph Generation (DSGG)
- Video Visual Relationship Detection (VidVRD)
- Human-Object Interaction Recognition (HOI)
- Relational Scene Understanding
- Crime Scene Analysis
- Multi-Agent Activity Understanding
- Temporal Relationship Prediction

---

## Contact

**Rajeshwar Yadav**  
Indian Institute of Technology Patna (IIT Patna)  
Email: rajeshwar_2021cs06@iitp.ac.in

For questions, suggestions, or bug reports regarding the dataset, please feel free to contact the authors.
