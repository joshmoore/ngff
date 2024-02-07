RFC-0
=====

Example

In a few different contexts recently, questions have been (rightly) asked regarding the process for modifying the specification. Likely it's not quite time for something as formal as say https://zarr.dev/zeps/active/ZEP0000.html but for each of the stages of a new spec there should be guidelines (preferably in the [spec page itself](https://github.com/ome/ngff/blob/main/latest/index.bs) as to who needs to communicate what to whom and what decisions can and need to be made. In a follow-up comment, I'll outline what I think of as the status quo and hopefully we can collect a few proposals for the process definition. The rest of the description will focus on defining the various parts of the process that can be re-used in proposals.

### Communication media
* open discussions (with notes!)
* https://image.sc
* https://imagesc.zulipchat.com/
* Issues
* PRs
* [specification](https://ngff.openmicroscopy.org/)

### Interested parties
* **editors**: those who have authored or are authoring specifications
* **implementors**: those who maintain a library or client which implements specs (see below)
* **developer community**: those who build tools that are expected to support NGFFs (napari, BDV, Viv)
* **[the ngff group](https://forum.image.sc/g/ngff)**: those who have actively signed up for calls, feedback, etc.
* and the wider community of users

### Involved components
* the specification itself (`./latest/index.bs`)
* the schema (`./latest/schemas/*`)
* implementing libraries (ome-zarr-py, n5-zarr, [validator](https://github.com/ome/ome-ngff-validator/), etc)
* implementing clients (MoBIE, ViZarr, napari-ome-zarr, neuroglancer, ITK, etc)

### Phases

The phases below are sometimes concurrent and/or in a different order.

* **Proposal**: an informal statement that someone would like to lead an effort to change the specification.
* **Issue opened**: a (slightly?) more formal statement of the purposes of a Proposal that will track all of the associated work.
* **Community call**: an open, usually zoom, call announced under https://forum.image.sc/tag/ome-ngff where a proposal might be discussed.
* **Hackathon**: an open, often in person, meeting to work on a Proposal.
* **Drafting**: period during which the specification is being actively modified.
* **PR Opened**: a change to the specification including the normative text, examples, schemas and schema tests.
* **Discussions**: once a formal change has been opened, period of time during which comments and feedback are collected and changes are made.
* **PR Merged**: no further changes are intended and the specification is considered acceptable to be part of "latest".
* **Acceptance**: the changes to "latest" are considered acceptable for a release and are ported to the appropriate version directory.
* **Implementation**: support is added to each of the libraries and clients listed above. A differentiation may need to be made between core (MUST) and additional (SHOULD) components.
* **Release**: an NGFF specification version is formally released by adding the appropriate tag to this repository.

----

(Edits to the above lists welcome.)

### Status quo

A general outline of how the versions 0.1 through 0.4 largely progressed (though perhaps @constantinpape can chime him on how his experience with 0.4 varied).

* **Proposals** generally started with fairly strong support during **community calls** which often led to the drafting of an issue. (In the case of v0.1, the first issue was on the zarr-specs repository.)
* To the extent possible, **implementations** were started as soon as there was a general consensus since it's much easier to show what's intended when there's draft data (which requires a writer implementation). This data was often uploaded to a temporary S3 location.
* Once the **PR was opened**, there was a general call for **feedback** (typically via the image.sc **ngff group**) with various iterations. Sometimes a second call occurred at this point.
* Once no further changes were requested, a final call with a deadline for release was made either via the image.sc group or a community call or both.
* The tag was pushed and then an attempt to make sure all implementations were aligned followed.


### Current exception

An exception to the above is the current `bioformats2raw.layout` proposal. It differs from previous versions in that:
 - It tries to capture a format that has been produced for some time.
 - It affects one or more _existing_ versions.
 - Support in all clients seems to be less essential, though just how to quantify this should be part of this definition.
