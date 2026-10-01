# I-Spent-10-Years-Structuring-World-History.-Today-I-m-Open-Sourcing-It.
# The Story Behind Histolines: 80,000+ Historical Figures in a Machine-Readable Timeline Database

**What if history could be read not only by people, but also by computers?**

History is fascinating, but much of the way historical information is stored on the modern web is difficult for computers to use.

If you want to explore the life of [Salvador Dalí](https://histolines.com/timeline_character.php?charname=Salvador+Dali), [Nikola Tesla](https://histolines.com/timeline_character.php?charname=Nikola+Tesla), or [Marie Curie](https://histolines.com/timeline_character.php?charname=Marie+Curie), you will often encounter thousands of words of unstructured prose.

That works well for a human reader, but it creates a very different problem for a data scientist, AI engineer, researcher, or developer trying to analyze history computationally.

Historical information on the web is often difficult to:

* Parse chronologically
* Search systematically
* Convert into structured data
* Connect between people and places
* Analyze geographically
* Use in machine-learning applications
* Combine with other historical datasets

More than a decade ago, we started building **[Histolines](https://histolines.com/)** to address this problem.

The idea was simple:

> **Turn historical events into structured, machine-readable data while keeping them useful and understandable to people.**

Today, after years of crawling, collecting, cleaning, deduplicating, organizing, and refining historical information, Histolines contains timelines covering **more than 80,000 historical figures**.

We are making the underlying historical event data available to the open-source community under the **Apache 2.0 License**.

---

## The Core Philosophy: Who, What, Where, and When

When we started building the Histolines database, we wanted to find a simple structure that could describe almost any historical event.

At its core, a historical event can often be reduced to:

**Who → What happened → When → Where**

For example, instead of storing a sentence such as:

> *“On May 11, 1904, the surrealist painter Salvador Dalí was born in Figueres, Catalonia, Spain.”*

Histolines can represent the information as structured fields:

| Field     | Example                    |
| --------- | -------------------------- |
| **WHO**   | Salvador Dali              |
| **WHAT**  | was born                   |
| **WHEN**  | May 11, 1904               |
| **WHERE** | Figueres, Catalonia, Spain |

The exact database representation contains separate fields for the year, month, day, location, and other information.

This seemingly simple structure makes historical information much easier to search, filter, analyze, and connect.

Want to find events involving artists in Paris between 1920 and 1930?

With unstructured text, that can require substantial natural-language processing.

With structured historical event data, it becomes a data-query problem.

---

# What Is in the Dataset?

The open-source release contains a comprehensive historical **events table**, where individual rows represent events, milestones, activities, publications, performances, and other historical information associated with people and organizations.

The goal has always been to keep the fundamental event structure relatively simple and machine-readable.

Some of the primary fields include:

### `whoCharName`

The primary person or historical subject associated with the event.

### `whoRel`

Other people, organizations, or entities connected to the event.

### `whatEventType`

The action or event type describing what happened.

### `whenYear`, `whenMonth`, `whenDay`

The date associated with the event.

The dataset can represent historical dates where only part of the date is known. A value of `0` in the month or day field can indicate that the precise month or day is unknown.

The dataset also supports historical dates from earlier eras, including dates represented using negative years for BC/BCE periods.

### `whereLoc`

The textual location associated with the event.

### `whereLat`, `whereLon`

Geographic coordinates associated with the location when available.

### `eventDetail`

Additional information describing the event.

### `whatRef`

Reference or source information associated with the event.

For more information about the Histolines data structure, see the [Histolines data documentation](https://histolines.com/about/data.php).

---

# Human History Is Beautifully Messy

Data scientists often look for perfectly clean datasets.

History rarely works that way.

Historical information found on the web can contain:

* Conflicting dates
* Different spellings of names
* Missing locations
* Incomplete biographies
* Duplicate information
* Ambiguous historical records
* Conflicting interpretations
* Errors in source material

The Histolines dataset reflects this reality.

It represents the historical information we have been able to collect, process, organize, and refine over many years. It is not intended to suggest that every historical fact is permanently settled or that every record is perfect.

Instead, we consider the dataset a **living historical archive**.

It can be corrected, expanded, compared with other sources, and improved over time.

That is one of the reasons we are releasing it under the **Apache 2.0 License**.

We want researchers, developers, historians, data scientists, and students to use the data, find problems, build new tools, and contribute ideas that can make the resource better.

---

# Why a Flat Historical Database?

One of the important design decisions behind Histolines is keeping the fundamental event data relatively flat.

A flat structure makes the information easier to:

* Import into SQL databases
* Analyze with Python or R
* Load into spreadsheets
* Use in machine-learning pipelines
* Convert into graph databases
* Combine with other datasets
* Filter by person, date, or location
* Use in visualization systems

It also provides a common foundation for building more complicated historical structures.

A simple event such as:

**Salvador Dali → was born → May 11, 1904 → Figueres**

can eventually become part of much larger networks connecting:

**People → Events → Places → Organizations → Artwork → Historical Periods**

This is one of the ideas behind [Histolines' interactive historical timelines](https://histolines.com/).

---

# What Can You Build With It?

We hope the dataset will be useful for projects across history, digital humanities, data science, and artificial intelligence.

### 1. AI and RAG Applications

Use structured historical events as a source for historical AI applications, retrieval-augmented generation systems, research assistants, or timeline-building tools.

Structured data can provide an additional source of grounding for questions such as:

> When did X meet Y?

> Where did X live in 1925?

> What events occurred in Paris during a particular period?

> Which historical figures were connected to a particular organization?

### 2. Historical Maps

Use the geographic information to visualize where historical figures lived, traveled, worked, fought, studied, or created their work.

This could allow researchers to map the movements of historical figures over their lifetimes.

### 3. Historical Network Graphs

The relationships contained within historical events can be used to construct networks connecting people, organizations, locations, and events.

Instead of looking at history as a collection of isolated biographies, you can begin to visualize it as a connected graph.

### 4. Timeline Applications

Build your own timeline interfaces using the underlying event data.

Histolines itself uses this approach to create [interactive historical timelines](https://histolines.com/).

### 5. Digital Humanities Research

Researchers can use the data to investigate patterns across large numbers of historical figures and events that would be difficult to study manually.

---

# An Open Historical Data Project

This dataset is part of a larger effort to make historical information more accessible as structured data.

Histolines has collected information from many different sources, including open datasets, museums, archives, public websites, and historical collections.

We have also developed crawlers and data-processing tools that help transform unstructured information into structured historical events.

You can learn more about this work through the [Histolines Historical Data Project](https://histolines.com/about/data.php).

Our [Histolines events archive on GitHub](https://github.com/histolines/Histolines_events_archive) provides another way to access and work with historical event data.

---

# Explore the Data

The dataset associated with this project is:

**`histolines_global_history_timelines_archive_v20260609.csv`**

The data is released under the **Apache License 2.0**.

You can use it to experiment with historical analysis, visualization, machine learning, natural-language processing, graph databases, or your own timeline applications.

You can also explore the resulting timelines directly on [Histolines.com](https://histolines.com/).

Some examples include:

* [Salvador Dalí Historical Timeline](https://histolines.com/timeline_character.php?charname=Salvador+Dali)
* [Nikola Tesla Historical Timeline](https://histolines.com/timeline_character.php?charname=Nikola+Tesla)
* [Marie Curie Historical Timeline](https://histolines.com/timeline_character.php?charname=Marie+Curie)

---

# Help Build a Better Historical Dataset

We know the dataset is not perfect.

That's part of the reason we are making it open.

If you find an error, discover a useful source, have a historical dataset that could be integrated, or build something interesting using the data, we'd love to hear about it.

The long-term
