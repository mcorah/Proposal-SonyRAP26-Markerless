# When tracking moving subjects with PTZ cameras, motion blur may make human detection and pose estimation difficult. What approaches do you envision to handle this issue?

* Camera control and smooth trajectories, modeling control and blur
  interactions, modeling intrinsics and blur
* CV: Image processing techniques that account for blur or segment blurred vs
  non-blurred regions, learned models may fill in gaps or constrain based on
  feasible motion
* Experiment design: prototype with slower moving subjects
* Camera hardware: high-framerates, good lighting, and low exposure can mitigate
  impacts of blur and effects of rapid motion
* Outputs and resolution: We plan to focus on pose reconstruction over the
  proposed timeline

# Please clarify the assumed input parameters and the range of variables to be optimized in your method. Beyond camera orientation and focal length, would camera positions or the number of cameras also be within the optimization scope?

Our ongoing work focuses on finite-horizon planning of pan, tilt, and zoom for
multiple cameras, and these are the focus of proposed work.
However, we could reasonably incorporate other parameters related to camera
intrinsics into our optimization framework, such as camera focus, without major
modification of our planning approach.
Indeed, optimization of intrinsic paramters is a topic we are quite interested
in, and we are paying close attention to ongoing research in this area such as
work from Mac Schwager's group on CineMPC.

Optimizing camera positions and numbers for the purpose of design of a
multi-camera system is an interesting problem that could be solved with similar
methods as we use now for planning (view planning via greedy submodular
optimization).
We refer to such problems in Section 6.1 of the proposal as a matter of future
work.
As proposed, this specific problem would be out of scope and distinct from
proposed work such as related to prototyping methods for markerless motion
capture.
Nevertheless, this problem is of interest to us and could be incorporated into
proposed or future activities given suitable time and support.

# From our perspective, moving cameras can help mitigate occlusion problems in team sports. Do you plan to explore joint optimization of fixed PTZ cameras and moving cameras?

Absolutely!
Some of our prior work on robot videography addresses similar challenges in the
form of occlusion-aware planning for multiple aerial robots [19] (in proposal).
Moreover, planning for hybrid systems of PTZ cameras, drones, rail-mounted
cameras, or cable-suspended cameras is of interest to us and would be amenable
to the view-based planning frameworks that we are developing.
We also maintain continued interest in view planning for aerial robots, and
performing experiments studying hybrid systems consisting of aerial robots and
PTZ cameras would be of interest to us independent of proposed work.
Likewise, rail-mounted or cable-suspended cameras could reasonably be studied in
simulation but are not currently available for the purpose of laboratory or
field experiments.
We expect that some such configuration would be more relevant to camera
coordination for the purpose of cinematography---another application that is
independently of interest to us---than to the proposed program that focuses on
motion capture.

Our specific interest in PTZ cameras is a product of low cost, ease of
deployment, and availability of driver software.
These are key factors that will enable the proposed laboratory and field
experiments.

Section 3.1 of the proposal discusses some related challenges for mobile robots
in the context of coordination of aerial robots, such as policy restrictions
related to operation of aerial robots or safety concerns for operating robots,
especially aerial robots, near people, e.g. on a sports field.
Likewise, introducing additional actuation and particularly motion that cannot
easily be registered via linear or rotary encoders would conflict with the goal
of precisely tracking moving subjects for the purpose of markerless motion
capture.


# Would your proposed research rely upon any Background Intellectual Property (BIP) such as pending patent filings, patent applications, or granted patents?  If so, are you listed as an inventor on each of the pieces of BIP that you plan to use?  If not, is your university the sole owner of the BIP that you plan to use?

The proposed work builds on ongoing work happening at Mines.
No patents are currently filed on this material.
In the event that the proposed work produces patentable subject matter, it can
be made available to Sony pursuant to the terms of a Sponsored Research
Agreement.

# Do you plan to release any of your research results as open-source software (OSS)?

PI Corah and NAPPLab maintain interest in releasing research products in the
form of open source software, and parts of the underlying codebase proposed in
this work have been released under BSD license variants.
In the event this work is funded, future licensing terms including OSS licenses
are negotiable as applicable.

# Is there any additional information about your potential research program that you think we should know about at this time?
