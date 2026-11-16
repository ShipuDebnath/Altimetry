# Radar & Laser Altimetry · Core version (slides 1–15)

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
