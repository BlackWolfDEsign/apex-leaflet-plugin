# apex-leaflet-plugin 1.0.0
a leaflet-plugin for oracle apex with some plugins
## supports
```
marker, circle and polygons
positioning (Where am I?)
layer group
mouse location
map_id and access_token
```

## plugin config
| Name        | Type            | Required | Default Value     |
|-------------|-----------------|----------|-------------------|
| Height      | Text            | Yes      | 700px             |
| Center      | Text            | Yes      | lat, lng          |
| Zoom        | Text            | Yes      | 14                |
| Max Zoom    | Text            | Yes      | 18                |
| Source      | SQL Code        | Yes      | _Described below_ |
| Tile Server | Text            | Yes      | _Described below_ |
| Attribution | Text            | Yes      | _Described below_ |
| Layer Group | Yes/No          | Yes      | Yes	       |
| Positioning | Yes/No          | Yes      | Yes	       |
| Map ID      | Text            | Yes      | _Described below_ |
| Access Token| Text            | Yes      | _Described below_ |
| Mouse Loc   | Yes/No          | Yes      | Yes	       |

The `Source` attribute should contain a SQL statement like :
```
-- marker_options: [VALUE] - color: 'red', fillColor: '#f03', fillOpacity: 0.5, radius: 500
-- marker_id: unique marker id
-- ovl_layers: for layer groups
-- marker_type: [VALUE] - marker, circle or polygon
-- lat and lng for marker and circle
-- loc for polygons: [VALUE] - [lat, lng], [lat, lng], [lat, lng]

select
	marker_options as src_marker_options,
	marker_id as src_marker_id,
	ovl_layers as src_ovl_layers,
	marker_type as src_marker_type,
	lat as src_lat,
	lng as src_lng,
	loc as src_loc,
	label as src_label
from
	src_table
```

The `Tile Server` attribute should contain a string like :
```
https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png
```

The `Attribution` attribute should contain a string like :
```
'&copy; <a href="https://www.openstreetmap.org/copyright">OpenStreetMap</a> contributors'
```

The `Map ID` and `Access Token` attributes should contain a string for other tileserver

## used in plugin and thanks to the developers of:
```
leaflet 1.5.1
fontawesome 5.9.0
leaflet-locatcontrol 0.67.0
```
