# When tracking moving subjects with PTZ cameras, motion blur may make human detection and pose estimation difficult. What approaches do you envision to handle this issue?

Fundamentally, motion blur is a product of motion of the scene relative
to the camera over the duration of the exposure of a frame.
Impacts of motion blur can be mitigated by reducing exposure duration, reducing
relative motion, or by building systems that are robust to motion blur.
From the perspective of markerless motion capture with PTZ cameras, we should
consider impacts of motion blur at several locations in the design and
evaluation of a system.

The scene and hardware will have significant impacts.
A brightly lit scene and lenses with large apertures would enable reduction in
exposure time.
So, bright lighting at a sporting event or appropriate choice of camera equipment
could each serve to mitigate adverse impacts of motion blur when filming and
reconstructing motions of quickly-moving athletes.

Some of our choices would seek to sidestep motion blur and challenges related to
imaging more broadly during initial phases of prototyping and evaluation.

For example, the severity of impacts of motion blur depend on the nature
and resolution of the output of the markerless motion capture system.
This provides one motivation for our focus on 3D skeletal reconstruction for the
duration of the proposed work---we expect that skeletal reconstructions would be
less impacted by motion blur or other aberrations than, for example, dense
reconstruction of surfaces.

Likewise, we can mitigate blur trivially by designing laboratory and field
experiments where cameras and subjects move at low or limited velocities.
Thus, motion blur would not prevent us from validating our basic approach.
Nor would motion blur limit the size of the capture volume when performing field
experiments.

On the other hand, laboratory and field experiments may provide the first point
in the process of evaluation and development where we would encounter motion
blur and have an opportunity to evaluate impacts of motion blur on system
performance.
Simulation experiments may not feature motion blur or other effects unless we
are able to incorporate tools that model motion blur or other effects.
In this sense, motion blur is a challenge that motivates physical experiments
and consideration of photorealistic simulation tools.

Motion blur can also be mitigated at the level of planning and control such as
by designing smooth motions that avoid inducing vibration or by introducing
terms in the optimization process that encode a preference for low relative
velocities.
This strategy aligns closely with our expertise in perception-aware planning and
control and would be in scope and of interest to us.

Finally, the system for image processing and reconstruction can be *made
robust* to motion blur.
For example, predicted or observed motion blur could be used to reject
observations or to model uncertainty.
Such a strategy could enable rejection of observations of some subjects in the
camera field of view and rejection of others which could admit greater
flexibility in planning and control.
There is also prior work on motion blur robust NeRF and Gaussian Splatting
methods (Deblur-NeRF, Deblur-GS, and work by Seiskari et al.).
Such dense reconstruction methods are out of scope over the year of proposed
work but highlight intensified challenges for obtaining dense reconstructions
with camera motion that we may encounter in future years.

# Please clarify the assumed input parameters and the range of variables to be optimized in your method. Beyond camera orientation and focal length, would camera positions or the number of cameras also be within the optimization scope?

Our ongoing work focuses on finite-horizon planning of pan, tilt, and zoom for
multiple cameras, and these are the primary focus of proposed work.
However, we could reasonably incorporate other parameters related to camera
intrinsics into our optimization framework, such as camera focus, without major
modification of our planning approach.
Indeed, optimization of other intrinsic parameters such as focus is a topic we
are quite interested in, and we are paying close attention to ongoing research
in this area such as work from Mac Schwager's group on CineMPC.

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

Some of our prior work on robot videography addresses similar challenges in the
form of occlusion-aware planning for multiple aerial robots [19]
(in proposal refs).
Moreover, planning for hybrid teams of PTZ cameras, drones, rail-mounted
cameras, or cable-suspended cameras is of interest to us and would be compatible
with the view-based planning frameworks that we are developing.
We also maintain continued interest in view planning for aerial robots, and
performing experiments studying hybrid teams of aerial robots and PTZ cameras is
of interest to us independent of proposed work.
Likewise, rail-mounted or cable-suspended cameras could reasonably be studied in
simulation but are not currently available to us for the purpose of laboratory
or field experiments.
Some such configurations may also be more relevant to camera coordination for
the purpose of cinematography---another application that is independently of
interest to us---than to the proposed program that focuses on motion capture.

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
of precisely tracking moving subjects for the purpose of markerless capture.

Occlusions can also be mitigated by other means such as by placing more cameras
or optimizing locations as per prior discussion of system design problems.
Ultimately, occlusions are also factor that will limit both static and mobile
cameras---all may be excluded and occluded from the interior of a close
formation of athletes---and the appropriate mitigation strategy may depend on
the nature of the task (cinematography or motion capture) or the type and
resolution of the output (pose reconstruction versus dense reconstruction of
surfaces).

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
