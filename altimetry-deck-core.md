# Radar & Laser Altimetry — core deck (15 slides)

Shipu Debnath · GEOG 789 Independent Study · Fall 2026  
Prepared for Dr. Sinead L. Farrell · University of Maryland

Text version of the HTML deck: slide text, speaker notes and references. Interactive figures, 3D views and animations are only in the HTML file.

# Part 1 — Core deck (slides 1–15)

## Slide 1 — Radar & Laser Altimetry
*01 · Active remote sensing · Satellite altimetry*

Shipu Debnath · GEOG 789 Independent Study · Fall 2026

Prepared for Dr. Sinead L. Farrell · University of Maryland

> **Speaker notes**
> 
> Introduction. This presentation examines active satellite altimetry, the measurement of surface height from orbit by timing a transmitted pulse. A radar or laser altimeter emits a pulse toward the surface directly beneath the satellite and records the time at which the echo returns. That interval is converted into a distance, the range, and because the position of the satellite is known with centimetre accuracy, the range yields the height of the reflecting surface.
> 
> The figure. The globe is a schematic illustration and is not drawn to scale. Land is shown as dots. The blue satellite represents a conventional radar altimeter on a 66° inclination orbit, such as Jason-3 or Sentinel-6, whose footprint is several kilometres across. The green satellite represents ICESat-2 on a 92° orbit, with six laser beams arranged in three pairs that produce footprints of approximately 11 m. Because the radar orbit is inclined at 66°, its ground track never extends poleward of 66° latitude, whereas ICESat-2 reaches 88°.
> 
> Structure of the presentation. The presentation proceeds from the measurement principle to the choice of frequency, then to radar and laser altimetry in turn, the interaction of each with different surfaces, footprint size, the history of altimetry missions, a direct comparison of the two techniques and, finally, the benefits of combining them.
> 
> Sources. The altimetry principle and its history are described by Cheney (2001), Escudier et al. (2018) and Magruder et al. (2024). Skylab carried the first experimental radar altimeter in 1973 (Raney, 2014); GEOS-3 followed in 1975, and TOPEX/Poseidon began the high-precision era in 1992.

---

## Slide 2 — Passive vs active remote sensing
*02 · Fundamentals*

**Records energy that is already there**

- Source: Sun or Earth's own emission

- Answers what: radiance, temperature

**Transmits a pulse and times its echo**

- Own pulse: day, night, through cloud[9]

- Answers where: echo delay gives range and height

Imaging & scattering[6]

**Imaging radar (SAR)**

side-looking images

**Scatterometer**

ocean wind vectors

Ranging · this talk

**Radar altimeter**

nadir range · km footprint

**Laser altimeter**

nadir range · metre spots

Profiling

**Profilers / sounders**

clouds, aerosols, ice

> **Speaker notes**
> 
> Passive and active sensing. Remote sensing instruments fall into two classes. Passive sensors record energy that is already present, either reflected sunlight or radiation emitted by the surface itself. Active sensors provide their own illumination: they transmit a pulse and record the returning echo (Glackin, 2014).
> 
> Why the distinction matters for altimetry. Because an active sensor knows exactly when its pulse was transmitted, the delay of the echo gives the distance to the surface. A passive sensor cannot measure distance in this way. Active microwave systems have the further advantage of operating independently of daylight and, in most conditions, of cloud cover (Amani et al., 2022). Under overcast skies, reflected sunlight and thermal infrared radiation are blocked, while microwaves pass through; at night only the active instruments continue to operate.
> 
> The family of active sensors. The radar family includes imaging synthetic aperture radar, scatterometers, altimeters and profiling sounders. Seasat (1978) was the first mission to carry a SAR, an altimeter and a scatterometer together (Raney, 2014, "Radars"). Altimeters are the simplest of these instruments in geometry: they look vertically downward and measure range. This presentation concerns the two types of altimeter, radar and laser.

---

## Slide 3 — From echo delay to surface height
*03 · Measurement principle*

1 cm ↔ 66.7 ps — two-way time per cm of range

8.9 ms — round trip from 1,336 km

3.3 ms — round trip from 496 km

> **Speaker notes**
> 
> The two governing equations. Range is obtained from the two-way travel time of the pulse: R = cΔt/2, where c is the speed of light and the factor of two accounts for the downward and return paths. Surface height then follows from h = H − R, where H is the height of the satellite above the reference ellipsoid (Magruder et al., 2024; Cheney, 2001).
> 
> Determining the orbit. The height H is obtained by precise orbit determination, which combines GNSS tracking, the DORIS network of ground beacons and satellite laser ranging. For Jason-class missions the radial orbit error is approximately 1 to 2 cm (Cheney, 2001; Escudier et al., 2018).
> 
> Propagation corrections. The atmosphere slows the pulse slightly, so the measured range is too long and must be corrected. The dry troposphere adds about 2.3 m of apparent range; water vapour adds from a few millimetres at high latitudes to approximately 40 cm in the tropics; and the ionosphere adds a few centimetres, rising to about 30 cm at solar maximum. Ocean waves introduce an additional sea-state bias (Escudier et al., 2018).
> 
> Reference surfaces. Heights are referred to the ellipsoid, a smooth mathematical approximation of the Earth. The geoid is the equipotential surface that a motionless ocean would adopt under gravity alone; its undulations are roughly one hundred times larger than the signals produced by tides and currents. The departure of sea level from the geoid, of the order of ±1 m, is the dynamic topography that reveals ocean circulation (Cheney, 2001).
> 
> Timing precision. One centimetre of range corresponds to 66.7 ps of two-way travel time. The round trip lasts approximately 8.9 ms from an altitude of 1,336 km and 3.3 ms from 496 km, so the timing system must resolve intervals some eight orders of magnitude smaller than the total travel time.

---

## Slide 4 — Where altimeters sit in the spectrum
*04 · Spectrum*

**Ionosphere delay shrinks with frequency**

All-weather; small ionospheric delay, removed with C-band.[1][9][10]

≈ 0.3 m range gates, smaller footprint, less snow penetration; rain-sensitive.[10]

10–25 m footprints, no ionospheric delay; blocked by cloud.[8][9]

> **Speaker notes**
> 
> Operating bands. Laser altimeters operate at 532 nm (green light, ICESat-2) and 1064 nm (near-infrared, GEDI). Radar altimeters operate principally in the Ku band at 13.6 GHz; the Ka band at 35.75 GHz is used by SARAL/AltiKa, SWOT and the forthcoming CRISTAL mission; and the C band at 5.3 GHz serves as a secondary frequency (Escudier et al., 2018).
> 
> Ionospheric delay. Free electrons in the ionosphere delay microwave signals in proportion to the inverse square of frequency (δR ∝ 1/f²). The delay is therefore smaller at higher frequencies and negligible at optical wavelengths. Dual-frequency altimeters, which measure in both Ku and C bands, estimate the delay directly and remove it (Amani et al., 2022). The Ka-band delay is approximately seven times smaller than the Ku-band delay (Escudier et al., 2018).
> 
> Trade-offs between bands. The Ku band is used for most missions because it penetrates cloud and most rain (Fischer et al., 2024). The Ka band provides a finer range resolution (0.30 m range gates compared with 0.47 m in Ku) and a smaller footprint, but it is more sensitive to rain. Lasers provide very small footprints but cannot measure through cloud.
> 
> L band. The L band (1 to 2 GHz, wavelengths of 15 to 30 cm) is used by imaging radars such as NISAR (1.257 GHz, 24 cm) rather than by altimeters. At L band the ionospheric delay is approximately 2.5 m even under quiet night-time conditions, about six times the S-band value and more than one hundred times the Ku-band value, because of the 1/f² dependence. Its ability to penetrate vegetation and dry snow, however, makes it well suited to SAR imaging.

---

## Slide 5 — How the radar footprint forms
*05 · Radar altimetry · how it works*

0.47 m — range resolution (320 MHz bandwidth) [10]

D ≈ 2.0 km — footprint, calm sea [3][5][11]

≈ 6.3 km — footprint at Hs = 4 m

≈ 2–9 kHz — pulse rate; echoes averaged against speckle [5][10]

> **Speaker notes**
> 
> Formation of the echo. The figure shows, from left to right, the expanding spherical shell of the radar pulse, the area of sea surface it illuminates, and the resulting received power as a function of time, known as the waveform.
> 
> Leading and trailing edges. The pulse first reaches the surface directly beneath the satellite. The illuminated area then grows rapidly as a disc, producing the steep leading edge of the waveform. Once the full pulse length has intersected the surface, the illuminated region becomes an annulus of constant area that expands outward into the weaker part of the antenna pattern, so the echo decays slowly; this is the trailing edge.
> 
> Pulse-limited footprint. The disc illuminated at the end of the leading edge is the pulse-limited footprint. It is approximately 2 km across over a calm sea and about 6 km in 4 m waves (Chelton et al., 1989), because waves spread the arrival times of the echo. Its diameter is given by D = 2√[2h(δR + Hs)/(1 + h/R_E)], where h is the altitude, δR the range resolution, Hs the significant wave height and R_E the Earth radius. Cheney (2001) reports a footprint of 2 to 3 km, and Raney (2014) 3 to 5 km depending on sea state.
> 
> Relation to the next slide. This animation shows the echo as the pulse sweeps across the entire antenna beam and is schematic. The instrument records only a short window near the leading edge, approximately 128 range samples. On Jason-2, the Poseidon-3 altimeter uses a 320 MHz chirp, which gives a range resolution of 47 cm (Escudier et al., 2018). The following slide examines that recorded window in detail.
> 
> Speckle. Each individual echo is affected by speckle, the random interference of returns from many surface facets. Averaging is therefore essential; Raney (2014) notes that 1,500 or more independent looks are averaged each second.

---

## Slide 6 — The echo waveform: what the radar records
*06 · Radar altimetry · the data*

simulated echoes every 0.8 km over ocean, coast, lake and land

**Record the echo**

Echo power vs. time in ~128 time bins[10]

**Fit a model shape**

"Retracking", e.g. the Brown ocean model[10][12]

> **Speaker notes**
> 
> The recorded waveform. A radar altimeter does not record a single number but a waveform: the echo power in approximately 100 to 128 range gates, each corresponding to about 0.47 m of range in the Ku band.
> 
> Retracking. Geophysical parameters are obtained by fitting a model waveform, such as the Brown (1977) ocean model, to the measured echo. The mid-point of the leading edge gives the two-way travel time and therefore the sea-surface height. The slope of the leading edge gives the significant wave height, since larger waves lengthen the rise time. The peak power, or backscatter coefficient, gives the wind speed, because a rougher sea scatters energy away from the satellite (Raney, 2014; Cheney, 2001).
> 
> Noise and averaging. A single echo is dominated by speckle. Averaging N echoes reduces the noise by a factor of √N, so altimeters average thousands of pulses per second. Fischer et al. (2024) note that approximately 1,000 waveforms are averaged to produce each 1 Hz measurement.
> 
> Other surfaces. Calm water in sea-ice leads produces a narrow, high-amplitude specular return. Ice sheets produce an extended trailing edge because the Ku-band signal penetrates dry snow and firn.
> 
> Along-track view. The three-dimensional view presents simulated echoes every 0.8 km along a track crossing open ocean, a coastline, a lake and land. Over the ocean the waveform takes the classical Brown shape. Within about 10 km of the coast, bright land enters the footprint before the satellite reaches it; its range exceeds the nadir range by approximately d²/2H less its elevation, so the spurious peak appears late in the window and moves earlier as the coast approaches, producing the parabolic signatures seen in real coastal radargrams. The lake produces a narrow specular spike, and over land the echo follows the terrain and fragments into several peaks, which is why land retracking is difficult.
> 
> Validation. In the Bering Sea, altimeter-derived significant wave heights agreed with NOAA buoy observations with a root-mean-square error of approximately 0.27 to 0.28 m and a correlation of 0.98 to 0.99 (Fischer et al., 2024).

---

## Slide 7 — Three radar geometries: disc, strip, swath
*07 · Radar altimetry · footprints*

**Conventional, pulse-limited**

- One echo from a 2–10 km disc[3][5]

- Jason-3, SARAL/AltiKa

**Delay-Doppler, along-track sharpened**

- Doppler slices: ~300 m along track

- CryoSat-2, Sentinel-3, Sentinel-6[10][13][14][15]

**Wide-swath interferometry (SWOT)**

- Two 50 km swaths, Ka-band

- Height from signal phase at two antennas[16]

> **Speaker notes**
> 
> Conventional low-resolution mode. In conventional (low-resolution mode) altimetry, each echo integrates over a disc approximately 2 to 10 km in diameter. This geometry is well suited to the open ocean, but near coasts the footprint frequently includes land.
> 
> Delay-Doppler (SAR) mode. In delay-Doppler mode the radar transmits bursts of 64 pulses. Because the satellite is moving, echoes from targets ahead of it are shifted slightly upward in frequency and those behind it slightly downward. Sorting the echoes by Doppler shift divides the beam into along-track strips of approximately 300 m; across track, each strip remains about 1.6 km wide. As the satellite advances it observes each strip repeatedly from different positions, and averaging these looks improves precision (Raney, 1998). This mode is used by CryoSat-2, Sentinel-3 and Sentinel-6. Escudier et al. (2018) give waveform footprint areas of about 300 km² for Jason, 100 km² for SARAL/AltiKa and about 5 km² for delay-Doppler processing, and Raney (2014) notes that delay-Doppler processing roughly halves the height noise.
> 
> Swath interferometry. SWOT carries two antennas separated by 10 m. The phase difference between the echoes received at each antenna determines the look angle and hence the height of every pixel across two 50 km swaths, providing the first two-dimensional maps of sea level (Morrow et al., 2019). Conventional radar resolution is typically 2 to 18 km (Amani et al., 2022).

---

## Slide 8 — Counting photons: ICESat-2 and GEDI
*08 · Laser altimetry · how it works*

**Laser**

532 nm, 10,000 pulses/s

**Beam splitter**

splits 1 pulse into 6 beams

**Ground spot**

≈ 11 m, every 0.7 m[8]

**Telescope**

0.8 m mirror

**Photon detector**

counts single photons

**Time of flight**

photon travel time gives height[4][17]

**6 beams in 3 pairs[8][17][18]**

**8 tracks, full waveform[8][19][20]**

> **Speaker notes**
> 
> Measurement chain. The ATLAS instrument on ICESat-2 fires 10,000 pulses of green (532 nm) light per second. A diffractive element divides each pulse into six beams. Footprints approximately 11 m in diameter are spaced 0.7 m apart along track, so they overlap to form continuous profiles. A 0.8 m telescope collects the returning light, and detectors record the arrival times of individual photons.
> 
> Photon budget. Approximately 300 trillion photons leave the instrument in each pulse, but only about a dozen are detected on return. For this reason ICESat-2 employs single-photon counting rather than recording a continuous waveform.
> 
> Beam geometry. The six beams are arranged in three pairs separated by 3.3 km. Each pair consists of a strong and a weak beam, with an energy ratio of about 4:1, separated by 90 m across track and 2.5 km along track because the beam pattern is rotated by approximately 2°. The paired beams allow the cross-track surface slope to be determined. The leading beam alternates when the spacecraft performs a yaw manoeuvre, approximately twice a year.
> 
> GEDI. GEDI, mounted on the International Space Station, uses three near-infrared (1064 nm) lasers to form four beams. Each beam is dithered across track on alternate shots, producing eight tracks spaced 600 m apart across a swath of about 4.2 km. Each beam fires 242 times per second, so each track receives a 25 m footprint approximately every 60 m, for a total of 968 footprints per second. GEDI therefore samples forest structure rather than mapping it continuously (Magruder et al., 2024; Dubayah et al., 2020).
> 
> Historical context. Bufton (1989) describes the principles of laser ranging and the small footprints it achieves, and notes that the first laser altimeters in space flew on Apollo 15, 16 and 17.

---

## Slide 9 — Photon clouds and full waveforms
*09 · Laser altimetry · the data*

**One 25 m footprint, one waveform[8][19]**

> **Speaker notes**
> 
> Photon clouds. The left panel presents a simulated ICESat-2 photon cloud, in which each point is a single detected photon. Dense bands correspond to reflecting surfaces, and scattered points are solar background noise, which is much reduced at night. Over forest, the separation between canopy and ground photons gives canopy height. Over sea ice, the height of floes relative to open leads gives freeboard. In shallow, clear water, green light reaches the seabed at depths of up to approximately 50 m (Magruder et al., 2024).
> 
> Full waveforms. The right panel illustrates GEDI full-waveform detection. As the pulse descends through the canopy, energy is returned first from the treetops, then from the mid-canopy and understorey, and finally from the ground, which produces the last strong peak. The relative-height metrics summarise this profile: RH98 approximates canopy height as the height below which 98 % of the returned energy lies, and RH50 marks the median energy height. These metrics are used to estimate above-ground biomass (Dubayah et al., 2020).
> 
> Three-dimensional view. The three-dimensional view represents the same physics over a 600 m by 240 m area sampled by one beam pair, with the weak beam carrying approximately one quarter of the energy of the strong beam and lying 90 m from it. Each scene is shown as a cut-away block. For sea ice, the side of the block shows the ice draft beneath each floe, roughly seven times the freeboard, so that approximately 90 % of the ice lies below the waterline. The profile and the three-dimensional view represent the same 600 m strip and share the same vertical exaggeration: ×49.7 for sea ice, ×4.1 for forest and ×6.2 for shallow water. The grey points indicate structure that the laser did not sample, emphasising that ICESat-2 produces profiles rather than maps.
> 
> Detection approaches. Magruder et al. (2024, Box 1) contrast full-waveform systems (GLAS, GEDI) with photon-counting systems (ATLAS). Bufton (1989) explains that the shape of the returned laser pulse records the vertical structure within the footprint.

---

## Slide 10 — Same target, different reflecting horizon
*10 · Interaction with the surface*

> **Speaker notes**
> 
> Principal point. Radar and laser altimeters observing the same location may reflect from different physical surfaces.
> 
> Behaviour over each surface. Over the ocean, both instruments measure the sea surface. Over sea ice, the laser reflects from the snow surface, whereas the Ku-band radar largely penetrates cold, dry snow and reflects near the snow–ice interface; the difference between the two gives snow depth, as discussed later. Over ice sheets, the radar penetrates dry snow and firn and therefore underestimates surface elevation slightly, while the laser measures the surface except where cloud intervenes. Over forest, the radar footprint is too large to resolve canopy structure, whereas the laser detects both treetops and the ground through canopy gaps. In coastal zones, the radar footprint includes land, while green laser light can reach the seabed.
> 
> Limitations. The assumption that the radar signal reaches the snow–ice interface fails for warm, wet or saline snow.
> 
> Sources. Magruder et al. (2024) describe radar footprints of about 3 km, penetration into snow and firn, and loss of tracking over steep terrain, together with the minimal surface penetration of laser altimeters. Amani et al. (2022) note that lasers cannot measure through thick cloud.

---

## Slide 11 — A 12 km × 12 km tile, as each sensor sees it
*11 · Footprints at a common scale*

**Layers**

**Zoom: 200 m × 120 m, true scale**

≈ 34,000 — ICESat-2 spots fit in one radar footprint [3][4][8]

> **Speaker notes**
> 
> A common scale. This figure places each sensor footprint on the same 12 km by 12 km tile at true scale; the GEDI footprints are enlarged by a factor of two for visibility. The blue disc is the conventional radar footprint, approximately 2 km in diameter, and the surrounding ring, about 6 km across, corresponds to the footprint in 4 m waves. The indigo strips are delay-Doppler cells of 0.3 km by 1.6 km. The green lines are the ICESat-2 beam pairs, separated by 3.3 km. The red points are GEDI tracks, and the amber strip is one swath of the future EDGE mission. The scale bar indicates 2 km at the centre of the tile, and the grid lines are spaced at 1 km.
> 
> Detailed view. The inset shows a 200 m by 120 m area at true scale, all of which lies within a single radar footprint.
> 
> The ratio of footprint areas. The figure of approximately 34,000 compares areas. A radar footprint 2 km in diameter covers about 3.2 km², whereas an ICESat-2 footprint of about 11 m covers approximately 95 m²; 3.2 million m² divided by 95 m² is approximately 34,000. The radar therefore averages over an area equivalent to tens of thousands of laser footprints. This is advantageous over the open ocean but blurs small features such as leads, crevasses and canopy gaps that the laser resolves.
> 
> Sources. Bufton (1989) notes that laser footprints are orders of magnitude smaller than radar footprints and that laser ranging does not require pulse averaging, because coherent fading is not a significant factor. The radar footprint of 2 to 3 km is from Cheney (2001), and the ICESat-2 footprint of 11 m from Magruder et al. (2024).

---

## Slide 12 — Five decades of altimetry missions
*12 · Missions*

**Global mean sea level from radar altimetry[3][10]**

Trend from published rates[21]

2.1 to 4.5 mm/yr — rise rate doubled, 1993–2023 [21]

17 Nov 2025 — Sentinel-6B launched [22]

> **Speaker notes**
> 
> Radar missions. Seasat (1978) demonstrated satellite radar altimetry, and TOPEX/Poseidon (1992) began the precise, continuous sea-level record. That record was continued by Jason-1, Jason-2 and Jason-3, Sentinel-6 (2020) and Sentinel-6B (November 2025). Other radar missions include CryoSat-2, designed for ice; SARAL/AltiKa, the first Ka-band altimeter; Sentinel-3; and SWOT (2022).
> 
> Laser missions. ICESat operated from 2003 to 2009, and ICESat-2 and GEDI have operated since 2018.
> 
> Planned missions. CRISTAL is planned for 2027 to 2028, Sentinel-6C for around 2030 and EDGE for 2030 to 2031.
> 
> Scientific significance. The combined record shows that global mean sea level rose by approximately 11 cm between 1993 and 2023, and that the rate of rise doubled from about 2.1 to 4.5 mm per year (Hamlington et al., 2024). The curve shown is the smoothed trend.
> 
> The value of multiple missions. Fischer et al. (2024) found that five or more altimeters were required to sample every winter storm in the Bering Sea; when only two or three were operating, 24 short-lived storms were missed. Regional sea level may also differ substantially from the global mean: in the North Atlantic subpolar gyre, altimetry reveals decadal trends of about −7.1 mm per year since the mid-2000s, driven by changes in ocean circulation (Chafik et al., 2019). Mission histories are summarised by Cheney (2001), Escudier et al. (2018) and Magruder et al. (2024).

---

## Slide 13 — From profiles to swaths: SWOT, CRISTAL, EDGE
*13 · Next generation*

**NASA · CNES · CSA · UKSA**

- 120 km swath, 20 km nadir gap

- 2-D maps of eddies, rivers, lakes

**ESA · Copernicus**

- First Ku + Ka interferometric altimeter

- Snow depth, sea-ice thickness[8][23]

**NASA Earth System Explorer**

- First global swath-imaging lidar

- Ice margins, glaciers, forests[24]

> **Speaker notes**
> 
> From profiles to swaths. The next generation of altimeters moves from single profiles toward wide-swath mapping.
> 
> SWOT. The Surface Water and Ocean Topography mission (NASA and CNES, launched 2022) measures a swath 120 km wide, resolving ocean eddies, rivers and lakes in two dimensions.
> 
> CRISTAL. The Copernicus Polar Ice and Snow Topography Altimeter (ESA, planned for 2027 to 2028) will be the first radar altimeter to operate in both Ku and Ka bands. The Ka-band signal reflects near the snow surface and the Ku-band signal near the ice surface, so a single satellite will be able to estimate snow depth on sea ice. Magruder et al. (2024) identify dual-band radar altimetry as an emerging approach to improving snow-depth estimates. CRISTAL will continue the CryoSat-2 record.
> 
> EDGE. EDGE (NASA, selected in January 2026, with launch planned for 2030 to 2031) will be the first laser altimeter to map swaths, five strips each 120 m wide, rather than profiles, with applications to ice-sheet margins, glaciers and forests. Magruder et al. (2024) noted that no laser altimetry mission was then planned to follow ICESat-2 and GEDI; EDGE addresses that gap.
> 
> Coverage per pass. The lower chart compares the width observed on each pass, from approximately 66 m for ICESat-2 to about 100 km for SWOT.

---

## Slide 14 — Radar vs laser altimetry, side by side
*14 · Scientific comparison*

**What must be corrected**

| Property | Radar altimetry | Laser altimetry |
|---|---|---|
| Wavelength | Ku / Ka (cm–mm) | 532 / 1064 nm (µm) |
| Footprint[4][8][10] | 2–10 km (LRM); 0.3 × 1.6 km (SAR) | 11 m (ICESat-2) · 25 m (GEDI) |
| Signal | averaged echo waveform | photons or full waveform |
| Weather[9] | all-weather, day & night | blocked by cloud |
| Penetration[8] | snow & firn | canopy gaps; clear water |
| Best for | sea level, waves, ice volume | ice detail, canopy, bathymetry |
| Record | continuous since 1992 | 2003–09 and 2018 onward |

> **Speaker notes**
> 
> Error budget. The left panel compares the magnitudes of the principal corrections on a logarithmic scale. Both techniques are affected by the dry troposphere, approximately 2.3 m, and by orbit error, approximately 1 to 3 cm. Water vapour, the ionosphere, sea-state bias and penetration into snow chiefly affect radar, whereas scattering by thin cloud affects only the laser (Escudier et al., 2018).
> 
> The underlying difference. The fundamental difference between the two techniques is wavelength: centimetres for radar and micrometres for laser. Wavelength determines footprint size, sensitivity to weather and the depth to which each signal penetrates the surface (Bufton, 1989; Magruder et al., 2024; Amani et al., 2022).
> 
> Conclusion. Radar altimetry provides a long, all-weather record, while laser altimetry provides fine spatial detail. The most robust results are obtained by combining the two.

---

## Slide 15 — Better together: one surface, two horizons
*15 · Synergy · conclusions · references*

Radar: all-weather record since 1992

Laser: metre-scale detail, canopy, seabed

Next: SWOT · CRISTAL · EDGE

> **Speaker notes**
> 
> Combining the two techniques: snow on sea ice. The laser measures the height of the snow surface above local sea level, the total freeboard F_L. The radar measures to approximately the ice surface, but its signal travels more slowly through snow, giving the radar freeboard F_R. Snow depth is then h_s = (F_L − F_R)/η_s, where η_s ≈ 1.2 corrects for the reduced propagation speed of radar in snow (Kwok et al., 2020). For example, a laser freeboard of 0.50 m and a radar freeboard of 0.20 m give a snow depth of approximately 24 cm.
> 
> Summary. Radar altimetry provides an all-weather record extending back to 1992. Laser altimetry provides fine spatial detail. Future missions, namely SWOT, CRISTAL and EDGE, extend both capabilities.
> 
> Anticipated questions. Why not rely on lasers alone? Clouds cover approximately two-thirds of the Earth at any time. Why not rely on radar alone? Its footprints are too large to resolve forests or narrow glaciers.
> 
> References. In the reference list, entries [1] to [10] are the course readings and entries [11] to [25] are additional sources. Kwok et al. (2020) describe the derivation of snow depth from laser and radar freeboards, and Magruder et al. (2024) review sea-ice and snow measurement by laser altimetry.

---

# References

## Course readings

1. Fischer, R., Farrell, S.L., Kuhn, J.M., & Duncan, K. (2024). Understanding decadal-scale dynamics in the Bering Sea: investigating trends and variability in sea ice, winds, and waves. J. Climate, 37(23), 6381–6394. <https://doi.org/10.1175/JCLI-D-23-0485.1>
2. Chafik, L., Nilsen, J.E.Ø., Dangendorf, S., Reverdin, G., & Frederikse, T. (2019). North Atlantic Ocean circulation and decadal sea level change during the altimetry era. Sci. Rep., 9, 1041. <https://doi.org/10.1038/s41598-018-37603-6>
3. Cheney, R.E. (2001). Satellite altimetry. In Encyclopedia of Ocean Sciences. Academic Press. <https://doi.org/10.1006/rwos.2001.0340>
4. Bufton, J.L. (1989). Laser altimetry measurements from aircraft and spacecraft. Proc. IEEE, 77(3), 463–477. <https://scholar.google.com/scholar?q=Bufton+1989+%22Laser+altimetry+measurements+from+aircraft+and+spacecraft%22>
5. Raney, R.K. (2014). Radar, altimeters. In E.G. Njoku (Ed.), Encyclopedia of Remote Sensing. Springer. <https://doi.org/10.1007/978-0-387-36699-9>
6. Raney, R.K. (2014). Radars. In E.G. Njoku (Ed.), Encyclopedia of Remote Sensing. Springer. <https://doi.org/10.1007/978-0-387-36699-9>
7. Glackin, D.L. (2014). Remote sensing, physics and techniques. In E.G. Njoku (Ed.), Encyclopedia of Remote Sensing. Springer. <https://doi.org/10.1007/978-0-387-36699-9>
8. Magruder, L.A., Farrell, S.L., Neuenschwander, A., Duncanson, L., Csatho, B., Kacimi, S., & Fricker, H.A. (2024). Monitoring Earth's climate variables with satellite laser altimetry. Nat. Rev. Earth Environ., 5, 120–136. <https://doi.org/10.1038/s43017-023-00508-8>
9. Amani, M., et al. (2022). Remote sensing systems for ocean: a review (Part 2: active systems). IEEE J. Sel. Top. Appl. Earth Obs. Remote Sens., 15, 1421–1453. <https://doi.org/10.1109/JSTARS.2022.3141980>
10. Escudier, P., et al. (2018). Satellite radar altimetry: principle, accuracy, and precision. In D. Stammer & A. Cazenave (Eds.), Satellite Altimetry over Oceans and Land Surfaces, 1–70. CRC Press. <https://doi.org/10.1201/9781315151779>

## Additional sources

11. Chelton, D.B., Walsh, E.J., & MacArthur, J.L. (1989). Pulse compression and sea level tracking in satellite altimetry. J. Atmos. Oceanic Technol., 6, 407–438. <https://scholar.google.com/scholar?q=Chelton+Walsh+MacArthur+1989+Pulse+compression+and+sea+level+tracking+in+satellite+altimetry>
12. Brown, G.S. (1977). The average impulse response of a rough surface and its applications. IEEE Trans. Antennas Propag., 25, 67–74. <https://doi.org/10.1109/TAP.1977.1141536>
13. Raney, R.K. (1998). The delay/Doppler radar altimeter. IEEE Trans. Geosci. Remote Sens., 36, 1578–1588. <https://doi.org/10.1109/36.718861>
14. Wingham, D.J., et al. (2006). CryoSat: a mission to determine the fluctuations in Earth's land and marine ice fields. Adv. Space Res., 37, 841–871. <https://doi.org/10.1016/j.asr.2005.07.027>
15. Donlon, C.J., et al. (2021). The Copernicus Sentinel-6 mission. Remote Sens. Environ., 258, 112395. <https://doi.org/10.1016/j.rse.2021.112395>
16. Morrow, R., et al. (2019). Global observations of fine-scale ocean surface topography with the SWOT mission. Front. Mar. Sci., 6, 232. <https://doi.org/10.3389/fmars.2019.00232>
17. Neumann, T.A., et al. (2019). The ICESat-2 global geolocated photon product (ATL03). Remote Sens. Environ., 233, 111325. <https://doi.org/10.1016/j.rse.2019.111325>
18. Smith, B., et al. ATLAS/ICESat-2 L3A Land Ice Height (ATL06) user guide: beam geometry and yaw orientation. NSIDC. nsidc.org <https://nsidc.org/sites/default/files/atl06-v002-userguide_1.pdf>
19. Dubayah, R., et al. (2020). The Global Ecosystem Dynamics Investigation. Sci. Remote Sens., 1, 100002. <https://doi.org/10.1016/j.srs.2020.100002>
20. GEDI mission team. GEDI instrument specifications. University of Maryland. gedi.umd.edu <https://gedi.umd.edu/instrument/specifications/>
21. Hamlington, B.D., et al. (2024). The rate of global sea level rise doubled during the past three decades. Commun. Earth Environ., 5, 601. <https://doi.org/10.1038/s43247-024-01761-5>
22. ESA (2025). Copernicus Sentinel-6B is launched, 17 November 2025. esa.int <https://www.esa.int/ESA_Multimedia/Videos/2025/11/Sentinel-6B_is_launched>
23. eoPortal (ESA). CRISTAL: Copernicus Polar Ice and Snow Topography Altimeter. eoportal.org <https://www.eoportal.org/satellite-missions/cristal>
24. NASA / Univ. of Maryland (2026). EDGE selected as a NASA Earth System Explorers mission. umd.edu <https://geog.umd.edu/featured-content/edge-mission-reaches-key-milestones-scientific-momentum-builds>
25. Kwok, R., et al. (2020). Arctic snow depth and sea ice thickness from ICESat-2 and CryoSat-2 freeboards. J. Geophys. Res. Oceans, 125, e2019JC016008. <https://doi.org/10.1029/2019JC016008>
