# MA4

activity_main.xml

<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">
    <ListView
        android:id="@+id/simpleListView"
        android:layout_width="fill_parent"
        android:layout_height="wrap_content"
        android:divider="@color/material_blue_grey_800"
        android:dividerHeight="1dp" />
</LinearLayout>


actvity_listview.xml


<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:background="#63A2D5"
    android:orientation="vertical">
    <TextView
        android:id="@+id/textView"

    android:layout_width="fill_parent"
    android:layout_height="50dp"
    android:layout_gravity="center"
    android:textSize="20dp"
    android:textColor="#000" />
</LinearLayout>


MAIn Activity.java


package com.example.karnataka;
import androidx.appcompat.app.AppCompatActivity;
import android.os.Bundle;
import android.view.View;
import android.widget.AdapterView;
import android.widget.ArrayAdapter;
import android.widget.ListView;
import android.widget.Toast;
public class MainActivity extends AppCompatActivity {
    ListView simpleList;
    String touristplaces[] = {"Bangalore", "Coorg", "Mysore", "Gokarna",
            "Madikeri", "Hampi", "Shimoga"};
    @Override protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        simpleList = (ListView)findViewById(R.id.simpleListView);
        ArrayAdapter<String> arrayAdapter = new ArrayAdapter<String>(this,
                R.layout.activity_listview, R.id.textView, touristplaces);
        simpleList.setAdapter(arrayAdapter);
        simpleList.setOnItemClickListener(new
                                                  AdapterView.OnItemClickListener() {
                                                      @Override
                                                      public void onItemClick(AdapterView<?> parent, View view, int
                                                              position, long id) {
                                                          String s=(String)parent.getItemAtPosition(position);
                                                          Toast.makeText(getBaseContext(),"You Have Selected " +
                                                                  s,Toast.LENGTH_LONG).show();
                                                      }
                                                  });
    }
}



activity_listview.java

package com.example.karnataka;
import androidx.appcompat.app.AppCompatActivity;
import android.os.Bundle;
class listview extends AppCompatActivity {
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_listview);
    }
}


