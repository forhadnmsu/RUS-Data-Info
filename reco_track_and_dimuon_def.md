## Reconstructed Dimuon Variables
These variables store information about reconstructed dimuons (`mu+ mu-` pairs), derived from the `SQDimuon` class, at the default vertex, target (`tgt`), and dump (`dump`) regions.

| Variable Name       | Type                | Description                                                                        | User Functions                      |
|---------------------|---------------------|------------------------------------------------------------------------------------|-------------------------------------|                     
| `dimuon_id`         | `std::vector<int>`    | List of dimuon IDs                           dimuon.                             | `SRecDimuon::get_dimuon_id()`       |
| `rec_dimuon_id`     | `std::vector<int>`    | List of reconstructed dimuon IDs only when the true dimuon exists.               | `SRecDimuon::get_rec_dimuon_id()`   |
| `track_id_pos`      | `std::vector<int>`    | Track ID of the positive muon track (returns the index of rhe `SRecTrack`).      | `SRecDimuon::get_track_id_pos()`    |
| `track_id_neg`      | `std::vector<int>`    | Track ID of the negative muon track (returns the index of rhe `SRecTrack`).      | `SRecDimuon::get_track_id_neg()`    |
| `rec_px_pos`        | `std::vector<double>` | x-component of the momentum of the vertexed (default) positive muon of the dimuon| `SRecDimuon::get_mom().Px()`        |
| `rec_py_pos`        | `std::vector<double>` | y-component of the momentum of the vertexed (default) positive muon of the dimuon| `SRecDimuon::get_mom().Py()`        |
| `rec_pz_pos`        | `std::vector<double>` | z-component of the momentum of the vertexed (default) positive muon of the dimuon| `SRecDimuon::get_mom().Pz()`        |
| `rec_px_neg`        | `std::vector<double>` | x-component of the momentum of the vertexed (default) negative muon of the dimuon| `SRecDimuon::get_mom().Px()`        |
| `rec_py_neg`        | `std::vector<double>` | y-component of the momentum of the vertexed (default) negative muon of the dimuon| `SRecDimuon::get_mom().Py()`        |
| `rec_pz_neg`        | `std::vector<double>` | z-component of the momentum of the vertexed (default) negative muon of the dimuon| `SRecDimuon::get_mom().Pz()`        |

| `rec_x_pos`        | `std::vector<double>` | x-component of the position of the vertexed (default) positive muon of the dimuon| `SRecDimuon::get_pos().X()`          |
| `rec_y_pos`        | `std::vector<double>` | y-component of the position of the vertexed (default) positive muon of the dimuon| `SRecDimuon::get_pos().Y()`          |
| `rec_z_pos`        | `std::vector<double>` | z-component of the position of the vertexed (default) positive muon of the dimuon| `SRecDimuon::get_pos().Z()`          |
| `rec_x_neg`        | `std::vector<double>` | x-component of the position of the vertexed (default) negative muon of the dimuon| `SRecDimuon::get_pos().X()`          |
| `rec_y_neg`        | `std::vector<double>` | y-component of the position of the vertexed (default) negative muon of the dimuon| `SRecDimuon::get_pos().Y()`          |
| `rec_z_neg`        | `std::vector<double>` | z-component of the position of the vertexed (default) negative muon of the dimuon| `SRecDimuon::get_pos().Z()`          |

| `rec_px_pos_tgt`    | `std::vector<double>` | x-component of the momentum of the vertexed (target) positive muon of the dimuon | `SRecDimuon::p_pos_target().Px()`   |
| `rec_py_pos_tgt`    | `std::vector<double>` | y-component of the momentum of the vertexed (target) positive muon of the dimuon | `SRecDimuon::p_pos_target().Py()`   |
| `rec_pz_pos_tgt`    | `std::vector<double>` | z-component of the momentum of the vertexed (target) positive muon of the dimuon | `SRecDimuon::p_pos_target().Pz()`   |
| `rec_px_neg_tgt`    | `std::vector<double>` | x-component of the momentum of the vertexed (target) negative muon of the dimuon | `SRecDimuon::p_neg_target.Px()`     |
| `rec_py_neg_tgt`    | `std::vector<double>` | y-component of the momentum of the vertexed (target) negative muon of the dimuon | `SRecDimuon::p_neg_target.Py()`     |
| `rec_pz_neg_tgt`    | `std::vector<double>` | z-component of the momentum of the vertexed (target) negative muon of the dimuon | `SRecDimuon::p_neg_target.Pz()`     |
| `rec_px_pos_dump`   | `std::vector<double>` | x-component of the momentum of the vertexed (dump) positive muon of the dimuon   | `SRecDimuon::p_pos_dump.Px ()`      |
| `rec_py_pos_dump`   | `std::vector<double>` | y-component of the momentum of the vertexed (dump) positive muon of the dimuon   | `SRecDimuon::p_pos_dump.Py ()`      |
| `rec_pz_pos_dump`   | `std::vector<double>` | z-component of the momentum of the vertexed (dump) positive muon of the dimuon   | `SRecDimuon::p_pos_dump.Pz ()`      |
| `rec_px_neg_dump`   | `std::vector<double>` | x-component of the momentum of the vertexed (dump) negative muon of the dimuon   | `SRecDimuon::p_neg_dump.Px ()`      |
| `rec_py_neg_dump`   | `std::vector<double>` | y-component of the momentum of the vertexed (dump) negative muon of the dimuon   | `SRecDimuon::p_neg_dump.Py ()`      |
| `rec_pz_neg_dump`   | `std::vector<double>` | z-component of the momentum of the vertexed (dump) negative muon of the dimuon   | `SRecDimuon::p_neg_dump.Pz ()`      |

## Reconstructed Track Variables
These variables store information about reconstructed muon tracks, derived from the `SQTrack` class, at the vertex, stations 1 and 3, target, and dump regions.

| Variable Name       | Type                  | Description                                                                 | User Functions                         |
|---------------------|-----------------------|-----------------------------------------------------------------------------|----------------------------------------|
| `rec_track_id`      | `std::vector<int>`    | Track ID of the recons. muon (set as the index of the vector`rec_track_id).`|                                        |
| `rec_charge`        | `std::vector<int>`    | Charge of the reconstructed muons.                                          | `SRecTrack::get_charge()`              |
| `rec_vx`            | `std::vector<double>` | x-coordinate of the reconstructed vertex.                                   | `SRecTrack::get_pos_vtx().X()`         |
| `rec_vy`            | `std::vector<double>` | y-coordinate of the reconstructed vertex.                                   | `SRecTrack::get_pos_vtx().Y()`         |
| `rec_vz`            | `std::vector<double>` | z-coordinate of the reconstructed vertex.                                   | `SRecTrack::get_pos_vtx().Z()`         |
| `rec_px`            | `std::vector<double>` | x-component of the reconstructed momentum at the vertex.                    | `SRecTrack::get_mom_vtx().Px()`        |
| `rec_py`            | `std::vector<double>` | y-component of the reconstructed momentum at the vertex.                    | `SRecTrack::get_mom_vtx().Py()`        |
| `rec_pz`            | `std::vector<double>` | z-component of the reconstructed momentum at the vertex.                    | `SRecTrack::get_mom_vtx().Pz()`        |
| `rec_x_st1`         | `std::vector<double>` | x-coordinate of the reconstructed track at station 1.                       | `SRecTrack::get_pos_st1().X()`         |
| `rec_y_st1`         | `std::vector<double>` | y-coordinate of the reconstructed track at station 1.                       | `SRecTrack::get_pos_st1().Y()`         |
| `rec_z_st1`         | `std::vector<double>` | z-coordinate of the reconstructed track at station 1.                       | `SRecTrack::get_pos_st1().Z()`         |
| `rec_px_st1`        | `std::vector<double>` | x-component of the reconstructed momentum at station 1.                     | `SRecTrack::get_mom_st1().Px()`        |
| `rec_py_st1`        | `std::vector<double>` | y-component of the reconstructed momentum at station 1.                     | `SRecTrack::get_mom_st1().Py()`        |
| `rec_pz_st1`        | `std::vector<double>` | z-component of the reconstructed momentum at station 1.                     | `SRecTrack::get_mom_st1().Pz()`        |
| `rec_x_st3`         | `std::vector<double>` | x-coordinate of the reconstructed track at station 3.                       | `SRecTrack::get_pos_st3().X()`         |
| `rec_y_st3`         | `std::vector<double>` | y-coordinate of the reconstructed track at station 3.                       | `SRecTrack::get_pos_st3().Y()`         |
| `rec_z_st3`         | `std::vector<double>` | z-coordinate of the reconstructed track at station 3.                       | `SRecTrack::get_pos_st3().Z()`         |
| `rec_px_st3`        | `std::vector<double>` | x-component of the reconstructed momentum at station 3.                     | `SRecTrack::get_mom_st3().Px()`        |
| `rec_py_st3`        | `std::vector<double>` | y-component of the reconstructed momentum at station 3.                     | `SRecTrack::get_mom_st3().Py()`        |
| `rec_pz_st3`        | `std::vector<double>` | z-component of the reconstructed momentum at station 3.                     | `SRecTrack::get_mom_st3().Pz()`        |
| `rec_num_hits`      | `std::vector<int>`    | Total hits associated with the reconstructed track.                         | `SRecTrack::get_num_hits()`            |
| `rec_chisq`         | `std::vector<double>` | Global track fit chi-squared value.                                         | `SRecTrack::get_chisq()`               |
| `rec_chisq_target`  | `std::vector<double>` | Chi-squared value of the track fit at the target.                           | `SRecTrack::get_chisq_target()`        |
| `rec_chisq_dump`    | `std::vector<double>` | Chi-squared value of the track fit at the dump.                             | `SRecTrack::get_chisq_dump()`          |
| `rec_chisq_upstream`| `std::vector<double>` | Chi-squared value of the track fit in the upstream region.                  | `SRecTrack::get_chisq_upstream()`      |
| `rec_x_tgt`         | `std::vector<double>` | x-coordinate of the reconstructed track at the target.                      | `SRecTrack::get_pos_target().X()`      |
| `rec_y_tgt`         | `std::vector<double>` | y-coordinate of the reconstructed track at the target.                      | `SRecTrack::get_pos_target().Y()`      |
| `rec_z_tgt`         | `std::vector<double>` | z-coordinate of the reconstructed track at the target.                      | `SRecTrack::get_pos_target().Z()`      |
| `rec_x_dump`        | `std::vector<double>` | x-coordinate of the reconstructed track at the dump.                        | `SRecTrack::get_pos_dump().X()`        |
| `rec_y_dump`        | `std::vector<double>` | y-coordinate of the reconstructed track at the dump.                        | `SRecTrack::get_pos_dump().Y()`        |
| `rec_z_dump`        | `std::vector<double>` | z-coordinate of the reconstructed track at the dump.                        | `SRecTrack::get_pos_dump().Z()`        |
| `rec_px_tgt`        | `std::vector<double>` | x-component of the reconstructed momentum at the target.                    | `SRecTrack::get_mom_target().Px()`     |
| `rec_py_tgt`        | `std::vector<double>` | y-component of the reconstructed momentum at the target.                    | `SRecTrack::get_mom_target().Py()`     |
| `rec_pz_tgt`        | `std::vector<double>` | z-component of the reconstructed momentum at the target.                    | `SRecTrack::get_mom_target().Pz()`     |
| `rec_px_dump`       | `std::vector<double>` | x-component of the reconstructed momentum at the dump.                      | `SRecTrack::get_mom_dump().Px()`       |
| `rec_py_dump`       | `std::vector<double>` | y-component of the reconstructed momentum at the dump.                      | `SRecTrack::get_mom_dump().Py()`       |
| `rec_pz_dump`       | `std::vector<double>` | z-component of the reconstructed momentum at the dump.                      | `SRecTrack::get_mom_dump().Pz()`       |
