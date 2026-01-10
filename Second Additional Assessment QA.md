# Use cases considering scene and hardware conditions:

In your responses, you noted that scene and hardware conditions can have a
significant impact. Could you share any concrete sports or non-sports use cases
where you consider the proposed approach to be realistically applicable, along
with any assumed scene conditions?

## Response

* look into research on markerless capture and applications to make more
  concrete and to identify uses outside sports

* Sports entertainment (fly through games or sideline seating)
* Practice tape

# Expected impact of the proposed approach:

Assuming such scenarios, we would like to understand the expected practical
impact of the proposed approach in quantitative terms (even a rough,
assumption-based estimate would be helpful). For example, compared with a
conventional setup that relies on many fixed cameras, what level of improvement
do you anticipate—such as a reduction in the number of required cameras, or
other measurable gains?

## Response

* Need to work through math for e.g. cost reduction and number of cameras

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
   (e.g. prioritizing action near a ball or while players are otherwise spread
   out over the volume)
3. If occlusions are significant and if adapting to occlusions is critical

Quantifying these impacts depends on nuanced aspects of the structure of the
environment and the scene being observed and the requirements for downstream
applications.

Still, there is some merit to discussing extremes.
Consider a single athlete (say a long distance runner) who wishes to record
their a practice session, running on an oval track.
A small number of PTZ cameras (e.g. 4-6) would be sufficient to provide dense
coverage of the athlete from multiple perspectives and for the entire track.
At this extreme, camera coordination and sufficient zoom would ensure that the
athlete fills a significant portion of each camera's field-of-view, even as the
athlete moves about a much larger volume.
Obtaining similar performance with static cameras would require a similar number
of cameras (4-6) for every 2-4m of a 400m track---whether those cameras are
arranged on trusses near the runner or in large nests with telephoto lenses
above and outside the track.
In this case, the difference in number of cameras would be on the order of 100x
and would have transformative impacts.
A Static camera system would require semi-permanent installation, precise
orientation and calibration of all cameras and altogether at immense cost.
A system based on PTZ cameras could be transported in a single vehicle and
installed in a few minutes by a small team.

A small step away from this scenario would be to obtain motion capture data for
a race, prioritizing a group of leaders.
In this case, the advantage for a practical deployment might be closer to 10x.
Allowing for slightly reduced resolution---some cameras may cover more than one
person at a time---10-20 PTZ cameras might provide adequate coverage of the
leading 5-10 athletes.
Comparable coverage with static cameras could be obtained with 4-6 cameras for
every 10-15m of track, approximately 100-240 cameras.

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
be covered by several dedicated PTZ cameras (say 6).
Conservatively, that same number of cameras might cover a 10m * 10m area of the
field.
For 22 athletes and a rectangular 110m * 49m field, we might expect a 2.5x
reduction in the number of cameras (132 vs 323).
If athletes move and can be covered in groups of 2-3 on average, the
gain becomes 5-7.5x.

American football
* 4-6 cameras * 22 athletes
* 110m * 49m / (10m)^2 * 6-10 cameras

* Similar benefits could be obtained recording performances

* Path to quantifying impacts (data collection and preliminary results)
* Allowing for varying detail and resolution
* Races and very large ad-hoc deployments
* Extremes

# Research targets:

Given that wide-area sports motion tracking systems, such as Hawk-Eye, are
already well established commercially, we believe it is important to consider
additional differentiating directions. In this context, we would appreciate your
view on whether photorealistic reconstruction using Gaussian Splatting could be
treated as one of the research targets and examined with relatively high
priority within this project.

## Response

* Contrast to Hawk-Eye sports motion tracking

Some investigation of Gaussian Splatting would be feasible.
A reasonable experiment design would seek to compare results for PTZ cameras and
a static camera array on a sparse subset of time-steps.
In this case, we would focus on comparative evaluation of surface coverage and
detail for challenging scenes.

# System architecture and scope of deliverables:

The proposal mentions an open-source release of the planner implementation and
related software modules. In this context, could you share your view on the
overall system architecture you envision (e.g., how the components fit
together), and clarify the scope of the system and software that would be
provided to Sony?

## Response
