# The Application of the Polifonia Ontology Network for the Digital Music Observatory
Daniel Antal

- [Executive summary](#executive-summary)
- [Background](#background)
- [Application Plans](#application-plans)
  - [Research data management](#research-data-management)
- [Interoperability between industry and heritage
  databases](#interoperability-between-industry-and-heritage-databases)
  - [Music entity and Composition
    Object](#music-entity-and-composition-object)
  - [Recording process, performing process, and
    rights](#recording-process-performing-process-and-rights)
  - [Recording and Release](#recording-and-release)
- [Licensing](#licensing)
- [Case study: Briging back rare music into
  circulation](#case-study-briging-back-rare-music-into-circulation)

## Executive summary

Our working hypothesis is that the PON ontologies can support in their
current 1.0 form some of the reproducible research work carried out on
the Digital Music Observatory and in the Open Music Europe research
project.

`Music Meta` is a rich and flexible semantic model to describe music
metadata related to artists, compositions, performances, recordings,
broadcasts, and links. Music Meta provides an abstraction layer
representing (Western) music metadata across different genres and
periods for various stakeholders and music datasets. We want to test and
increase the applicability of this ontology to provide interoperability
between cultural heritage organisations, libraries and industry
organisations like copyright management organisations, labels,
publishers and distributors.

In `Open Music Europe`, we would like to create the
`Slovak Comprehensive Music Database`, a linked database of Slovak
collective management organisations, industry, music libraries and
heritage organisations supported by a knowledge graph. The `SKCMDb` does
not exist yet. We want to test the PON `Music Meta` ontology to see if
it can be helpful in the creation of `SKCMDb` by providing
interoperability among various music databases. `Open Music Europe` uses
standardised databases and definitions so that our Slovak use case can
be replicated in any European country; in fact, we are already working
in 2-3 replications in Hungary, Bulgaria and Lithuania, which may
provide further test cases for PON.

The `PON` ontologies are well-developed in digital humanities,
particularly musicology, but have not yet been tested and improved for
industry use. An immediate task is to define an equivalence relationship
among PON objects and ISO-standard music industry concepts; this will
also allow the application of global PIDs on the most important music
objects.

The testing of PON on more significant parts of the constituent
databases of `SKCMDb` would require a written agreement among Hudobné
centrum (recordings, databases, publishing rights), `SOZA` (work
registers and rights management), `Hudobný Fond` (music sheets and
publishing rights), the `Slovak National Library` (which regulates music
libraries), and Reprex (as a technical provider of the aforementioned
organisations). A possible way forward is to evaluate very small data
samples to draw up this agreement in 1-2 iterations and to include all
relevant Polifonia stakeholders in the Digital Music Observatory’s
stakeholder network because Polifonia’s network will end in April 2024.

Our working hypothesis is that the PON ontologies can support in their
current 1.0 form some of the reproducible research work carried out on
the Digital Music Observatory and in the Open Music Europe research
project.

## Background

The `Digital Music Observatory` is a prototype of an open,
decentralised, reproducible research-supported data observatory that
follows the Feasibility Study for establishing a European Music
Observatory. High-quality indicators and databases are being developed,
consulted with the industry, produced and added to the Digital Music
Observatory web resource in various public and private projects. The
platform is being developed by Reprex, and the four main Data Pillars by
the Open Music Europe project.

The `Polifonia Ontology Network` (PON) provides a modular backbone of
music ontologies to address both cultural heritage and more general
queries in the music domain. As illustrated in the diagram
below,`PON v1.0` comprises 15 ontology module that are organised
thematically and hierarchically. Four foundational models provide
interoperability across PON through their abstract design: `Source`,
`Instrument`,`Music Meta`, and `Music Representation`.

## Application Plans

### Research data management

Open Music Europe should adopt a new version of its research data
management activities and Data Management Plan that explicitly endorses
some of the Polifonia ontologies.

## Interoperability between industry and heritage databases

`Music Meta` is a rich and flexible semantic model to describe music
metadata related to artists, compositions, performances, recordings,
broadcasts, and links. Music Meta provides an abstraction layer
representing (Western) music metadata across different genres and
periods for various stakeholders and music datasets. We want to test and
increase the applicability of this ontology to provide interoperability
between cultural heritage organisations, libraries and industry
organisations like copyright management organisations, labels,
publishers and distributors.

Most industry databases are organised around three central objects: the
“Phonogram” or sound recording, the “Musical Work” and the “Music
score”. Each is standardised, and because various rights are attached to
these objects, they have well-maintained global registers and ISO
permanent IDs. It would be very practical if PON would not recognise
these central objects and offer equivalent classes, as almost all
industry uses and most heritage uses (such as libraries, and archives)
use them.

1.  International Standard Recording Code or ISRC (ISO 3901) -- unknown
    number of PIDs, but more than 100 million objects;
2.  International Standard Musical Work Code or ISWC (ISO 15707) --
    CIS-Net has about 52 million PIDs and objects;
3.  International Standard Music Number or ISMN (ISO 10957) for printed
    music -- a lower number, because printed music historically was
    published with book identifiers.

The representation of these objects must not be ambiguous in
`MusicMatch`. The second topic is the mapping of rigths and licenses
into the `PON` ontologies. In this case, only limited support can be
achieved over a short period of time, however, there are some
opportunities of quick fixes with the replacement of the ambiguous and
even misleading `hasLicense` property.

### Music entity and Composition Object

It is unclear what is the difference between the `MusicalEntity` and
`CompositionObject`? Is `MusicalEntity` broader in that it includes
scale practices and improvisation? Or, if the `CompositionObject` still
consists of these practices, than we need a `MusicWork` object.

Generally, the Music work is such a central concept of music that it
should have an equivalent class. It is paramount to how music is stored,
published, and licensed. The music work is a composition that is
considered “final”, i.e., the process of composition was finished, and
the creator somehow “recorded” the abstract music in music notation or
recording it. Once the music work is registered and published, other
musicians can play it (with a license).

The `MusicWork` can have opus statements, dedications, text (lyrics or
libretto), and instrumentalisation attached. It has a global
identification system; the ISWC (International Standard Musical Work
Code) is an internationally recognised reference number for identifying
musical works; the CIS-Net database currently contains 52 million works.
All industry databases use the music work concept. From an industry
perspective, I do not see the `CompositionObject` and `MusicalEntity`
differences because the definition of a `MusicalWork` is intentionally
very abstract.

Because most industry and heritage databases use the `MusicalWork` and
the ISWC as their PID, an equivalence relationship, in this case, would
be essential for usability. In my opinion, the `MusicalEntity` and the
`CompositionObject` should only differ because the creator deems one of
them complete in the sense that it is worth repeating. The broader
category should include trivial music like scale practising, doodles of
later music works, or improvisation not intended to be repeated. Once a
music is composed, i.e., it is open to be performed, even if with newer
and newer arrangements, it should be a `MusicalWork`.

### Recording process, performing process, and rights

`MusicalPerformance` and `RecordingProcess` are both derived from
`CreativeProcess`. They both require a license if the music work is
still protected.

- A `MusicalPerformance` that is performed in front of the public is the
  live performance, and it requires a public performance license.

- A `StudioPerformance` is not performed in front of the public but it
  requires a mechanical license to create the recorded fixation.

- A Live recording is the mix of the two, when the musical work is
  recorded in front of a public audience.

The following elements of the *Convention for the Protection of
Producers of Phonograms Against Unauthorized Duplication of Their
Phonograms* should be very clearly present in the ontology, because they
apply to more than 100 million sound recordings.

1)  “phonogram” means any exclusively aural fixation of sounds of a
    performance or of other sounds; *appears to be identical to
    Recording*

2)  “producer of phonograms” means the person who, or the legal entity
    which, first fixes the sounds of a performance or other sounds; this
    is a special role;

3)  “duplicate” means an article which contains sounds taken directly or
    indirectly from a phonogram and which embodies all or a substantial
    part of the sounds fixed in that phonogram; *this will result in a
    mechanical license*

4)  “distribution to the public” means any act by which duplicates of a
    phonogram are offered, directly or indirectly, to the general public
    or any section thereof.

### Recording and Release

The `Commercial Release` is another central concept with an PID
(International Standard Recording Code), which applies to recordings
that are permitted to be distributed to the public. Most music databases
contain only such recordings, and they identify the commercially
released recordings.

The `Release` class should be vetted from a legal point of view, and at
least the `Commercial Release`, which must have an ISRC code, should be
differentiated from any other release that does not have it. It is also
a convenient distinction because such a recording (with few exceptions)
cannot be played publicly.

The word `release` in itself refers to a process, and this process has a
legal definition. If it is based on pre-existing licenses, it will
result in a commercial release with a globally recognised ISRC code and
the right to play (with a further license) the music in public. The
semantic check of the ‘release’ should be making predicaments with
various agents who release a recording and then categorising them.

The fair use exemption from obtaining a license may be applied for
criticism, comment, teaching, scholarship and research. This means that
particularly scholarly organisations may hold not commercially released
recordings.

- A `commercial release` is made with the intention of distribution to
  the public. This can be broadcasted on the basis of a special,
  *blanket license*, without explicit permission from the creators of
  the commercial release.

- Another typical use case is the recording of performances for comment,
  teaching, scholarship and research. Music schools, academies, but
  musicology archives have many such recordings. In this case, the
  intention is not to make the recording public; usually the recording
  can be used with limitations, for example, only in a music library.

- Another exception is when the author releases a non-commercial
  recording, for example, a demo, on a website like Bandcamp. Such a
  release does not meet the requirements of a commercial release and,
  therefore cannot be played in a radio. The intention is to provide a
  proof-of-concept for a future commercial release or other type of
  recording. This *may be intended for the public*, but it cannot be
  distributed to the public, for example, it cannot be broadcasted, at
  least without explicit consent from the creator.

- Another exception is a recording that the author may deposit as a
  supplement to register the work as a “music score”, mainly if the
  author is not familiar with music notation. In this case the recording
  plays a special role, to use it as an identifier for the more abstract
  music work, and it is *not intended* to make public.

A better classification of the recordings is essential to use the
`MusicMatch` with sound recording databases. These databases usually
contain recordings with one specific purpose; for example, the SOZA
database uses the (4) recordings, the SLOVGRAM database or the Deezer
API the (1) type recordings, the Slovak Music Information Center has a
mix of (1) and (2) recordings, and Bandcamp is packed with (1) and (3)
recordings. Since these recordings can be used differently and have
different licences, a classification is necessary. As a first step, the
most frequent class with a global PID, i.e. the commercial release,
should be detached from other `Recordings`. A binary
`Commercial release` and `Non-commercial release` would be already
helpful, or a `Commercial release`, and `Non-commercial release`.

Last, I need to use a special property, “Public domain”. While there are
different ways various releases can go into the public domain, from a
cultural heritage and rights management perspective, this property is
paramount because it means that no license is needed to use the
recording. In any other case, a set of various licensing conditions may
be attached, but for the public domain, this is not necessary.

## Licensing

The `hasLicense` property is defined as “a Recording, Release, or Score
is associated with a specific License. This property represents the
relationship between a musical recording, a release of music, or a
musical score, and the license that governs its usage and distribution.
It indicates that the mentioned Recording, Release, or Score is subject
to the terms and conditions defined by the mentioned License.”

In music, we differentiate among different rights: 1. synchronization
and other grand rights (when the music will be part of a larger artwork,
such as a film or a theatrical, staged production); 2. public
performance rights (broadcasting rights fall under this); 3. mechanical
reproduction rights, and then we have hybrid rights, or situations when
both types of licensing is required. We have two groups of rightsholder:
authors (copyright holders), and producers/performers (sound recording
copyright or neighboring right holders).

It is questionable if the same `hasLicense` property should be applied
for a `Recording`, `Release`, or `Score`, because they represent a
different right and a different type of a license; furthermore, we must
realise that we are talking about a hierarchy of three licenses that are
built on each other. Some of the licenses are not valid without a prior
license! The purpose of these licenses, and their place in the licensing
hierarchy is so different that a generic `hasLicense` will almost
certainly result in mapping errors.

I am not even sure that the `hasLicense` property is helpful in this
form. I think it should be replaced with `hasAuthorsRight` and
`hasNeighbouringRight` properties.

The `License` could be modelled similarly to provenance, but it would be
very complicated, like PROVO itself. A License must be given by a
competent Agent, where qualified Persons act in various Roles. It
connects the Agent, the Music object, with multiple Use contexts
(“Broadcast on TV”, “Retransmission on Cable TV”, “Digitally stream”,
“Play on stage”) with a term as a time interval.

The Licenses are contextual; broadcasting licenses are blanket licenses
where the rightsholders do not need to be informed; stage rights can
relate to a single event. The `hasLicense` property is so vague that it
cannot be observed. There is no single database for all licenses, and
most music databases do not contain the license, only the right to
obtain or give a license. The `hasLicense` property causes semantic
confusion and makes mapping in databases impossible.

I would suggest different properties:

1.  Is the `Musical_work` in the public domain, or does it require a
    public performance license to be played in front of the public and a
    mechanical copying license to be recorded (it has a copyright in the
    US/UK or author’s right in the EU)
2.  Is the `Recording` in the public domain, or does it require a
    mechanical right to be duplicated and a public performance right to
    be distributed or communicated to the public? (In the US/UK, it has
    a sound recording copyright, or in the EU, it has neighbouring
    rights for producers and performers.)
3.  Is the `Music notation` in the public domain, or does it require a
    rental or copying license.
4.  Are there any other limitations in place to play the music or its
    recording in public (explicit lyrics in specific broadcasts, not
    covered by blanket licensing for broadcast, only available for
    scholarly use, only for liturgical use.)

A binary property.`inPublicDomain` would be beneficial because, in this
case, we do not talk about rightsholders; therefore, no license can be
given or obtained. Any further case is too complex to be described by a
`hasLicense` property.

I think that licensing is not well represented with objects (“licenses”)
or events (“licensing events”), they would require a more sophisticated
process mapping. If we look at PROVO-O, a widely used ontology, it has
the [prov:Plan](https://www.w3.org/TR/prov-o/#Plan) class, similar to
other ontologies’ process management or quality assurance classes.

The `Plan` is a set of rules that `Agents` in various `Roles` are
expected to follow. This is very helpful when multiple persons are
involved in a thing’s curation, selection, measurement, documentation,
and quality control.

In my opinion, this is a good analogy for a `LicensingPolicy` class. For
example, the recording of the live performance of the “Nirvana Unplugged
in MTV” album has required several different licenses to be played on
television, on cable television, on radio, on a theatre stage, or
digital streaming platforms. The `hasLicense` property is entirely
contextual: the “About a Girl” recording has a different set of licenses
(in plural) on cable television or if it appears on an LCD screen in a
theatre.

Designing a suitable `LicensingPolicy` object would require a three-year
project. But from a database point of view, most music databases do not
even contain this information what they have if there are particular
types of rights attached to the musical work or the recording.

## Case study: Briging back rare music into circulation

One of the most important uses of the Slovak Comprehensive Music
Database is the clarification of the legal status of a large body of
sound recordings which are currently under the custody of the Slovak
Music Information Center. These works had been in most cases performed
on radio (in the former Czechoslovakia, under a different rights
management regime) or played on stage and recorded without the intent to
distribute the recording to the public.

In some cases, the recordings may had been distributed to the public,
but the documentation does not exists; they are certainly out of
circulation, but we do not know if this is due the fact that they must
not be in circulation, or they are just out of circulation for
commercial reasons. We want to create a link between the archive of the
`Slovak Music Information Center` and `SOZA`, and if possible,
`SLOVGRAM`, to identify works that are out of circulation but could be
legally available for radio broadcasting or music streaming.

In other cases, the original aim of the recording was explicitly not for
distribution to the public, but due to the lapse of time, or the
scarcity of the recording, there may be a legitimate interest to
distribute it to the public now. In these cases we need to identify to
the natural and legal persons or their agents (music labels, publishers)
to clarify the circumstances under which the legal status of such
recordings can be changed. It is also possible that these rare and
important recordings can be used as `demo recordings` to create interest
for their new recording and distribution to the public in a newer
interpretation or a higher quality audio.
