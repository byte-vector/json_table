# Json Table Widget [![GitHub stars](https://img.shields.io/github/stars/apgapg/json_table.svg?style=social)](https://github.com/apgapg/json_table) [![Twitter Follow](https://img.shields.io/twitter/url/https/@ayushpgupta.svg?style=social)](https://twitter.com/ayushpgupta) ![GitHub last commit](https://img.shields.io/github/last-commit/apgapg/json_table.svg) [![Website shields.io](https://img.shields.io/website-up-down-green-red/http/shields.io.svg)](https://play.google.com/store/apps/details?id=com.coddu.flutterprofile)[![Open Source Love](https://badges.frapsoft.com/os/v2/open-source.svg?v=103)](https://github.com/apgapg/json_table)


This Flutter package provides a Json Table Widget for directly showing table from a json(Map).

<img src="https://raw.githubusercontent.com/apgapg/json_table/master/src/s1.gif"  height = "400" alt="JsonTable">

# 💻 Installation
In the `dependencies:` section of your `pubspec.yaml`, add the following line:

[![Version](https://img.shields.io/pub/v/json_table.svg)](https://pub.dartlang.org/packages/json_table)

```yaml
dependencies:
  json_table: <latest version>
```

# ❔ Usage

### Import this class

```dart
import 'package:json_table/json_table.dart';
```

### Add Json Table Widget
- Accepts Map<dynamic> as input. Just decode your json array string and pass it in JsonTable. No casting to model required.
- Option for creating column header builder. This basically returns a widget to show as table column header
```dart
tableHeaderBuilder: (String header) {
    return Container(
      padding: EdgeInsets.symmetric(horizontal: 8.0, vertical: 4.0),
      decoration: BoxDecoration(border: Border.all(width: 0.5),color: Colors.grey[300]),
      child: Text(
        header,
        textAlign: TextAlign.center,
        style: Theme.of(context).textTheme.display1.copyWith(fontWeight: FontWeight.w700, fontSize: 14.0,color: Colors.black87),
      ),
    );
  }
```
- Option for creating table cell builder
```dart
tableCellBuilder: (value) {
    return Container(
      padding: EdgeInsets.symmetric(horizontal: 4.0, vertical: 2.0),
      decoration: BoxDecoration(border: Border.all(width: 0.5, color: Colors.grey.withOpacity(0.5))),
      child: Text(
        value,
        textAlign: TextAlign.center,
        style: Theme.of(context).textTheme.display1.copyWith(fontSize: 14.0, color: Colors.grey[900]),
      ),
    );
  }
```

### Simple Implementation
```dart
//Decode your json string
final String jsonSample='[{"id":1},{"id":2}]';
var json = jsonDecode(jsonSample);

//Simply pass this json to JsonTable
child: JsonTable(json)
```

### Full Implementation
```dart
JsonTable(
   json,
   tableHeaderBuilder: (String header) {
     return Container(
       padding: EdgeInsets.symmetric(horizontal: 8.0, vertical: 4.0),
       decoration: BoxDecoration(border: Border.all(width: 0.5),color: Colors.grey[300]),
       child: Text(
         header,
         textAlign: TextAlign.center,
         style: Theme.of(context).textTheme.display1.copyWith(fontWeight: FontWeight.w700, fontSize: 14.0,color: Colors.black87),
       ),
     );
   },
   tableCellBuilder: (value) {
     return Container(
       padding: EdgeInsets.symmetric(horizontal: 4.0, vertical: 2.0),
       decoration: BoxDecoration(border: Border.all(width: 0.5, color: Colors.grey.withOpacity(0.5))),
       child: Text(
         value,
         textAlign: TextAlign.center,
         style: Theme.of(context).textTheme.display1.copyWith(fontSize: 14.0, color: Colors.grey[900]),
       ),
     );
   },
 )
```

### Key Highlights
- The table constructed isn't the flutter's native data table.
- The table is manually coded hence serves a great learning purpose on how to create simple tables manually in flutter

### Limitations
- The Json array item's must contain the same keys set in every json object.
- Currently the column header keys are extracted from first json item of json array. Hence no required keys that are to be shown must be missing in first json object

## TODO
- [ ] Custom header list parameter. This will help to show only those keys as mentioned in header list
- [ ] Add support for keys missing in json object
- [ ] Add support for auto formatting of date
- [ ] Extracting column headers logic must be change. Not to depend on first object
- [ ] Pagination support etc. Its good if this table can be replaced with Flutter's native DataTable

# ⭐ My Flutter Packages
- [pie_chart](https://pub.dartlang.org/packages/pie_chart)  [![GitHub stars](https://img.shields.io/github/stars/apgapg/pie_chart.svg?style=social)](https://github.com/apgapg/pie_chart)  Flutter Pie Chart with cool animation.
- [avatar_glow](https://pub.dartlang.org/packages/avatar_glow)  [![GitHub stars](https://img.shields.io/github/stars/apgapg/avatar_glow.svg?style=social)](https://github.com/apgapg/avatar_glow)  Flutter Avatar Glow Widget with glowing animation.
- [search_widget](https://pub.dartlang.org/packages/search_widget)  [![GitHub stars](https://img.shields.io/github/stars/apgapg/search_widget.svg?style=social)](https://github.com/apgapg/search_widget)  Flutter Search Widget for selecting an option from list.
- [animating_location_pin](https://pub.dev/packages/animating_location_pin)  [![GitHub stars](https://img.shields.io/github/stars/apgapg/search_widget.svg?style=social)](https://github.com/apgapg/animating_location_pin)  Flutter Animating Location Pin Widget providing Animating Location Pin Widget which can be used while fetching device location.
                                                                                                                                                                                                                             
# ⭐ My Flutter Apps
- [flutter_profile](https://github.com/apgapg/flutter_profile)  [![GitHub stars](https://img.shields.io/github/stars/apgapg/flutter_profile.svg?style=social)](https://github.com/apgapg/flutter_profile)  Showcase My Portfolio: Ayush P Gupta on Playstore.
- [flutter_sankalan](https://github.com/apgapg/flutter_sankalan)  [![GitHub stars](https://img.shields.io/github/stars/apgapg/flutter_sankalan.svg?style=social)](https://github.com/apgapg/flutter_sankalan)  Flutter App which allows reading/uploading short stories.

# 👍 Contribution
1. Fork it
2. Create your feature branch (git checkout -b my-new-feature)
3. Commit your changes (git commit -m 'Add some feature')
4. Push to the branch (git push origin my-new-feature)
5. Create new Pull Request
