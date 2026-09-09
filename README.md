# Christchurch-SA2-Building-Coverage-Overture-Maps-vs-LINZ
A GIS comparison of building footprint coverage across Christchurch's 2026 SA2 study areas, combining citywide mapping with local aerial-imagery checks.

![Citywide coverage comparison, Top 10 ranking and scatterplot](images/overview.png)
*Project application screenshot. The map shows signed coverage differences; black outlines identify the Top 10 areas by absolute difference. The orange scatterplot line is a fitted regression, not a line of equality.*

## Project questions

- Where do Overture and LINZ produce different building coverage estimates?
- Which areas have the largest absolute differences?
- Can dated aerial imagery help explain the observed differences?

## Approach

QGIS was used to prepare boundaries and building footprints, calculate area-based coverage, and compare local geometries. ArcGIS Online and Experience Builder were used to present the SA2 comparison and imagery case study.

The study uses the Christchurch urban study extent, rather than the entire Christchurch City administrative area. Areas are calculated in NZTM2000 (EPSG:2193).

**Building coverage (%) = 100 × building footprint area within a study polygon / area of that same study polygon.**

**Coverage difference (pp) = Overture coverage − LINZ coverage.** Positive values indicate higher Overture coverage. The Top 10 chart ranks the absolute difference.

## Results and interpretation

- Burlington-Oakbridge has the largest displayed absolute difference: **6.75 percentage points**.
- The displayed SA2 scatterplot has **R² = 0.98**. This describes the fitted linear relationship, not accuracy or agreement with ground truth.
- In the Burlington-Oakbridge case study, several areas that were vacant or under construction in 2020–2021 contain completed buildings in 2025. These correspond to clusters of Overture-only coverage, supporting data currency as one explanation for the gap.
- For buildings present in both periods, differences also include roof-section coverage, boundary detail and alignment. Individual examples favour different datasets; neither is assumed to be ground truth.

These are selected case observations, not a citywide accuracy assessment. The proportion of the coverage gap attributable to construction has not been quantified.

## Local case study

![Experience Builder local case-study page with paired aerial imagery](images/Local Case Study.png)

*Case-study page preview showing the navigation and paired imagery presentation. Detailed evidence and interpretations follow below.*

| Case | Evidence | Interpretation |
|---|---|---|
| Construction between image dates | Vacant/construction sites in 2020–2021 and completed housing in 2025 | Differences in the period represented by the building data |
| Roof coverage differences | Roof sections visible in both periods included in LINZ but absent from the compared Overture outline | Local outline completeness or mapping-scope differences |
| Alignment and shape | Existing buildings with different offsets and corner configurations | Positional and shape disagreement; cause not conclusively established |

The same building dataset versions are overlaid on both imagery dates. The dates do not represent separate 2020 and 2025 building releases. The 2025 imagery is a comparison reference, not a confirmed source for Overture.

### Case 1 — Construction between image dates

| 2020–2021 aerial imagery | 2025 aerial imagery |
|---|---|
| ![Earlier imagery showing vacant sites and construction](images/case01_development_2020_2021.png) | ![Later imagery showing completed residential development](images/case01_development_2025.png) |

Several vacant or developing sites in the earlier image contain completed buildings by 2025. The central large building was already partly constructed in the earlier image, so it should not be classified as wholly absent at that time.

![Exclusive and shared building coverage over the earlier aerial imagery](images/case01_coverage_overlay.png)

*Coverage overlay on 2020–2021 imagery: blue = Overture only; pink = LINZ only; light grey = shared coverage. Colours indicate geometric coverage classes, not confirmed construction or demolition.*

Clusters of blue footprints correspond to several of the subsequently developed locations. Together, the imagery and overlay support data currency as an explanation for part of the SA2 coverage gap; its contribution has not been quantified.
