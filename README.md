## Event-Level Variables
| Variable Name | Type     | Description                         | User Functions                                       |
|---------------|----------|-------------------------------------|------------------------------------------------------|
| `runID`       | `int`    | Identifier for the current run      | `SQEvent::get_run_id()`                              |
| `spillID`     | `int`    | Identifier for the spill in the run | `SQEvent::get_spill_id()`                            |
| `eventID`     | `int`    | Unique identifier for the event     | `SQEvent::get_event_id()`                            |
| `rfID`        | `int`    | Identifier for the RF               | `SQEvent::get_qie_rf_id()`                           |
| `turnID`      | `int`    | Identifier for the Turn             | `SQEvent::get_qie_turn_id()`                         |
| `fpgaTrigger` | `int[5]` | Array of FPGA triggers              | `SQEvent::get_trigger(SQEvent::MATRIX1..MATRIX5)`    |
| `nimTrigger`  | `int[5]` | Array of NIM triggers               | `SQEvent::get_trigger(SQEvent::NIM1..NIM5)`          |
| `rfIntensity` | `int[33]`| Array for QIE RF intensities        | `SQEvent::get_qie_rf_intensity(i)` (i = -16..16)     |

## Hit-Level Variables  
| Variable Name  | Type                 | Description                         | User Functions                           |
|----------------|----------------------|-----------------------------------|--------------------------------------------|
| `hitID`        | `std::vector<int>`   | Hit IDs for all hits               | `SQHit::get_hit_id()`                     |
| `hitTrackID`   | `std::vector<int>`   | Track IDs for all hits             | `SQHit::get_track_id()`                   |
| `processID`    | `std::vector<int>`   | Process IDs (encoded) for hits    | Custom encoding function (`EncodeProcess`) |
| `detectorID`   | `std::vector<int>`   | Detector IDs for all hits          | `SQHit::get_detector_id()`                |
| `elementID`    | `std::vector<int>`   | Element IDs associated with hits  | `SQHit::get_element_id()`                  |
| `driftDistance`| `std::vector<double>`| Drift distances for each hit      | `SQHit::get_drift_distance()`              |
| `tdcTime`      | `std::vector<double>`| TDC timing values for each hit    | `SQHit::get_tdc_time()`                    |
## Monte Carlo Truth-Level Variables

| Variable Name | Type                  | Description                              | User Functions                      |
|---------------|-----------------------|----------------------------------------|---------------------------------------|
| `gCharge`     | `std::vector<int>`    | Charges of the Monte Carlo tracks      | `SQTrack::get_charge()`               |
| `gvx`         | `std::vector<double>` | X-coordinate of the generated vertex  | `SQTrack::get_pos_vtx().X()`           |
| `gvy`         | `std::vector<double>` | Y-coordinate of the generated vertex  | `SQTrack::get_pos_vtx().Y()`           |
| `gvz`         | `std::vector<double>` | Z-coordinate of the generated vertex  | `SQTrack::get_pos_vtx().Z()`           |
| `gpx`         | `std::vector<double>` | X-component of momentum at vertex     | `SQTrack::get_mom_vtx().Px()`          |
| `gpy`         | `std::vector<double>` | Y-component of momentum at vertex     | `SQTrack::get_mom_vtx().Py()`          |
| `gpz`         | `std::vector<double>` | Z-component of momentum at vertex     | `SQTrack::get_mom_vtx().Pz()`          |
| `gx_st1`      | `std::vector<double>` | X-coordinate at station 1              | `SQTrack::get_pos_st1().X()`          |
| `gy_st1`      | `std::vector<double>` | Y-coordinate at station 1              | `SQTrack::get_pos_st1().Y()`          |
| `gz_st1`      | `std::vector<double>` | Z-coordinate at station 1              | `SQTrack::get_pos_st1().Z()`          |
| `gpx_st1`     | `std::vector<double>` | X-component of momentum at station 1  | `SQTrack::get_mom_st1().Px()`          |
| `gpy_st1`     | `std::vector<double>` | Y-component of momentum at station 1  | `SQTrack::get_mom_st1().Py()`          |
| `gpz_st1`     | `std::vector<double>` | Z-component of momentum at station 1  | `SQTrack::get_mom_st1().Pz()`          |
| `gx_st3`      | `std::vector<double>` | X-coordinate at station 3              | `SQTrack::get_pos_st3().X()`          |
| `gy_st3`      | `std::vector<double>` | Y-coordinate at station 3              | `SQTrack::get_pos_st3().Y()`          |
| `gz_st3`      | `std::vector<double>` | Z-coordinate at station 3              | `SQTrack::get_pos_st3().Z()`          |
| `gpx_st3`     | `std::vector<double>` | X-component of momentum at station 3  | `SQTrack::get_mom_st3().Px()`          |
| `gpy_st3`     | `std::vector<double>` | Y-component of momentum at station 3  | `SQTrack::get_mom_st3().Py()`          |
| `gpz_st3`     | `std::vector<double>` | Z-component of momentum at station 3  | `SQTrack::get_mom_st3().Pz()`          |

## Dimuon Variables
The following table lists the reconstructed dimuon variables used in the analysis, with the updated naming convention prefixed by `rec_dimuon_`. These variables are stored in `std::vector` containers and are accessible via the specified user functions from the `SRecDimuon` class.

```cpp
| Variable Name                | Type                  | Description                                                                      | User Functions                      |
|------------------------------|-----------------------|----------------------------------------------------------------------------------|-------------------------------------|
| rec_dimuon_id                | std::vector<int>      | List of dimuon IDs.                                                              | SRecDimuon::get_dimuon_id()         |
| rec_dimuon_true_id           | std::vector<int>      | List of reconstructed dimuon IDs only when the true dimuon exists.               | SRecDimuon::get_rec_dimuon_id()     |
| rec_dimuon_track_id_pos      | std::vector<int>      | Track ID of the positive muon track (returns the index of the SRecTrack).        | SRecDimuon::get_track_id_pos()      |
| rec_dimuon_track_id_neg      | std::vector<int>      | Track ID of the negative muon track (returns the index of the SRecTrack).        | SRecDimuon::get_track_id_neg()      |
| rec_dimuon_px_pos            | std::vector<double>   | x-component of the momentum of the vertexed (default) positive muon of the dimuon| SRecDimuon::get_mom_pos().Px()      |
| rec_dimuon_py_pos            | std::vector<double>   | y-component of the momentum of the vertexed (default) positive muon of the dimuon| SRecDimuon::get_mom_pos().Py()      |
| rec_dimuon_pz_pos            | std::vector<double>   | z-component of the momentum of the vertexed (default) positive muon of the dimuon| SRecDimuon::get_mom_pos().Pz()      |
| rec_dimuon_px_neg            | std::vector<double>   | x-component of the momentum of the vertexed (default) negative muon of the dimuon| SRecDimuon::get_mom_neg().Px()      |
| rec_dimuon_py_neg            | std::vector<double>   | y-component of the momentum of the vertexed (default) negative muon of the dimuon| SRecDimuon::get_mom_neg().Py()      |
| rec_dimuon_pz_neg            | std::vector<double>   | z-component of the momentum of the vertexed (default) negative muon of the dimuon| SRecDimuon::get_mom_neg().Pz()      |
| rec_dimuon_x                 | std::vector<double>   | x-component of the position of the vertexed (default) dimuon                     | SRecDimuon::get_pos().X()           |
| rec_dimuon_y                 | std::vector<double>   | y-component of the position of the vertexed (default) dimuon                     | SRecDimuon::get_pos().Y()           |
| rec_dimuon_z                 | std::vector<double>   | z-component of the position of the vertexed (default) dimuon                     | SRecDimuon::get_pos().Z()           |
| rec_dimuon_px_pos_tgt        | std::vector<double>   | x-component of the momentum of the vertexed (target) positive muon of the dimuon | SRecDimuon::p_pos_target().Px()     |
| rec_dimuon_py_pos_tgt        | std::vector<double>   | y-component of the momentum of the vertexed (target) positive muon of the dimuon | SRecDimuon::p_pos_target().Py()     |
| rec_dimuon_pz_pos_tgt        | std::vector<double>   | z-component of the momentum of the vertexed (target) positive muon of the dimuon | SRecDimuon::p_pos_target().Pz()     |
| rec_dimuon_px_neg_tgt        | std::vector<double>   | x-component of the momentum of the vertexed (target) negative muon of the dimuon | SRecDimuon::p_neg_target().Px()     |
| rec_dimuon_py_neg_tgt        | std::vector<double>   | y-component of the momentum of the vertexed (target) negative muon of the dimuon | SRecDimuon::p_neg_target().Py()     |
| rec_dimuon_pz_neg_tgt        | std::vector<double>   | z-component of the momentum of the vertexed (target) negative muon of the dimuon | SRecDimuon::p_neg_target().Pz()     |
| rec_dimuon_px_pos_dump       | std::vector<double>   | x-component of the momentum of the vertexed (dump) positive muon of the dimuon   | SRecDimuon::p_pos_dump().Px()       |
| rec_dimuon_py_pos_dump       | std::vector<double>   | y-component of the momentum of the vertexed (dump) positive muon of the dimuon   | SRecDimuon::p_pos_dump().Py()       |
| rec_dimuon_pz_pos_dump       | std::vector<double>   | z-component of the momentum of the vertexed (dump) positive muon of the dimuon   | SRecDimuon::p_pos_dump().Pz()       |
| rec_dimuon_px_neg_dump       | std::vector<double>   | x-component of the momentum of the vertexed (dump) negative muon of the dimuon   | SRecDimuon::p_neg_dump().Px()       |
| rec_dimuon_py_neg_dump       | std::vector<double>   | y-component of the momentum of the vertexed (dump) negative muon of the dimuon   | SRecDimuon::p_neg_dump().Py()       |
| rec_dimuon_pz_neg_dump       | std::vector<double>   | z-component of the momentum of the vertexed (dump) negative muon of the dimuon   | SRecDimuon::p_neg_dump().Pz()       |

## Reconstructed Track Variables
These variables store information about reconstructed muon tracks, will be obtained from the `SRecTrack` class, at the vertex, stations 1 and 3, target, and dump regions.

```cpp
| Variable Name              | Type                  | Description                                                                 | User Functions                         |
|----------------------------|-----------------------|-----------------------------------------------------------------------------|----------------------------------------|
| rec_track_id               | std::vector<int>      | Track ID of the recons. muon (set as the index of the vector rec_track_id). |                                        |
| rec_track_charge           | std::vector<int>      | Charge of the reconstructed muons.                                          | SRecTrack::get_charge()                |
| rec_track_vx               | std::vector<double>   | x-coordinate of the reconstructed vertex.                                   | SRecTrack::get_pos_vtx().X()           |
| rec_track_vy               | std::vector<double>   | y-coordinate of the reconstructed vertex.                                   | SRecTrack::get_pos_vtx().Y()           |
| rec_track_vz               | std::vector<double>   | z-coordinate of the reconstructed vertex.                                   | SRecTrack::get_pos_vtx().Z()           |
| rec_track_px               | std::vector<double>   | x-component of the reconstructed momentum at the vertex.                    | SRecTrack::get_mom_vtx().Px()          |
| rec_track_py               | std::vector<double>   | y-component of the reconstructed momentum at the vertex.                    | SRecTrack::get_mom_vtx().Py()          |
| rec_track_pz               | std::vector<double>   | z-component of the reconstructed momentum at the vertex.                    | SRecTrack::get_mom_vtx().Pz()          |
| rec_track_x_st1            | std::vector<double>   | x-coordinate of the reconstructed track at station 1.                       | SRecTrack::get_pos_st1().X()           |
| rec_track_y_st1            | std::vector<double>   | y-coordinate of the reconstructed track at station 1.                       | SRecTrack::get_pos_st1().Y()           |
| rec_track_z_st1            | std::vector<double>   | z-coordinate of the reconstructed track at station 1.                       | SRecTrack::get_pos_st1().Z()           |
| rec_track_px_st1           | std::vector<double>   | x-component of the reconstructed momentum at station 1.                     | SRecTrack::get_mom_st1().Px()          |
| rec_track_py_st1           | std::vector<double>   | y-component of the reconstructed momentum at station 1.                     | SRecTrack::get_mom_st1().Py()          |
| rec_track_pz_st1           | std::vector<double>   | z-component of the reconstructed momentum at station 1.                     | SRecTrack::get_mom_st1().Pz()          |
| rec_track_x_st3            | std::vector<double>   | x-coordinate of the reconstructed track at station 3.                       | SRecTrack::get_pos_st3().X()           |
| rec_track_y_st3            | std::vector<double>   | y-coordinate of the reconstructed track at station 3.                       | SRecTrack::get_pos_st3().Y()           |
| rec_track_z_st3            | std::vector<double>   | z-coordinate of the reconstructed track at station 3.                       | SRecTrack::get_pos_st3().Z()           |
| rec_track_px_st3           | std::vector<double>   | x-component of the reconstructed momentum at station 3.                     | SRecTrack::get_mom_st3().Px()          |
| rec_track_py_st3           | std::vector<double>   | y-component of the reconstructed momentum at station 3.                     | SRecTrack::get_mom_st3().Py()          |
| rec_track_pz_st3           | std::vector<double>   | z-component of the reconstructed momentum at station 3.                     | SRecTrack::get_mom_st3().Pz()          |
| rec_track_num_hits         | std::vector<int>      | Total hits associated with the reconstructed track.                         | SRecTrack::get_num_hits()              |
| rec_track_chisq            | std::vector<double>   | Global track fit chi-squared value.                                         | SRecTrack::get_chisq()                 |
| rec_track_chisq_tgt        | std::vector<double>   | Chi-squared value of the track fit at the target.                           | SRecTrack::get_chisq_target()          |
| rec_track_chisq_dump       | std::vector<double>   | Chi-squared value of the track fit at the dump.                             | SRecTrack::get_chisq_dump()            |
| rec_track_chisq_upstream   | std::vector<double>   | Chi-squared value of the track fit in the upstream region.                  | SRecTrack::get_chisq_upstream()        |
| rec_track_x_tgt            | std::vector<double>   | x-coordinate of the reconstructed track at the target.                      | SRecTrack::get_pos_target().X()        |
| rec_track_y_tgt            | std::vector<double>   | y-coordinate of the reconstructed track at the target.                      | SRecTrack::get_pos_target().Y()        |
| rec_track_z_tgt            | std::vector<double>   | z-coordinate of the reconstructed track at the target.                      | SRecTrack::get_pos_target().Z()        |
| rec_track_x_dump           | std::vector<double>   | x-coordinate of the reconstructed track at the dump.                        | SRecTrack::get_pos_dump().X()          |
| rec_track_y_dump           | std::vector<double>   | y-coordinate of the reconstructed track at the dump.                        | SRecTrack::get_pos_dump().Y()          |
| rec_track_z_dump           | std::vector<double>   | z-coordinate of the reconstructed track at the dump.                        | SRecTrack::get_pos_dump().Z()          |
| rec_track_px_tgt           | std::vector<double>   | x-component of the reconstructed momentum at the target.                    | SRecTrack::get_mom_target().Px()       |
| rec_track_py_tgt           | std::vector<double>   | y-component of the reconstructed momentum at the target.                    | SRecTrack::get_mom_target().Py()       |
| rec_track_pz_tgt           | std::vector<double>   | z-component of the reconstructed momentum at the target.                    | SRecTrack::get_mom_target().Pz()       |
| rec_track_px_dump          | std::vector<double>   | x-component of the reconstructed momentum at the dump.                      | SRecTrack::get_mom_dump().Px()         |
| rec_track_py_dump          | std::vector<double>   | y-component of the reconstructed momentum at the dump.                      | SRecTrack::get_mom_dump().Py()         |
| rec_track_pz_dump          | std::vector<double>   | z-component of the reconstructed momentum at the dump.                      | SRecTrack::get_mom_dump().Pz()         |
