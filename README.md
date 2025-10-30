# utah-forge-drilling-data
Processed drilling logs from Utah FORGE deep geothermal test well (MU-ESW1) for validation of a directional drilling dynamics model and ML applications. GDR submission: https://gdr.openei.org/submissions/1006

## aggregated Pason logs (uncleaned, unfiltered)
Combined daily Pason drilling data into two continuous time-series regimes:
- Regime 1 (regime_2017-07-31_to_2017-08-26.csv): 7/31/17 - 8/26/17, depths 81-5708 ft
- Regime 2 (regime_2017-09-01_to_2017-09-13.csv): 9/1/17 - 9/13/17, depths 6507-7536 ft

Note: there's a ~800 ft data gap (5708-6507 ft) from 8/27/17 to 8/31/17 (files not in original GDR upload)

Data columns:
`Date`, `Time`, `Depth` (ft), `Block Ht` (ft), `Bit Depth` (ft), `ROP(1 ft)` (ft/hr), `ROP (1min)` (ft/hr), `Hookload` (klbs), `Surface Torque` (ft-lbs), `Rotary Speed` (RPM), `Pump Pressure` (psi), `Pump 1 SPM`, `Pump 2 SPM` (strokes/min), `Flow In`, `Flow Out` (gpm), `Pit Total` (bbls), `Temp In`, `Temp Out` (degF), `source_file`, `source_date`, and `regime`
Notes:
- First 18 cols are from the Pason log; last 3 cols are metadata I added during processing
- `Depth` is current hole depth, whereas  `Bit Depth` is bit position
- `ROP(1 ft)` is the instantaneous ROP over last 1 ft drilled
- `ROP (1min)` is smoothed 1-minute average ROP
- `Hookload` is the load on hook, a proxy for the axial force F(t)
- `Surface Torque` is torque at top drive, T(t) in the model
- `Rotary Speed` (RPM) is top drive rotation speed (=0 for pure mud motor drilling)
