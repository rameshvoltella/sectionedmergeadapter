## SectionedMergeAdapter

This is a library based on `MergeAdapter` by CommonsWare. It allows you to work with sections and subheaders in your `ListView`s. With this library, you get the advantage of stitching together the rows and the header of the subsection in the subsection itself. For example, if there are no rows in a subsection of the `ListView`, the header of the subsection is also not shown.

### Screenshot

<div style="text-align:center"><img src="app/Screenshot_20160724-231927.png" style="width:450px"/></div>

### Example code

```java
ListView listView = (ListView) findViewById(android.R.id.list);

ArrayAdapter<String> adapter1 =
        new ArrayAdapter<>(this, R.layout.item_list, android.R.id.text1, arrayList1);
ArrayAdapter<String> adapter2 =
        new ArrayAdapter<>(this, R.layout.item_list, android.R.id.text1, arrayList2);
ArrayAdapter<String> adapter3 =
        new ArrayAdapter<>(this, R.layout.item_list, android.R.id.text1, arrayList3);

TextView tv1 = (TextView) getLayoutInflater().inflate(R.layout.item_header, null, false)
        .findViewById(R.id.headerText);
tv1.setText("Header 1");
TextView tv2 = (TextView) getLayoutInflater().inflate(R.layout.item_header, null, false)
        .findViewById(R.id.headerText);
tv2.setText("Header 2");
TextView tv3 = (TextView) getLayoutInflater().inflate(R.layout.item_header, null, false)
        .findViewById(R.id.headerText);
tv3.setText("Header 3");

SectionedMergeAdapter adapter = new SectionedMergeAdapter();

adapter.addSection(new SectionedMergeAdapter.Section(tv1, adapter1));
adapter.addSection(new SectionedMergeAdapter.Section(tv2, adapter2));
adapter.addSection(new SectionedMergeAdapter.Section(tv3, adapter3));

listView.setAdapter(adapter);
```

### Note
Since `SectionedMergeAdapter` is extending from the `MergeAdapter`, you can use other `MergeAdapter` functionalities like `addView()`, `addViews()` and `addAdapter()` with this library.

For a detailed list of things supported with `MergeAdapter` check out [CWAC MergeAdapter](https://github.com/commonsguy/cwac-merge).

### Installation
Clone the repository and import the module in your project.
