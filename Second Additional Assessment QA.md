# Use cases considering scene and hardware conditions:

In your responses, you noted that scene and hardware conditions can have a
significant impact. Could you share any concrete sports or non-sports use cases
where you consider the proposed approach to be realistically applicable, along
with any assumed scene conditions?

## Response

We will consider three scenarios:
1. An individual recording their motion while running on standard 400m track
   with limited supporting personal to operate an ad hoc markerless motion
   capture system
2. Extension of this scenario to consider reconstructing leaders in a running
   race
3. Application to American Football and reconstruction of players that are close
   together or far apart
We will assume adequate lighting and no occlusion (unless otherwise
specified), and we will ignore motion blur as that was discussed extensively
with the last round of questions.
For this analysis, we will assume interest in dense reconstruction (e.g.
photorealistic) such as via Gaussian Splatting or as an extension of a method
that computes skeletal reconstruction plus shape and application for
entertainment purposes or for review as practice tape.

We will also briefly adapt our analysis to other relevant settings such as
reconstructing motion for downhill skiing or a theatrical or musical
performance.

# Expected impact of the proposed approach:

Assuming such scenarios, we would like to understand the expected practical
impact of the proposed approach in quantitative terms (even a rough,
assumption-based estimate would be helpful). For example, compared with a
conventional setup that relies on many fixed cameras, what level of improvement
do you anticipate—such as a reduction in the number of required cameras, or
other measurable gains?

## Response

The key contribution of this proposal is to develop motion capture methods that
function by coordinating sensing capacity to cover a smaller region of a larger
volume, e.g. to reconstruct motion of moving athletes.

The impact (in terms of reducing cost or number of cameras) would be significant
under the following conditions:
1. If the region of interest is narrow in scope compared to coverage of the
   entire volume with static cameras
   (e.g. when covering a single athlete or one (or a few) concentrated groups
   moving through a much larger volume)
2. If satisficing results can be obtained by significantly varying levels of
   detail and prioritizing observation of small portion of a larger scene
   (e.g. prioritizing action near a ball while players are otherwise spread
   out over the volume)
3. If occlusions are significant so that coordinating cameras to mitigate
   occlusions is critical

Quantifying these impacts depends on nuanced aspects of the structure of the
environment, the number of subjects, and the structure of their motion as well
as the requirements for downstream applications.
As noted in this round of questions, markerless motion capture systems that
perform skeletal reconstruction are maturing, and Sony is deploying this at
stadium-scale via Hawk-Eye innovations.
For this reason, we will focus on necessary requirements to obtain dense
reconstructions of subjects, observation of the subject's entire surface via
several, evenly spaced, camera views and, informally, that the subject should
fill most or a large portion of the frame.
We will generally assume that 4-6 such unique cameras views would be necessary
to densely reconstruct a single person, but this will be a multiplicative factor
that cancels out when making comparison.

The following are rough estimates intended to make comparisons in terms of
orders of magnitude.

There is merit to discussing extremes.
Consider a single athlete (say a long distance runner) who wishes to record
their a practice session, running on an oval track.
A small number of PTZ cameras (e.g. 4-6) would be sufficient to provide dense
coverage of the athlete from multiple perspectives and for the entire track.
At this extreme, camera coordination and sufficient zoom would ensure that the
athlete fills a significant portion of each camera's field-of-view, even as the
athlete moves about the large volume of the track.
Obtaining similar performance with static cameras would require a similar number
of cameras for every 2-4m of a 400m track---whether those cameras are arranged
on trusses near the runner or in large nests with telephoto lenses above and
outside the track.
In this case, the reduction in number of cameras by deploying a PTZ system would
be on the order of 100x and would have transformative impacts.
A Static camera system would require extensive setup or semi-permanent
installation, precise orientation and calibration of all cameras and altogether
at immense cost.
A system based on PTZ cameras could be transported in a single vehicle and
installed in a few minutes by a small team or possibly the athlete theirself.

Taking a small step away from this scenario, consider obtaining motion capture
data for a race on the same track, prioritizing a group of leaders.
In this case, the advantage for a practical deployment might be closer to 10x.
Allowing for slightly reduced resolution---some cameras may cover more than one
person at a time, say averaging 3 people covered per camera view---10-20 PTZ
cameras might provide adequate coverage of the leading 5-10 athletes.
Comparable coverage with static cameras could be obtained with the standard
number of cameras for every 10-15m of track, approximately 100-240 cameras.

Similar analysis would apply for recording races in more varied settings or
other sports with similar requirements---one of the papers we cited in the
original proposal provided field results for downhill skiing.
Likewise, given suitable lighting conditions, capture of performances involving
small numbers of musicians or actors moving about a volume such as a stadium
would be possible with similar 10-100x reduction in camera equipment.

Impacts for team sports, though central to our initial proposal narrative, would
be harder to quantify.
Consider dense capture for American football.
In the worst case, with teams spread broadly across the field, each athlete may
be covered by several dedicated PTZ cameras (gain, say 6).
Conservatively, that same number of cameras might cover a 10m * 10m area of the
field.
For 22 athletes and a rectangular 110m * 49m field, we might expect a 2.5x
reduction in the number of cameras (132 vs 323).
If athletes move and can be covered in groups of 3 on average, the
gain becomes 7.5x.

However, consider that players may be arranged more densely: players line up
closely together at the start of play.
Observations from sideline are also heavily occluded, and sides of players are
nearly parallel to views from end-zones.
Directing many cameras from varying perspectives narrowly along the line (either
by virtue of arrangement of cameras around the field or via explicit
occlusion-aware planning) could provide significantly improved coverage for
parts of the scene that would otherwise suffer due to severe occlusion.
Consider the same configuration of cameras as deployed to cover players spread
out all over a field.
For a static array, 30 cameras might be aimed at a 10m wide strip across the
width of the field; compare to 40 or 100+ PTZ cameras with views distributed
evenly over players' surfaces with and capacity to direct denser coverage over
the middle of the field where players are close together (and that are
subsequently impacted by occlusion).
Obtaining improved reconstruction performance and mitigating occlusion
due to dense configurations of players
would be technically challenging but may be a key motivating factor
for applying motion capture based on coordinated  cameras to this team sports
setting.

If this project is funded, we will also be able to quantify these impacts more
accurately such as by obtaining  simulation results based on existing tracking
data for team sports or via field deployments of prototype systems.

# Research targets:

Given that wide-area sports motion tracking systems, such as Hawk-Eye, are
already well established commercially, we believe it is important to consider
additional differentiating directions. In this context, we would appreciate your
view on whether photorealistic reconstruction using Gaussian Splatting could be
treated as one of the research targets and examined with relatively high
priority within this project.

## Response

Our initial proposal drew motivation from applications of both dense and
skeletal reconstruction.
However, our initial technical focus on skeletal reconstruction would be for
pragmatic reasons toward prototyping markerless capture with a coordinated
camera system.
However, we are very interested in evaluating and demonstrating capabilities for
dense reconstruction.

We agree that dense reconstruction and Gaussian Splatting provide the more
compelling motivation.
As hinted in the question, Hawk-Eye systems already provide skeletal
reconstruction capabilities for sports; applications that rely on metric
accuracy, such as automated refereeing,  may also be more suitable to static
camera arrays in general.
For team sports and skeletal reconstruction, the impact of our methods may be
marginal.
However, systems for dense reconstruction at the scale of a stadium do not yet
exist, and we believe that coordinated camera systems such as what we propose
would be enabling and transformative for reasons noted in the responses above.

Some investigation relevant to Gaussian Splatting would be feasible in the first
year.
First, preliminary analysis of surface coverage could be completed based on
subjects' positions and poses.
This analysis would provide further evidence for the hypothesis that
comparable reconstruction performance could be achieved with many times fewer
cameras than for a static camera system.

Limited demonstration of Gaussian Splatting may also be possible in the first
year.
As noted, methods for dynamic Gaussian Splatting (for reconstruction of moving
subjects) are less established than methods applied to static scenes.
A reasonable experiment design might then seek to adapt established methods for
Gaussian Splatting intended for static scenes and to compare results for PTZ
cameras and a static camera array on a sparse subsets of time-steps.

As discussed in the last round of questions, challenges like motion blur would
be amplified for dense reconstruction, and we would initially perform evaluation
via simulation tools or in a laboratory setting controlled conditions and
limited velocities.

# System architecture and scope of deliverables:

The proposal mentions an open-source release of the planner implementation and
related software modules. In this context, could you share your view on the
overall system architecture you envision (e.g., how the components fit
together), and clarify the scope of the system and software that would be
provided to Sony?

## Response

Two of the planning tools we developed previously for multi-camera
coordination are available under BSD license variants:
1. https://github.com/castacks/MultiDroneMultiActorFilming
2. https://github.com/GreedyPerspectives/GreedyPerspectives
Our ongoing work on multi-camera videography with PTZ cameras builds on the
first of these.
We would expect to continue to build on this multi-camera planning codebase and
to make developments available similarly.

We are also developing a variety of (ROS2-based) tools for camera control and
for tracking people and moving objects.
We could expect to make these tools available.
However, this part of our system would be more specialized to our prototype
systems and may be of reduced interest to Sony.

The sponsored work will also involve development of new tools for (dense
and/or skeletal) markerless motion capture with coordinated cameras.
We would expect this part of our system to be less specialized to our laboratory
prototypes and to be of more interest to Sony.
We would expect to prioritize making this part of the system available to Sony
and as open source software.

