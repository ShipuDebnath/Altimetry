# Radar & Laser Altimetry · Extended version

**Shipu Debnath**  
GEOG 789: Independent Study · Fall 2026  
Submitted to **Dr. Sinéad L. Farrell**, Associate Professor  
Department of Geographical Sciences, University of Maryland, College Park

Text version of the HTML deck: slide text, speaker notes and references. Interactive figures, 3D views and animations are only in the HTML file.

# Part 1 — Core deck (slides 1–15)

## Slide 1 — Radar & Laser Altimetry
*01 · Active remote sensing · Satellite altimetry*

Shipu Debnath

GEOG 789: Independent Study · Fall 2026

Submitted to

Dr. Sinéad L. Farrell, Associate Professor

Department of Geographical Sciences, University of Maryland, College Park

> **Speaker notes**
> 
> This presentation, prepared by Shipu Debnath for GEOG 789: Independent Study and submitted to Dr. Sinéad L. Farrell, Associate Professor in the Department of Geographical Sciences at the University of Maryland, College Park, examines how radar and laser altimeters measure the height of the Earth’s surface from orbit.
> 
> The measurement. Both instruments rely on the same principle. The altimeter transmits a short pulse toward the surface directly beneath it and records the time until the echo returns. That interval gives the range, and because the satellite’s position is known to about one centimetre, the range yields the height of the reflecting surface.
> 
> The figure. The globe is schematic and not to scale. The blue satellite represents a conventional radar altimeter such as Jason-3 or Sentinel-6, on a 66° orbit, with a footprint of roughly 2 to 10 km depending on sea state. The green satellite represents ICESat-2, on a 92° orbit, with six laser beams and footprints of about 11 m. The two orbits already indicate one theme of the talk: the reference radar record stops at 66° latitude, whereas ICESat-2 reaches 88°.
> 
> Outline. The presentation proceeds from the measurement principle and the choice of wavelength to radar and laser altimetry in turn, then compares how each interacts with different surfaces and at what spatial scale, reviews the mission record, and closes with the case for combining the two.
> 
> Sources. Cheney (2001); Escudier et al. (2018); Magruder et al. (2024).

---

## Slide 2 — Passive vs active remote sensing
*02 · Fundamentals*

**Records energy that is already there**

**Transmits a pulse and times its echo**

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
> Altimetry is best placed in context through the distinction between passive and active remote sensing.
> 
> Passive sensors. Passive sensors record energy that is already present: reflected sunlight, emitted thermal infrared radiation, or naturally emitted microwaves. Optical imagers, thermal sensors and microwave radiometers belong to this group. Their measurements describe what the surface is, in terms of radiance or temperature (Glackin, 2014).
> 
> Active sensors. Active sensors transmit their own signal and record the echo. Since the transmission time is known, the delay locates the surface; active sensors therefore describe where the surface is. Radar operates by day and night and through cloud (Amani et al., 2022).
> 
> Illumination and weather. The three panels show why this matters. On a clear day both classes receive a usable signal. Under overcast conditions, reflected sunlight and thermal infrared are blocked, while microwaves pass through the cloud. At night, reflected sunlight is absent, and only active instruments and emitted radiation remain available.
> 
> The family of active instruments. The lower row classifies active instruments by what they measure. Synthetic aperture radar forms side-looking images; scatterometers retrieve ocean wind vectors; profilers and sounders resolve the vertical structure of clouds, aerosols and ice. Radar and laser altimeters, the subject of this talk, look vertically downward and measure range: the radar with a footprint kilometres across, the laser with spots of a few metres to tens of metres (Raney, 2014, “Radars”).
> 
> An altimeter is therefore best understood as an active ranging instrument: its primary product is a distance, not an image.

---

## Slide 3 — From echo delay to surface height
*03 · Measurement principle*

1 cm ↔ 66.7 ps — two-way time per cm of range

8.9 ms — round trip from 1,336 km

3.3 ms — round trip from 496 km

**Equations**

$$R = \frac{c\,\Delta t}{2}$$

$$h = H - R$$

> **Speaker notes**
> 
> Every result in this talk rests on the principle summarised here.
> 
> Range and height. The range follows from the two-way travel time, $R = c\,\Delta t/2$, where $c$ is the speed of light. The surface height above the reference ellipsoid is then $h = H - R$, where $H$ is the altitude of the satellite above the same ellipsoid (Magruder et al., 2024; Cheney, 2001). The readout gives the travel time and range for each mission altitude shown: Sentinel-6 at 1,336 km, SWOT at 891 km, CryoSat-2 at 717 km and ICESat-2 at 496 km.
> 
> Orbit determination. $H$ is determined by precise orbit determination, combining three independent tracking systems: GNSS receivers on board, satellite laser ranging from ground stations, and the DORIS network of radio beacons. For the Jason series the radial orbit error is about 1 to 2 cm (Cheney, 2001; Escudier et al., 2018).
> 
> Range corrections. The atmosphere delays the pulse, so the uncorrected range is too long. The dry troposphere contributes about 2.3 m, water vapour from a few millimetres to about 40 cm, and the ionosphere a few centimetres, reaching about 30 cm at solar maximum. The sea-state bias is a further radar-specific correction. Each is modelled or measured and removed (Escudier et al., 2018).
> 
> Components of sea-surface height. Over the ocean, the corrected height can be written $h = N + \eta + \text{tides} + \mathrm{IB}$. $N$ is the geoid, the gravitational equipotential surface that a motionless ocean would follow; $\eta$ is the dynamic topography associated with ocean circulation; the tides are removed using models; and IB is the inverse-barometer response of the sea surface to atmospheric pressure. The geoid undulates by tens of metres, about one hundred times more than the oceanographic signal, while $\eta$ is of the order of ±1 m (Cheney, 2001; Escudier et al., 2018).
> 
> Timing requirement. A range change of one centimetre corresponds to 66.7 picoseconds of two-way travel time, whereas the full round trip lasts about 8.9 ms from Sentinel-6 and 3.3 ms from ICESat-2. Centimetre-level heights therefore require timing about eight orders of magnitude finer than the travel time itself, together with centimetre-level orbits and corrections.

---

## Slide 4 — Where altimeters sit in the spectrum
*04 · Spectrum*

**Ionosphere delay shrinks with frequency**

All-weather; small ionospheric delay, removed with C-band.[1][9][10]

≈ 0.3 m range gates, smaller footprint, less snow penetration; rain-sensitive.[10]

10–25 m footprints, no ionospheric delay; blocked by cloud.[8][9]

**Equations**

$$\delta R_{\mathrm{iono}} = \frac{40.3\,\mathrm{TEC}}{f^{2}}$$

> **Speaker notes**
> 
> The next consideration is the choice of wavelength, which determines much of an altimeter’s performance.
> 
> Bands in use. Laser altimeters operate at 532 nm, as on ICESat-2, and at 1064 nm, as on ICESat and GEDI. Radar altimeters operate mainly in the Ku band, at 13.6 GHz or a wavelength of 2.2 cm, used by the Jason series, Sentinel-3, Sentinel-6 and CryoSat-2, and in the Ka band, at 35.75 GHz or 8.4 mm, used by SARAL/AltiKa, SWOT and the forthcoming CRISTAL. The C band at 5.3 GHz and, on Envisat, the S band at 3.2 GHz have served as secondary frequencies. The L band at 1.26 GHz is shown for reference only; it is used by the NISAR imaging radar rather than by altimeters (Escudier et al., 2018).
> 
> Ionospheric delay. Free electrons in the ionosphere delay a radio signal by $\delta R_{\mathrm{iono}} = 40.3\,\mathrm{TEC}/f^{2}$, where TEC is the total electron content along the path. Because of the inverse-square dependence on frequency, the delay is about seven times smaller in Ka band than in Ku band and is negligible at optical wavelengths. It also scales with TEC, which is low on a quiet night and high near solar maximum. Dual-frequency measurement in Ku and C bands allows the delay to be estimated directly (Escudier et al., 2018; Amani et al., 2022).
> 
> Ku band. Ku band has been the standard frequency for ocean altimetry. It operates through cloud and most rain, and its ionospheric delay can be removed using the C-band channel (Fischer et al., 2024).
> 
> Ka band. Ka band provides finer range resolution, with range gates of about 0.3 m rather than 0.47 m, a smaller footprint and shallower penetration into snow. Its principal limitation is greater attenuation by rain (Escudier et al., 2018).
> 
> Laser. Lasers provide the finest spatial sampling, with footprints of 10 to 25 m and no ionospheric delay, but they cannot measure through cloud (Magruder et al., 2024; Amani et al., 2022).
> 
> In short, wavelength sets the balance between all-weather coverage and spatial detail.

---

## Slide 5 — How the radar footprint forms
*05 · Radar altimetry · how it works*

0.47 m — range resolution (320 MHz bandwidth) [10]

$D$ ≈ 2.0 km — footprint, calm sea [3][5][11]

≈ 6.3 km — footprint at $H_{\mathrm{s}}$ = 4 m

≈ 2–9 kHz — pulse rate; echoes averaged against speckle [5][10]

> **Speaker notes**
> 
> The radar altimeter is considered first, beginning with the formation of its echo.
> 
> Echo formation. The transmitted pulse expands as a spherical shell. It first reaches the surface at nadir, and the illuminated area then grows as a disc; this growth produces the steep leading edge of the waveform. Once the full pulse length has reached the surface, the illuminated area becomes an annulus of nearly constant area that moves outward into the weaker part of the antenna pattern, producing the slowly decaying trailing edge.
> 
> Range resolution. After pulse compression, a 320 MHz chirp bandwidth gives a range resolution of 0.47 m on Poseidon-3 (Escudier et al., 2018). The instrument records only a short window of about 128 range samples around the leading edge.
> 
> The pulse-limited footprint. The disc illuminated at the end of the leading edge defines the pulse-limited footprint, given by $D = 2\sqrt{2h(\delta R + H_{\mathrm{s}})/(1 + h/R_{\mathrm{E}})}$, where $h$ is the altitude, $\delta R$ the range resolution, $H_{\mathrm{s}}$ the significant wave height and $R_{\mathrm{E}}$ the Earth’s radius (Chelton et al., 1989). At the Jason and Sentinel-6 altitude of 1,336 km, $D$ is about 2 km over a calm sea, 6.3 km at $H_{\mathrm{s}} = 4$ m and about 10 km in high seas. From the lower orbit of CryoSat-2 the corresponding values are somewhat smaller. Throughout the presentation, the conventional radar footprint is therefore given as approximately 2 to 10 km, depending on sea state and altitude.
> 
> Speckle and averaging. Each echo is the coherent sum of returns from many scattering facets with random phases, so individual echoes are dominated by speckle noise. Altimeters therefore transmit at roughly 2 to 9 kHz and average many echoes; Raney (2014) notes that 1,500 or more independent looks are combined each second.
> 
> This kilometre-scale footprint is the fundamental spatial limit of conventional radar altimetry, and it recurs in every comparison that follows.

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
> The recorded echo, or waveform, is the basic radar altimeter measurement. Three geophysical quantities are derived from it in three steps.
> 
> Recording. The altimeter records echo power as a function of time in about 128 range gates, each corresponding to 0.47 m of range in Ku band (Escudier et al., 2018).
> 
> Retracking. A model waveform, over the ocean the Brown (1977) model, is fitted to the recorded echo. This procedure is known as retracking (Escudier et al., 2018).
> 
> Interpretation. The mid-point of the leading edge gives the two-way travel time, and hence sea-surface height. The slope of the leading edge gives significant wave height, because higher waves spread the arrival times and lengthen the rise; the example shown corresponds to $H_{\mathrm{s}} = 2.0$ m. The peak power, or backscatter coefficient $\sigma^{0}$, gives wind speed, because a wind-roughened surface scatters energy away from nadir (Raney, 2014; Cheney, 2001). In the Bering Sea, altimeter wave heights agreed with NOAA buoys to within about 0.27 to 0.28 m, with correlations of 0.98 to 0.99 (Fischer et al., 2024).
> 
> Averaging. A single echo is dominated by speckle. Averaging $N$ echoes reduces the noise approximately as $1/\sqrt{N}$, which is why about 1,000 waveforms are combined into each 1 Hz measurement (Fischer et al., 2024). The panel compares averages of 1, 10, 100 and 1,000 echoes.
> 
> Dependence on the surface. Waveform shape varies with the reflecting surface. The open ocean produces the classical Brown shape. Calm water in a sea-ice lead produces a narrow, intense specular return. An ice sheet produces an extended trailing edge, because Ku-band energy penetrates dry snow and firn and is scattered within the volume. Near coasts, land enters the footprint and introduces spurious peaks; this is why coastal and land retracking require specialised algorithms.
> 
> A single waveform thus provides height, wave height and wind speed, provided the retracker is matched to the surface.

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
> Radar altimetry is now practised in three geometries, shown here from left to right.
> 
> Conventional, pulse-limited mode. In low-resolution mode, each echo integrates over a disc of approximately 2 to 10 km, depending on sea state, within an antenna beam about 30 km wide. This mode, used by Jason-3 and SARAL/AltiKa, performs well over the open ocean but frequently includes land near the coast (Cheney, 2001; Raney, 2014).
> 
> Delay-Doppler mode. In delay-Doppler, or SAR, mode the radar transmits bursts of coherent pulses and sorts the echoes by Doppler frequency. This divides the footprint into along-track cells about 300 m long, while the across-track width remains about 1.6 km. Each cell is observed repeatedly as the satellite passes, and combining these looks approximately halves the height noise (Raney, 1998; Raney, 2014). The mode is used by CryoSat-2, Sentinel-3 and Sentinel-6.
> 
> Wide-swath interferometry. SWOT carries two Ka-band antennas separated by a 10 m boom. The phase difference between the echoes received at the two antennas gives the look angle, and therefore the height of each pixel, across two 50 km swaths. A conventional nadir altimeter covers the 20 km gap between them. The result is the first two-dimensional measurement of sea-surface height, in which individual eddies can be followed as they cross the swaths (Morrow et al., 2019).
> 
> Radar altimetry has thus progressed from a single footprint of several kilometres, to cells 300 m long, to two-dimensional swaths.

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
> Laser altimetry operates on the same timing principle, but the instrument design is quite different.
> 
> Measurement chain. ICESat-2 carries the ATLAS instrument, which emits 10,000 pulses of 532 nm light per second. A diffractive element splits each pulse into six beams. Each beam illuminates a ground spot about 11 m in diameter, and consecutive spots are 0.7 m apart along track, so they overlap to form continuous profiles. A 0.8 m telescope collects the returning light, single-photon detectors register each arrival, and the time of flight of each photon gives its height (Magruder et al., 2024; Neumann et al., 2019).
> 
> Photon budget. Of the roughly 300 trillion photons in each transmitted pulse, only about a dozen are detected on return. ICESat-2 therefore records individual photon arrivals rather than a full waveform.
> 
> Beam geometry. The six beams are arranged in three pairs about 3.3 km apart. Within each pair, a strong and a weak beam, with an energy ratio of about 4:1, are separated by 90 m across track, which allows the local cross-track slope to be estimated. The arrangement is reversed when the spacecraft performs its twice-yearly yaw manoeuvre.
> 
> GEDI. GEDI, mounted on the International Space Station, uses three 1064 nm lasers to produce four beams, which are dithered to generate eight ground tracks 600 m apart. Footprints are 25 m in diameter and spaced about 60 m along track, and the full return waveform is recorded for each shot. GEDI therefore samples forest structure rather than mapping it continuously (Magruder et al., 2024; Dubayah et al., 2020).
> 
> Historical note. Bufton (1989) set out the principles of space laser altimetry and the advantage of small footprints; the first such instruments flew on Apollo 15 to 17.
> 
> The two missions represent complementary designs: photon counting for dense, fine-scale profiles, and full-waveform recording for vegetation structure.

---

## Slide 9 — Photon clouds and full waveforms
*09 · Laser altimetry · the data*

**One 25 m footprint, one waveform[8][19]**

> **Speaker notes**
> 
> This slide shows what laser altimetry data look like in practice.
> 
> Photon clouds. Each point represents a single detected photon. Dense bands mark reflecting surfaces, while scattered points are solar background, which is substantially lower at night than in daylight. Three scenes are shown. Over forest, the vertical separation between canopy and ground photons gives canopy height. Over sea ice, floes stand above the water surface in leads, and that height difference is the freeboard. In clear shallow water, green light reaches the seabed at depths up to about 50 m (Magruder et al., 2024); the apparent depth must be divided by about 1.34 to correct for refraction.
> 
> Profile and three-dimensional view. The profile and the block diagram represent the same 600 m segment, sampled by one strong and one weak beam 90 m apart, and share the same vertical exaggeration: 49.7 for sea ice, 4.1 for forest and 6.2 for shallow water. The grey points indicate structure that the laser did not sample, a reminder that ICESat-2 produces profiles rather than maps.
> 
> GEDI waveforms. A GEDI shot returns a single waveform from a 25 m footprint. Energy from the upper canopy arrives first, followed by returns from the mid-canopy and understorey and finally from the ground. Relative-height metrics summarise the waveform: RH98 approximates canopy height and RH50 the median energy height, and these metrics are used to estimate above-ground biomass (Dubayah et al., 2020).
> 
> Data products. For ICESat-2, ATL03 contains the geolocated photons from which all higher-level products derive; ATL06 provides land-ice height, ATL07 and ATL10 sea-ice height and freeboard, ATL08 terrain and canopy height, and ATL13 inland water height. For GEDI, L2A provides the relative-height metrics and L4A and L4B provide footprint-level and gridded biomass.
> 
> Photon counting resolves fine-scale profiles across many surface types, while full-waveform recording captures the vertical structure of vegetation (Magruder et al., 2024, Box 1).

---

## Slide 10 — Same target, different reflecting horizon
*10 · Interaction with the surface*

> **Speaker notes**
> 
> An important consequence of the difference in wavelength is that radar and laser altimeters observing the same location may reflect from different physical surfaces.
> 
> Open ocean. Over the open ocean both instruments measure the mean sea surface.
> 
> Sea ice with snow. The laser reflects from the top of the snow cover. Ku-band radar largely penetrates cold, dry snow and reflects near the snow–ice interface. The difference between the two provides an estimate of snow depth.
> 
> Ice sheets. Radar returns include surface reflection and volume scattering within the firn, which biases elevations low by decimetres to metres. The laser measures the snow surface.
> 
> Forest. The radar footprint integrates canopy and ground together, whereas the laser records both the canopy top and, through gaps, the ground.
> 
> Coasts and shallow water. Land within the radar footprint contaminates the echo, although delay-Doppler processing reduces the effect. Green laser light can reach the seabed in clear water to about 50 m.
> 
> Cloud. The cloud case over the ice sheet illustrates the principal limitation of the laser: optically thick cloud blocks the beam, while the radar continues to measure (Amani et al., 2022).
> 
> A caveat. The assumption that Ku-band radar reaches the snow–ice interface breaks down for warm, wet or saline snow, which reflects the signal from within the snowpack.
> 
> These differing reflecting horizons introduce error when they are ignored, but they become a source of information when the two measurements are combined (Magruder et al., 2024).

---

## Slide 11 — A 12 km × 12 km tile at a common scale
*11 · Footprints at a common scale*

**Layers**

**Zoom: 200 m × 120 m, true scale**

≈ 34,000 — ICESat-2 spots fit in one radar footprint [3][4][8]

> **Speaker notes**
> 
> To compare spatial scales directly, this slide places each footprint on a single 12 km by 12 km tile at true scale.
> 
> The layers. The blue disc is a conventional radar footprint of about 2 km diameter, or 3.2 km², corresponding to a calm sea; the outer ring indicates its size at a significant wave height of 4 m. A delay-Doppler cell covers about 0.3 by 1.6 km, or 0.49 km². The green lines are the three ICESat-2 beam pairs, 3.3 km apart, each spot covering about 95 m². GEDI footprints of 25 m, or 491 m², are drawn at twice their true size for visibility. The amber strip is a single 120 m swath of the planned EDGE mission. The scale bar shows 2 km and the grid spacing is 1 km.
> 
> True-scale inset. The inset shows an area of 200 by 120 m drawn at true scale, all of it lying within a single radar footprint, with ICESat-2 spots and complete GEDI footprints.
> 
> Ratio of areas. About 34,000 ICESat-2 footprints fit within one calm-sea radar footprint, that is, 3.2 km² divided by roughly 95 m². In high seas, with a radar footprint near 10 km, the ratio exceeds 800,000. The radar averages over this entire area, which is appropriate for the open ocean but smooths out leads, crevasses and canopy gaps that the laser resolves (Bufton, 1989; Cheney, 2001; Magruder et al., 2024).
> 
> Footprint area, spanning more than four orders of magnitude, largely determines which surface features each sensor can resolve.

---

## Slide 12 — Five decades of altimetry missions
*12 · Missions*

**Global mean sea level from radar altimetry[3][10]**

Trend from published rates[21]

2.1 to 4.5 mm/yr — rise rate doubled, 1993–2023 [21]

17 Nov 2025 — Sentinel-6B launched [22]

> **Speaker notes**
> 
> The mission record and the climate data record it has produced are summarised here.
> 
> Radar missions. Seasat in 1978 demonstrated satellite radar altimetry, and Geosat, from 1985 to 1990, mapped the marine geoid. TOPEX/Poseidon, launched in 1992, began the high-precision reference record, which was continued by Jason-1, Jason-2, Jason-3, Sentinel-6 in 2020 and Sentinel-6B, launched on 17 November 2025. ERS-1, ERS-2 and Envisat extended coverage toward the poles; CryoSat-2, launched in 2010, was designed for the cryosphere; SARAL/AltiKa, in 2013, was the first Ka-band altimeter; and Sentinel-3 and SWOT followed.
> 
> Laser missions. ICESat operated from 2003 to 2009, and ICESat-2 and GEDI have operated since 2018 (Magruder et al., 2024).
> 
> Planned missions. CRISTAL, planned for 2027 to 2028, Sentinel-6C, around 2030, and EDGE, in 2030 to 2031, will extend the record.
> 
> Global mean sea level. The reference missions show that global mean sea level rose by about 11 cm between 1993 and 2023, and that the rate of rise approximately doubled over that period, from about 2.1 to 4.5 mm per year (Hamlington et al., 2024). The curve shows the smoothed trend.
> 
> The value of multiple missions. Record continuity depends on overlapping reference missions, and sampling improves with the number of satellites in orbit. Fischer et al. (2024) found that five or more altimeters were needed to sample every winter storm in the Bering Sea. Regional records may also depart markedly from the global mean: in the North Atlantic subpolar gyre, sea level has fallen by about 7.1 mm per year since the mid-2000s (Chafik et al., 2019).
> 
> Radar altimetry has thus supplied a continuous climate record since 1992, and laser altimetry has added a polar and terrestrial record since 2003.

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
> The next generation of missions extends altimetry from profiles to swaths.
> 
> SWOT. The Surface Water and Ocean Topography mission, a partnership of NASA, CNES, the Canadian Space Agency and the UK Space Agency, has operated since 2022. It measures a 120 km swath, comprising two 50 km swaths separated by a 20 km nadir gap, and maps ocean eddies, rivers and lakes in two dimensions.
> 
> CRISTAL. The Copernicus Polar Ice and Snow Topography Altimeter, to be launched by ESA in 2027 to 2028, will be the first interferometric altimeter operating in both Ku and Ka bands. Because Ka-band energy reflects near the snow surface and Ku-band energy near the snow–ice interface, snow depth and sea-ice thickness can be retrieved from a single platform. Magruder et al. (2024) identify dual-band radar as a promising route to improved snow depth. CRISTAL will also continue the CryoSat-2 record.
> 
> EDGE. EDGE, selected by NASA in January 2026 as an Earth System Explorer for launch in 2030 to 2031, will be the first global swath-imaging lidar, mapping five strips each 120 m wide over ice-sheet margins, glaciers and forests. Magruder et al. (2024) noted that no laser altimetry mission was planned beyond ICESat-2 and GEDI; EDGE addresses that gap.
> 
> Coverage per pass. The lower chart compares the width observed on each pass, from about 66 m for ICESat-2 to 2 to 10 km for a nadir radar and about 100 km for SWOT.
> 
> Both radar and laser altimetry are therefore moving from measuring lines to measuring surfaces.

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
> This slide brings the preceding material together in a direct comparison.
> 
> Error budget. The left panel compares the principal corrections on a logarithmic scale. Both techniques share the dry-troposphere correction, of about 2.3 m, and the orbit error, of about 1 to 3 cm. Water vapour, the ionosphere, sea-state bias and penetration into snow are predominantly radar issues, whereas scattering by thin cloud affects only the laser (Escudier et al., 2018).
> 
> Wavelength and footprint. Radar wavelengths are of the order of centimetres to millimetres, laser wavelengths of the order of a micrometre. The radar footprint is about 2 to 10 km in conventional mode and about 0.3 by 1.6 km in delay-Doppler mode, compared with 11 m for ICESat-2 and 25 m for GEDI (Bufton, 1989; Escudier et al., 2018; Magruder et al., 2024).
> 
> Signal and weather. The radar records an averaged echo waveform; the laser records individual photons or a full waveform. Radar operates in all weather, day and night, whereas the laser is blocked by cloud (Amani et al., 2022).
> 
> Penetration and applications. Radar penetrates snow and firn; laser light passes through canopy gaps and clear water (Magruder et al., 2024). Radar is best suited to sea level, waves and ice volume, and the laser to fine-scale ice features, canopy height and shallow bathymetry.
> 
> Record length. The radar record has been continuous since 1992; the laser record covers 2003 to 2009 and 2018 onward.
> 
> Almost every difference in the table follows from wavelength, and the strengths of each technique correspond closely to the limitations of the other.

---

## Slide 15 — Better together: one surface, two horizons
*15 · Synergy · conclusions · references*

Radar: all-weather record since 1992

Laser: metre-scale detail, canopy, seabed

Next: SWOT · CRISTAL · EDGE

**Equations**

$$h_{\mathrm{s}} = \frac{F_{\mathrm{L}} - F_{\mathrm{R}}}{\eta_{\mathrm{s}}}$$

> **Speaker notes**
> 
> The core presentation closes with an example of how the two techniques are combined.
> 
> Snow depth from two freeboards. The laser measures the total freeboard, $F_{\mathrm{L}}$, the height of the snow surface above local sea level. The radar measures the radar freeboard, $F_{\mathrm{R}}$, close to the ice surface but slightly reduced because the signal travels more slowly through snow. Snow depth is then $h_{\mathrm{s}} = (F_{\mathrm{L}} - F_{\mathrm{R}})/\eta_{\mathrm{s}}$, where $\eta_{\mathrm{s}} \approx 1.2$ accounts for the slower propagation (Kwok et al., 2020). With $F_{\mathrm{L}} = 0.50$ m, $F_{\mathrm{R}} = 0.20$ m and a snow density $\rho_{\mathrm{s}} = 0.30$ g cm⁻³, the snow depth is approximately 24 cm.
> 
> Conclusions. First, radar altimetry provides the all-weather record that has run continuously since 1992. Second, laser altimetry provides metre-scale detail of ice, vegetation and the seabed. Third, the forthcoming missions, SWOT, CRISTAL and EDGE, extend both techniques into two dimensions.
> 
> Anticipated questions. If asked why lasers alone are not sufficient: cloud covers about two-thirds of the Earth at any given time. If asked why radar alone is not sufficient: its footprint is too large to resolve forest structure, narrow glaciers or individual leads.
> 
> References. References 1 to 10 are the course readings; references 11 to 25 are additional sources. Questions are welcome.

---

# Part 2 — Polar extension (slides 16–23)

## Slide 16 — The Arctic, Greenland and the North Atlantic from orbit
*16 · Polar extension · Arctic focus*

**How far north does each satellite see?**

4.60 M km² — Sept 2025 sea-ice minimum, tied 10th lowest [26]

19 of 19 — lowest minima all fall in 2007–2025 [26]

−129 Gt — Greenland mass change 2025 (2003–24 mean −219 Gt/yr) [27]

> **Speaker notes**
> 
> The following section applies these techniques to the study region of this independent study: the Arctic Ocean, Greenland and the North Atlantic.
> 
> Circulation. The schematic polar stereographic map shows the principal pathways. Warm Atlantic water flows north along Norway and enters Fram Strait as the West Spitsbergen Current. The Transpolar Drift carries sea ice across the pole and out through Fram Strait into the East Greenland Current. The anticyclonic Beaufort Gyre stores freshwater in the western Arctic.
> 
> Latitude limits. For a nadir-looking altimeter, the maximum latitude observed equals 180° minus the orbital inclination. CryoSat-2, ICESat-2 and CRISTAL reach 88° N; Sentinel-3 reaches 81.4° N; Jason-3 and Sentinel-6 reach only 66° N and therefore do not observe the Arctic Ocean. NISAR, a left-looking imaging radar, reaches 77.5° N, so Sentinel-1 provides coverage of the high Arctic (Magruder et al., 2024).
> 
> Recent conditions. The September 2025 sea-ice minimum was 4.60 million km², tied for the tenth lowest in the satellite record, and the nineteen lowest minima have all occurred between 2007 and 2025 (NSIDC). Greenland lost 129 Gt of ice in 2025, less than its 2003–2024 mean of 219 Gt per year but still a net loss (NOAA Arctic Report Card).
> 
> In the Arctic, orbital inclination determines coverage, and only a small number of missions observe the central Arctic Ocean.

---

## Slide 17 — NISAR: the first L- and S-band radar imager
*17 · Polar extension · NISAR*

SweepSAR: transmit lights the whole 242 km swath; a narrow receive beam follows the echo from near to far range.

**Look left or right: which pole is seen?**

> **Speaker notes**
> 
> Altimeters measure height; the study of ice dynamics also requires motion, which is the contribution of NISAR.
> 
> Instrument. NISAR is an imaging radar rather than an altimeter: it views the surface obliquely and forms images. It carries NASA’s L-band radar, at a wavelength of 24 cm, and ISRO’s S-band radar, at about 10 cm, the first pairing of these two frequencies on one satellite, behind a 12 m deployable reflector.
> 
> Orbit and coverage. The satellite flies a 747 km dawn–dusk orbit inclined at 98.4°, images a 242 km swath and revisits every 12 days, with pixel sizes of 3 to 10 m depending on mode. It was launched on 30 July 2025, and calibrated L-band data have been publicly available since 20 July 2026.
> 
> SweepSAR. A wide swath ordinarily comes at the expense of resolution. NISAR avoids this trade-off: on transmission the antenna illuminates the full 242 km swath, and on reception a narrow beam electronically follows the echo from near range to far range.
> 
> Polar coverage. A side-looking radar observes only one side of its ground track. Looking left provides complete coverage of Antarctica but limits Arctic coverage to 77.5° N. NISAR looks left, so Sentinel-1 and other radars are required for the high Arctic.
> 
> NISAR therefore contributes frequent, high-resolution measurements of surface motion, although not at the highest Arctic latitudes.

---

## Slide 18 — Ice motion: interferometry and feature tracking
*18 · Polar extension · how NISAR measures motion*

**Phase change between two passes gives surface motion**

**Matching ice patterns between passes gives drift**

Altimeter thickness + SAR drift = ice volume leaving the Arctic. Fram Strait: ≈2,400 km³/yr (1992–2014)[34]

**Equations**

$$\Delta r = \frac{\lambda}{4\pi}\,\Delta\varphi$$

$$Q = \int h\,u\,C\,\mathrm{d}x$$

> **Speaker notes**
> 
> This slide describes the two methods by which imaging radar measures ice motion, and how motion and altimetry combine to give ice flux.
> 
> Interferometry. The phase of a radar echo depends on the distance to the surface. A displacement $\Delta r$ between two acquisitions changes the phase by $\Delta\varphi = 4\pi\,\Delta r/\lambda$, so each fringe corresponds to half a wavelength of motion along the line of sight: 12 cm at L band, about 5 cm at S band and about 2.8 cm at C band. L band therefore produces more widely spaced fringes and retains coherence longer over snow and ice. Over the fast-flowing trunk of a glacier, twelve days of motion produces fringes too dense to resolve. The interferogram shown is synthetic.
> 
> Feature tracking. Feature tracking identifies the same surface pattern in two images and measures its displacement. It is suited to fast glaciers and drifting sea ice; NISAR’s sea-ice requirement is a resolution of 100 m per day on a 5 km grid.
> 
> Ice flux. The ice volume flux through a gate is $Q = \int h\,u\,C\,\mathrm{d}x$, combining thickness from altimetry, drift velocity from radar and ice concentration, integrated across the gate. Through Fram Strait the flux averaged about 2,400 km³ per year over 1992–2014 (Spreen et al., 2020). Because Fram Strait lies north of NISAR’s coverage limit, drift there is obtained from Sentinel-1.
> 
> Altimetry supplies thickness, imaging radar supplies drift, and together they quantify the export of ice from the Arctic.

---

## Slide 19 — Sea-ice thickness from freeboard
*19 · Polar extension · sea ice*

$\rho_{\mathrm{w}}$ 1024 · $\rho_{\mathrm{i}}$ 917 (FYI) / 882 (MYI) · $\rho_{\mathrm{s}}$ 300 kg m⁻³[36]. About 90 % of the ice is under water, so 1 cm of freeboard ≈ 10 cm of ice.

**Leads give the sea-level reference[8]**

Mirror-like water in a lead returns a sharp spike; rough floes return a broad echo. Peakiness sorts them[35].

**Equations**

$$h_{\mathrm{i}} = \frac{\rho_{\mathrm{w}} F_{\mathrm{i}} + \rho_{\mathrm{s}} h_{\mathrm{s}}}{\rho_{\mathrm{w}} - \rho_{\mathrm{i}}}$$

> **Speaker notes**
> 
> Sea-ice thickness cannot be measured directly from orbit; it is inferred from freeboard.
> 
> Hydrostatic balance. Sea ice floats in hydrostatic equilibrium, so its freeboard constrains its total thickness: $h_{\mathrm{i}} = (\rho_{\mathrm{w}} F_{\mathrm{i}} + \rho_{\mathrm{s}} h_{\mathrm{s}})/(\rho_{\mathrm{w}} - \rho_{\mathrm{i}})$. Here the seawater density $\rho_{\mathrm{w}}$ is 1024 kg m⁻³, the ice density $\rho_{\mathrm{i}}$ is 917 kg m⁻³ for first-year and 882 kg m⁻³ for multiyear ice, and the snow density $\rho_{\mathrm{s}}$ is 300 kg m⁻³ (Alexandrov et al., 2010). Because the denominator is small, about 90 % of the ice lies below the waterline, and 1 cm of freeboard corresponds to roughly 10 cm of thickness.
> 
> Sensor reference surfaces. The laser measures the total freeboard to the snow surface; Ku-band radar measures to near the snow–ice interface, with a small correction for slower propagation in snow. Additional snow loading depresses the floe, and sufficient snow can reduce the freeboard to zero and flood the ice surface.
> 
> Leads as the sea-level reference. Freeboard requires the local sea level, which is obtained from leads. Calm lead water produces a sharp specular radar return, whereas rough, snow-covered floes produce a diffuse echo; the pulse peakiness parameter is used to distinguish the two (Laxon et al., 2013; Magruder et al., 2024).
> 
> Since a 1 cm error in sea level or freeboard propagates into about 10 cm of thickness, centimetre-level ranging is essential.

---

## Slide 20 — Snow: the largest uncertainty in sea-ice thickness
*20 · Polar extension · snow*

**Arctic snow depth, October 2018 to April 2019 (ICESat-2 minus CryoSat-2)[25]**

**Same snow error, opposite thickness error**

Combine them: the errors cancel. Hence CryoSat-2 + ICESat-2 today and Ku + Ka on CRISTAL next.

**Equations**

$$\frac{\partial h_{\mathrm{i}}}{\partial h_{\mathrm{s}}} = -\frac{\rho_{\mathrm{w}} - \rho_{\mathrm{s}}}{\rho_{\mathrm{w}} - \rho_{\mathrm{i}}}$$

$$\frac{\partial h_{\mathrm{i}}}{\partial h_{\mathrm{s}}} = \frac{\rho_{\mathrm{w}}(\eta_{\mathrm{s}} - 1) + \rho_{\mathrm{s}}}{\rho_{\mathrm{w}} - \rho_{\mathrm{i}}}$$

> **Speaker notes**
> 
> Snow on sea ice is the largest single source of uncertainty in thickness retrievals.
> 
> Observed snow depth. By differencing ICESat-2 and CryoSat-2 freeboards across the Arctic, Kwok et al. (2020) found mean snow depth increasing from 9 cm in late October to 19 cm in April, with greater depths on multiyear ice, 14 to 27 cm, than on first-year ice, 5 to 17 cm. Snow accounted for about half of the laser freeboard in every month.
> 
> Opposite sensitivities. An error in the assumed snow depth changes the laser-derived thickness by $-(\rho_{\mathrm{w}} - \rho_{\mathrm{s}})/(\rho_{\mathrm{w}} - \rho_{\mathrm{i}})$, about −6.8 per unit for first-year ice, and the radar-derived thickness by $[\rho_{\mathrm{w}}(\eta_{\mathrm{s}} - 1) + \rho_{\mathrm{s}}]/(\rho_{\mathrm{w}} - \rho_{\mathrm{i}})$, about +5.1 per unit. A 5 cm snow error therefore produces about −34 cm of error for the laser and +25 cm for the radar.
> 
> Combining sensors. Because these errors are of opposite sign, combining laser and radar constrains snow depth and ice thickness jointly. This principle underlies the orbit alignment of CryoSat-2 and ICESat-2 and the dual-band design of CRISTAL. It assumes that the radar reaches the snow–ice interface, which may fail for saline or wet snow (Kacimi & Kwok, 2020).
> 
> Context. Laser and radar altimetry together indicate that Arctic winter sea-ice volume decreased by about 6,000 km³, roughly one third, between 2003 and 2021 (Magruder et al., 2024).

---

## Slide 21 — Greenland: thinning seen by radar and laser
*21 · Polar extension · Greenland*

−1.2 m — mean thinning 2010–2023 [38]

−6.4 m — in the melt (ablation) zone [38]

3 % — CryoSat-2 vs ICESat-2 agreement [38]

**Elevation change along an outlet glacier**

Radar: all-weather; km footprint, echo from the nearest slope point; enters dry firn[8]

Laser: 11 m spots on steep margins; surface only; stopped by cloud[8]

> **Speaker notes**
> 
> For the Greenland Ice Sheet, radar and laser altimetry together document sustained thinning.
> 
> Observed change. A joint ESA–NASA analysis found that CryoSat-2 and ICESat-2 elevation changes agree to within 3 %. Between 2010 and 2023 the ice sheet thinned by 1.2 m on average and by 6.4 m in the ablation zone, where summer melt exceeds accumulation, with maximum thinning of 67 m at Sermeq Kujalleq, also known as Jakobshavn Isbræ, and 75 m at Zachariæ Isstrøm (CPOM, 2024).
> 
> Spatial pattern. The schematic map shows the consistent pattern: little change in the high interior and the strongest thinning along the margins and fast-flowing outlet glaciers. North of 77.5° N, Sentinel-1 rather than NISAR observes glacier flow.
> 
> Along-flow profile. The illustrative profile shows thinning greatest near the calving front, about 4 to 6 m per year at Jakobshavn and Kangerlussuaq (Smith et al., 2020), and decreasing inland. The record combines ICESat from 2003 to 2009, CryoSat-2 from 2010 and ICESat-2 from 2018.
> 
> Radar and laser over ice sheets. Radar operates in all weather, but over sloping terrain its kilometre-scale footprint returns the echo from the point of closest approach rather than from nadir, and it penetrates dry firn. The laser resolves 11 m footprints on steep margins and reflects from the surface, but it is interrupted by cloud (Magruder et al., 2024).
> 
> From elevation to mass. Volume change multiplied by density gives mass change, and the choice of density, whether of ice or firn, is a principal source of uncertainty. Greenland and Antarctica together lost about 320 Gt per year over 2003–2019, equivalent to about 14 mm of global sea-level rise (Magruder et al., 2024, citing Smith et al., 2020).

---

## Slide 22 — Sea level under the ice: leads, gyres, freshwater
*22 · Polar extension · Arctic Ocean & North Atlantic*

4,600 km³ — freshwater gained by the Beaufort Gyre by 2010 (vs 2003–06) [40]

≈2,400 km³/yr — sea ice exported through Fram Strait 1992–2014, falling 27 %/decade [34]

**Arctic to North Atlantic[2]**

**Equations**

$$\eta = \mathrm{SSH} - N$$

$$\mathbf{u}_{\mathrm{g}} = \frac{g}{f}\,\hat{\mathbf{k}} \times \nabla\eta$$

> **Speaker notes**
> 
> This slide links altimetric measurements beneath the Arctic sea ice to freshwater storage and to the North Atlantic.
> 
> Sea level from leads. In ice-covered regions, a radar altimeter observes the ocean surface only through leads. Specular lead echoes sample sea level, while diffuse floe echoes provide freeboard.
> 
> Dynamic topography and geostrophic flow. Subtracting the geoid from sea-surface height gives the dynamic topography, $\eta = \mathrm{SSH} - N$, and its gradient gives the geostrophic velocity, $\mathbf{u}_{\mathrm{g}} = (g/f)\,\hat{k} \times \nabla\eta$. The Beaufort Gyre appears as a dome of elevated sea level with anticyclonic circulation, supported by a thick layer of low-density freshwater.
> 
> Freshwater and ice export. Combining radar altimetry with GRACE, Armitage et al. (2016) estimated that the Beaufort Gyre had accumulated about 4,600 km³ of freshwater by 2010 relative to 2003–2006. CryoSat-2 now provides monthly fields of Arctic sea level and geostrophic currents to 88° N (Doglioni et al., 2023). Sea-ice export through Fram Strait averaged about 2,400 km³ per year over 1992–2014, declining by about 27 % per decade (Spreen et al., 2020).
> 
> Connection to the North Atlantic. Arctic freshwater exits through Fram Strait and Davis Strait toward the Labrador and Irminger Seas, where winter convection contributes to the Atlantic Meridional Overturning Circulation. Increased freshwater input could reduce surface density and weaken convection, although this remains an open question. Altimetry already documents strong decadal variability in the region: subpolar-gyre sea level rose by about 3.9 mm per year from the early 1990s and fell by about 7.1 mm per year from the mid-2000s, as the gyre first warmed and then cooled and intensified (Chafik et al., 2019).

---

## Slide 23 — Polar take-aways
*23 · Polar extension · summary · references*

**Height and thickness**

Radar and laser altimeters: sea level in leads, sea-ice freeboard, ice-sheet elevation.

**Motion**

SAR (NISAR, Sentinel-1): glacier speed and sea-ice drift. Thickness × drift = volume flux.

**Mind the gaps**

Pole holes: 66° N (Jason), 77.5° N (NISAR), 81.4° N (Sentinel-3), 88° N (CryoSat-2, ICESat-2).

**Snow is the key unknown**

Laser and radar err in opposite directions; CRISTAL's Ku + Ka is built for this.

> **Speaker notes**
> 
> To close the polar section, four points summarise the role of altimetry in this region.
> 
> Height and thickness. Radar and laser altimeters measure sea level in leads, sea-ice freeboard and thus thickness, and ice-sheet elevation change.
> 
> Motion. Imaging radars such as NISAR and Sentinel-1 measure glacier velocity and sea-ice drift; combined with thickness, these give volume flux.
> 
> Coverage limits. Orbital inclination limits what each mission observes: 66° N for the Jason series, 77.5° N for NISAR, 81.4° N for Sentinel-3 and 88° N for CryoSat-2 and ICESat-2.
> 
> Snow. Snow depth remains the principal unknown for sea-ice thickness. Laser and radar errors act in opposite directions, and CRISTAL’s dual Ku- and Ka-band design is intended to address it.
> 
> References. The extension references continue the main numbering from reference 26 onward.

---

# Part 3 — Key terms (slides 24–32, T1–T9)

## T1 — Measuring height: range, orbit, geoid
*T1 · Key terms · Measuring height*

Everything is measured from the same zero: the ellipsoid. schematic

**Range ($R$)**

Distance from the satellite down to the surface, from the pulse’s two-way travel time: $R$ = $c$Δ$t$/2.[8][3]

Why it matters: It is the only thing the altimeter itself measures.

**Orbit height ($H$) and ellipsoid**

$H$ is the satellite’s height above the reference ellipsoid, a smooth flattened sphere used as height zero. Precise orbit determination (GNSS, DORIS, laser ranging) gives $H$ to about 1 cm.[10]

Why it matters: Any orbit error goes straight into sea level.

**Geoid**

The level surface a still ocean would follow under gravity alone. Its bumps reach about 200 m peak-to-peak; a seamount raises the sea about 1 m.[3]

Why it matters: The sea follows the geoid to within 1–2 %, so it must be removed to resolve currents.

**Sea surface height (SSH)**

SSH = $H$ − $R$: the height of the sea surface above the ellipsoid.[3][10]

Why it matters: The basic altimetry product behind every ocean study.

**Mean sea surface and SLA**

MSS is SSH averaged over several years. Sea-level anomaly SLA = SSH − MSS.[10]

Why it matters: The subpolar-gyre trends in Chafik et al. are SLA trends[2].

> **Speaker notes**
> 
> The following key-terms slides define the vocabulary of the course readings, beginning with the quantities from which every altimetric height is constructed.
> 
> Range. The distance from the satellite to the surface, obtained from the two-way travel time as $R = c\,\Delta t/2$; it is the only quantity the altimeter measures directly (Magruder et al., 2024; Cheney, 2001).
> 
> Orbit height and the ellipsoid. $H$ is the satellite’s height above the reference ellipsoid, the smooth mathematical surface that serves as the height datum; it is determined from GNSS, DORIS and laser ranging to about 1 cm (Escudier et al., 2018).
> 
> Geoid. The equipotential surface that a motionless ocean would follow under gravity alone, with undulations of about 200 m peak to peak. The sea surface follows it to within 1–2 %, so it must be removed before currents can be resolved (Cheney, 2001).
> 
> Sea-surface height. $\mathrm{SSH} = H - R$, the height of the sea surface above the ellipsoid.
> 
> Mean sea surface and sea-level anomaly. The mean sea surface is SSH averaged over several years; the sea-level anomaly is the departure of SSH from that mean (Escudier et al., 2018).
> 
> The subpolar-gyre trends reported by Chafik et al. (2019) are expressed as sea-level anomalies.

---

## T2 — What changes the pulse on its way
*T2 · Key terms · Corrections*

Each layer slows the pulse; the corrections remove that extra range. schematic

**Dry troposphere**

Delay from the gases of the atmosphere, about 2.3 m of extra range. Computed from surface pressure in weather models.[10]

Why it matters: The largest correction, but smooth and well known.

**Wet troposphere**

Delay from water vapour and cloud: a few millimetres near the poles up to about 40 cm in the tropics. Measured by a radiometer on board.[10]

Why it matters: Patchy in space and time, so it limits accuracy.

**Ionosphere**

Delay from free electrons high in the atmosphere, up to about 30 cm at solar maximum. Removed by measuring at two frequencies (Ku and C).[10][9]

Why it matters: Lasers do not feel it; radars must correct it.

**Sea-state bias**

Wave troughs reflect more radar power than crests, so the measured surface sits low, by as much as tens of centimetres. Corrected from wave height and wind.[10]

Why it matters: Still one of the main radar error sources.

**Precise orbit determination**

Tracking the satellite with GNSS, DORIS beacons and laser ranging; about 1 cm for Jason-class orbits.[10]

Why it matters: Enables a sea-level record good to millimetres per year.

> **Speaker notes**
> 
> These terms describe the corrections applied to the measured range; magnitudes are from Escudier et al. (2018).
> 
> Dry troposphere. The delay due to atmospheric gases, about 2.3 m, computed from surface pressure in numerical weather models; it is the largest correction but also the most predictable.
> 
> Wet troposphere. The delay due to water vapour and cloud liquid water, from millimetres at high latitudes to about 40 cm in the tropics, measured by an onboard microwave radiometer. Its spatial variability limits accuracy.
> 
> Ionosphere. The delay due to free electrons, up to about 30 cm near solar maximum, removed by dual-frequency measurement; lasers are unaffected (Amani et al., 2022).
> 
> Sea-state bias. Wave troughs reflect more radar energy than crests, so the measured mean surface lies too low, typically by a few per cent of the significant wave height; it is corrected empirically from wave height and wind speed.
> 
> Precise orbit determination. Tracking of the satellite by GNSS, DORIS and laser ranging to about 1 cm radial accuracy, which makes a sea-level record at millimetre-per-year precision possible.

---

## T3 — Reading the radar echo
*T3 · Key terms · Reading the echo*

One waveform gives height, wave height and wind. schematic

**Waveform**

The echo’s power against time, recorded in 128 range gates, each 0.47 m in Ku band.[10]

Why it matters: The raw data behind every radar height.

**Leading edge and retracking**

Retracking fits a model shape (for example the Brown model) to the echo. The mid-point of the leading edge gives the range.[10][5]

Why it matters: Different surfaces (ocean, leads, ice sheets) need different retrackers.

**Speckle**

Random flicker in each echo, because many surface facets add up with random phases. Thousands of echoes are averaged each second.[5][1]

Why it matters: Why one radar echo is never used alone.

**Significant wave height (SWH)**

A standard measure of wave size. Rougher seas spread the echo, so SWH grows with the rise time of the leading edge.[5]

Why it matters: Altimeter SWH matched Bering Sea buoys to about 0.27 m[1].

**Backscatter ($\sigma^{0}$)**

The strength of the echo. Wind roughens the sea and scatters power away, so σ⁰ falls as wind speed rises.[5][3]

Why it matters: Gives wind speed along every altimeter track.

> **Speaker notes**
> 
> These terms describe the radar echo and the quantities derived from it.
> 
> Waveform. Echo power as a function of time, recorded in 128 range gates of 0.47 m each in Ku band (Escudier et al., 2018).
> 
> Leading edge and retracking. Retracking fits a model waveform, such as the Brown model, to the echo; the mid-point of the leading edge defines the range. Different surfaces require different retrackers.
> 
> Speckle. Random fluctuation in individual echoes arising from the coherent sum of many facets with random phases. Thousands of echoes are averaged each second (Raney, 2014), about 1,000 per 1 Hz measurement (Fischer et al., 2024).
> 
> Significant wave height. The mean height of the highest third of waves, derived from the rise time of the leading edge (Raney, 2014).
> 
> Backscatter coefficient. $\sigma^{0}$, the normalised echo strength, which decreases as wind roughens the sea surface and therefore yields wind speed (Raney, 2014; Cheney, 2001).
> 
> Fischer et al. (2024) validated altimeter wave heights against Bering Sea buoys to within about 0.27 m.

---

## T4 — Footprints: what each sensor measures
*T4 · Key terms · Footprints*

The footprint sets the smallest feature a sensor can see. schematic

**Footprint**

The patch of ground that sends the echo back.[4]

Why it matters: Sets whether a lead, a glacier or a tree can be seen.

**Pulse-limited**

Footprint set by the short pulse length, not the antenna. For a radar it is about 2 km across over a calm sea and widens to about 10 km in high seas.[5]

Why it matters: Conventional radar altimeters work this way.

**Beam-limited**

Footprint set by the width of the beam. A laser’s beam is so narrow that its pulse- and beam-limited footprints are the same.[4][5]

Why it matters: Why laser spots are tens of metres, not kilometres.

**Delay-Doppler (SAR mode)**

Uses the Doppler shift to divide the footprint into strips about 300 m long along track, and roughly halves the height noise.[10][5]

Why it matters: Lets CryoSat-2 and Sentinel-3 pick out leads in sea ice.

**Full waveform vs photon counting**

GEDI records the whole returned pulse; ICESat-2 detects single photons at 10,000 pulses per second.[8]

Why it matters: Waveforms show canopy layers; photons give fine-scale profiles.

> **Speaker notes**
> 
> These terms concern footprints, the main distinction between radar and laser altimetry.
> 
> Footprint. The area of the surface that contributes to the echo; it sets the smallest resolvable feature (Bufton, 1989).
> 
> Pulse-limited footprint. A footprint defined by the pulse length rather than the antenna beam. For a radar altimeter it is about 2 km across over a calm sea and widens to about 10 km in high seas (Raney, 2014; Chelton et al., 1989).
> 
> Beam-limited footprint. A footprint defined by the beam width. A laser beam is so narrow that its pulse-limited and beam-limited footprints coincide, giving spots of a few metres to tens of metres (Bufton, 1989).
> 
> Delay-Doppler mode. Doppler processing that divides the radar footprint into along-track cells about 300 m long and approximately halves the height noise (Escudier et al., 2018; Raney, 2014).
> 
> Full waveform and photon counting. GEDI records the complete return pulse, whereas ICESat-2 detects individual photons at 10,000 pulses per second (Magruder et al., 2024).
> 
> The 300 m delay-Doppler cells are what allow CryoSat-2 and Sentinel-3 to detect individual leads in sea ice.

---

## T5 — Sea-ice words: leads, floes, freeboard
*T5 · Key terms · Sea ice*

Freeboard is measured; thickness is calculated from it. schematic

**Lead**

A crack of open water (or new thin ice) between floes. It gives the local sea level.[8]

Why it matters: The reference level for every freeboard.

**Floe**

A single piece of floating sea ice. Most of its thickness, the draft, is under water.[8]

Why it matters: Floes and leads mix within one radar footprint.

**Freeboard**

How high the ice sits above local sea level. A laser measures to the snow surface (total freeboard); a Ku-band radar mainly to the ice surface.[8]

Why it matters: Converted to thickness using snow depth and densities.

**Snow depth**

The snow layer on the ice. It can be estimated from laser minus radar freeboard, or from dual-band radar.[8][25]

Why it matters: The largest uncertainty in sea-ice thickness.

**Marginal ice zone (MIZ)**

The outer edge of the pack, where waves break the ice into small floes. Sea ice damps waves and shelters the coast.[8][1]

Why it matters: Less ice lets bigger waves reach the shore[1].

> **Speaker notes**
> 
> These terms form the sea-ice vocabulary for freeboard and thickness; definitions follow Magruder et al. (2024).
> 
> Lead. A linear opening of open water or thin new ice between floes, which provides the local sea-level reference.
> 
> Floe. A discrete piece of floating sea ice, most of whose thickness, the draft, lies below the waterline.
> 
> Freeboard. The height of the ice above local sea level. The laser measures to the snow surface, giving total freeboard; Ku-band radar measures mainly to the ice surface.
> 
> Snow depth. The thickness of the snow layer on the ice, estimated from the difference between laser and radar freeboards or from dual-band radar (Kwok et al., 2020); it is the largest source of uncertainty in thickness.
> 
> Marginal ice zone. The outer region of the pack, where waves break the ice into small floes. Sea ice attenuates waves and shelters the coast (Fischer et al., 2024).
> 
> These are the quantities measured in the seas surrounding Greenland.

---

## T6 — Reading currents from sea level
*T6 · Key terms · Ocean currents*

Slopes of about a metre across an ocean drive the main currents. schematic

**Dynamic topography**

Sea surface minus the geoid. Its highs and lows are about ±1 m.[3][10]

Why it matters: This is the signal that maps currents.

**Geostrophic current**

Flow balanced between the push down the sea-surface slope and the Coriolis force from Earth’s spin. It follows the height contours.[3]

Why it matters: Lets altimetry map currents without a current meter.

**Gyre**

A basin-wide loop of currents. In the Northern Hemisphere flow is clockwise round highs and anticlockwise round lows.[3]

Why it matters: The North Atlantic has a subtropical and a subpolar gyre[2].

**Western boundary current**

The fast, narrow current on the west side of a gyre, such as the Gulf Stream. Its sea level varies by up to about 30 cm (rms).[3]

Why it matters: The most variable part of the ocean.

**Eddy (mesoscale)**

A rotating ring of water 100–300 km across, shed by meandering currents.[3]

Why it matters: Altimeter sea-level maps track eddies week by week.

> **Speaker notes**
> 
> These terms describe how ocean currents are inferred from sea-surface height.
> 
> Dynamic topography. Sea-surface height minus the geoid, with highs and lows of about ±1 m (Cheney, 2001).
> 
> Geostrophic current. Flow in which the horizontal pressure gradient associated with the sea-surface slope balances the Coriolis force, so that water moves along contours of constant height; in the Northern Hemisphere, higher sea level lies to the right of the flow.
> 
> Gyre. A basin-scale circulation: anticyclonic, or clockwise, around a high and cyclonic around a low in the Northern Hemisphere.
> 
> Western boundary current. The fast, narrow current on the western side of a gyre, such as the Gulf Stream, where sea-level variability reaches about 30 cm rms.
> 
> Mesoscale eddy. A rotating feature 100 to 300 km across shed by meandering currents and tracked from week to week in altimeter maps.
> 
> The North Atlantic contains both a subtropical and a subpolar gyre (Chafik et al., 2019).

---

## T7 — North Atlantic: gyres and the overturning
*T7 · Key terms · North Atlantic*

Subpolar sea level rose, then fell, as the gyre changed. schematic

**Subpolar gyre (SPG)**

The anticlockwise loop of currents south of Greenland, around the Labrador and Irminger Seas. Sea level there rose about 3.9 mm/yr from the early 1990s, then fell about 7.1 mm/yr from the mid-2000s.[2]

Why it matters: Shows regional sea level can move opposite to the global rise.

**Gulf Stream and North Atlantic Current**

The warm current that carries heat north-east. Its sea level changes in the opposite direction to the subpolar gyre (a dipole).[2]

Why it matters: The two regions must be read together.

**AMOC**

Atlantic Meridional Overturning Circulation: warm water flows north near the surface, sinks in the north, and returns south at depth. It weakened from the mid-2000s.[2]

Why it matters: Moves heat that shapes North Atlantic and Arctic climate.

**Deep convection**

In winter, cooling makes surface water dense enough to sink, mainly in the Labrador and Irminger Seas.[2]

Why it matters: Changes in convection may drive gyre shifts.

**Steric and dynamic sea level**

Steric: sea level changes because water expands or shrinks with temperature and salinity. Dynamic: changes from currents.[2]

Why it matters: Subpolar trends follow steric changes driven by circulation.

> **Speaker notes**
> 
> These terms describe the North Atlantic circulation that is central to this study; definitions and figures are from Chafik et al. (2019).
> 
> Subpolar gyre. The cyclonic gyre south of Greenland, encompassing the Labrador and Irminger Seas. Its sea level rose by about 3.9 mm per year from the early 1990s and fell by about 7.1 mm per year from the mid-2000s.
> 
> Gulf Stream and North Atlantic Current. The warm current system carrying heat north-eastward; its sea level varies in opposition to that of the subpolar gyre, forming a dipole.
> 
> Atlantic Meridional Overturning Circulation. The circulation in which warm surface water flows north, sinks at high latitudes and returns south at depth; it weakened from the mid-2000s.
> 
> Deep convection. The winter sinking of dense surface water, principally in the Labrador and Irminger Seas, which may drive shifts in the gyre.
> 
> Steric and dynamic sea level. Steric change results from expansion or contraction of seawater with temperature and salinity; dynamic change results from circulation. Subpolar trends are dominated by steric changes driven by circulation.

---

## T8 — Storms, winds and waves from orbit
*T8 · Key terms · Storms and waves*

More satellites in orbit mean fewer storms slip between the tracks. schematic

**Sea-ice extent**

The area where ice concentration is at least 15 %. In the Bering Sea, 9 of the 10 winters from 2014 to 2023 had unusually low extent.[1]

Why it matters: Less ice means more open water for storms to act on.

**Extratropical cyclone**

A low-pressure storm outside the tropics (poleward of 30°). Cyclone Merbok in September 2022 drove waves over 15 m in the Bering Sea.[1]

Why it matters: Main source of extreme winds and waves at high latitude.

**Wave damping by sea ice**

Sea ice weakens waves and protects the coast. Without it, more wave energy reaches the shore.[1]

Why it matters: Links ice loss to coastal flooding and erosion.

**Altimeter constellation**

Several altimeters flying at once. Five or more were needed to sample regional storms well; with only two or three, short storms were missed.[1]

Why it matters: Why multi-mission records matter.

**Reanalysis and buoys**

ERA5 reanalysis blends a weather model with observations into a continuous record. Buoys measure waves in place and check the satellites.[1]

Why it matters: Altimeter wave heights matched buoys to about 0.27 m.

> **Speaker notes**
> 
> These terms concern storms, winds and waves; definitions and figures are from Fischer et al. (2024), co-authored by Dr. Farrell.
> 
> Sea-ice extent. The area with at least 15 % ice concentration. In the Bering Sea, nine of the ten winters from 2014 to 2023 had anomalously low extent.
> 
> Extratropical cyclone. A low-pressure system poleward of 30° latitude. Cyclone Merbok in September 2022 generated waves exceeding 15 m in the Bering Sea.
> 
> Wave attenuation by sea ice. Sea ice damps wave energy and protects the coast; reduced ice cover allows more wave energy to reach the shore.
> 
> Altimeter constellation. Several altimeters operating simultaneously. Five or more were required to sample every regional storm; with only two or three, short-lived storms were missed.
> 
> Reanalysis and in-situ validation. ERA5 combines a numerical weather model with observations to produce a continuous record, and buoys validate altimeter wave heights to within about 0.27 m.
> 
> The same methods could be applied to the seas surrounding Greenland.

---

## T9 — Ice-sheet words: firn, mass balance, thinning
*T9 · Key terms · Ice sheets*

Altimeters measure height change; mass needs firn density too. schematic

**Firn**

Old snow slowly compacting into ice near the surface. Radar signals penetrate into it; firn models are needed to turn height change into mass.[8]

Why it matters: A key source of uncertainty for radar over Greenland.

**Surface mass balance**

Snowfall added at the surface minus melt and runoff.[8]

Why it matters: Separates weather-driven change from ice flow.

**Outlet glacier and dynamic thinning**

Fast-flowing glaciers drain the ice sheet into the ocean. When they speed up, for example with warmer ocean water, they thin.[8]

Why it matters: Most Greenland thinning is at these margins.

**Elevation change (d$h$/d$t$)**

Repeat altimetry measures how fast the surface height changes; combined with density this gives mass change.[8]

Why it matters: How ICESat, CryoSat-2 and ICESat-2 track ice loss.

**Sea-level contribution**

Greenland and Antarctica together lost about 320 Gt of ice per year in 2003–2019, about 14 mm of global sea level.[8]

Why it matters: Ice loss is now a major part of sea-level rise.

> **Speaker notes**
> 
> The final key-terms slide defines the ice-sheet vocabulary used to interpret elevation change; definitions and figures follow Magruder et al. (2024).
> 
> Firn. Multi-year snow in the process of compacting into glacial ice. Radar penetrates it, and firn models are required to convert elevation change into mass change.
> 
> Surface mass balance. Accumulation from snowfall minus losses from surface melt and runoff.
> 
> Outlet glaciers and dynamic thinning. Fast-flowing glaciers that drain the ice sheet into the ocean and thin when they accelerate, for example in response to warmer ocean water.
> 
> Elevation change rate. $\mathrm{d}h/\mathrm{d}t$, the rate of surface-height change from repeat altimetry; multiplied by density, it gives mass change.
> 
> Sea-level contribution. Greenland and Antarctica together lost about 320 Gt per year over 2003–2019, equivalent to about 14 mm of global sea-level rise.
> 
> Greenland’s outlet glaciers form part of the study region.

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

## Extension references

26. NSIDC / CIRES (2025). Arctic sea ice has reached minimum extent for 2025. 17 Sept 2025. colorado.edu <https://cires.colorado.edu/news/arctic-sea-ice-has-reached-minimum-extent-2025>
27. NOAA (2025). Arctic Report Card 2025: Greenland Ice Sheet. noaa.gov <https://arctic.noaa.gov/?p=11279>
28. NASA JPL. NISAR observatory: the L-SAR and S-SAR radars. jpl.nasa.gov <https://nisar.jpl.nasa.gov/mission/observatory/radars/>
29. eoPortal (ESA). NISAR (NASA-ISRO Synthetic Aperture Radar): orbit and performance. eoportal.org <https://www.eoportal.org/satellite-missions/nisar>
30. ISRO (2025). GSLV-F16 / NISAR mission, launched 30 July 2025, Sriharikota. isro.gov.in <https://www.isro.gov.in/Mission_GSLVF16_NISAR.html>
31. ASF DAAC (2026). NISAR L-band data now publicly available (from 20 July 2026). alaska.edu <https://asf.alaska.edu/notices/nisar-l-band-data-now-publicly-available/>
32. NASA JPL. NISAR observation strategy (left-looking; Arctic pole filled by other SARs). jpl.nasa.gov <https://nisar.jpl.nasa.gov/mission/observation-strategy/>
33. Rosen, P., et al. (2021). NISAR mission overview and requirements (incl. sea-ice velocity). CEOS LPV plenary. nasa.gov <https://lpvs.gsfc.nasa.gov/PDF/LPV_plenary_2021/Day1/20210524_CEOS_NISAR.pdf>
34. Spreen, G., et al. (2020). Arctic sea ice volume export through Fram Strait from 1992 to 2014. J. Geophys. Res. Oceans, 125, e2019JC016039. <https://doi.org/10.1029/2019JC016039>
35. Laxon, S.W., et al. (2013). CryoSat-2 estimates of Arctic sea ice thickness and volume. Geophys. Res. Lett., 40, 732–737. <https://doi.org/10.1002/grl.50193>
36. Alexandrov, V., et al. (2010). The relation between sea ice thickness and freeboard in the Arctic. The Cryosphere, 4, 373–380. <https://doi.org/10.5194/tc-4-373-2010>
37. Kacimi, S., & Kwok, R. (2020). The Antarctic sea ice cover from ICESat-2 and CryoSat-2: freeboard, snow depth, and ice thickness. The Cryosphere, 14, 4453–4474. <https://doi.org/10.5194/tc-14-4453-2020>
38. ESA (2024). ESA and NASA deliver first joint picture of Greenland Ice Sheet melting (CPOM study, Geophys. Res. Lett.). esa.int <https://www.esa.int/Applications/Observing_the_Earth/FutureEO/CryoSat/ESA_and_NASA_deliver_first_joint_picture_of_Greenland_Ice_Sheet_melting>
39. Smith, B., et al. (2020). Pervasive ice sheet mass loss reflects competing ocean and atmosphere processes. Science, 368, 1239–1242. <https://doi.org/10.1126/science.aaz5845>
40. Armitage, T.W.K., et al. (2016). Arctic sea surface height variability and change from satellite radar altimetry and GRACE, 2003–2014. J. Geophys. Res. Oceans, 121, 4303–4322. <https://doi.org/10.1002/2015JC011579>
41. Doglioni, F., et al. (2023). Sea surface height anomaly and geostrophic current velocity from altimetry over the Arctic Ocean (2011–2020). Earth Syst. Sci. Data, 15, 225. <https://doi.org/10.5194/essd-15-225-2023>
