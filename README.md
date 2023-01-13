<h1>Convert Website Into Android App<h1>
<img src="android.png" alt="android">

<h4>In AndroidManifest add Like this</h4>

-------------------------------------------------------------------------------------------------
`<manifest xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools">
    <uses-permission  android:name="android.permission.INTERNET"></uses-permission>`
--------------------------------------------------------------------------------------------------

<h4>In MainActivity.java add</h4>

`import android.webkit.WebSettings;` <br>
`import android.webkit.WebView;`  
`import android.webkit.WebViewClient;`

<h4>In class add like this</h4>
<h2>public class MainActivity extends AppCompatActivity {</h2>
 private WebView mywebView;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        mywebView=(WebView) findViewById(R.id.webview);
        mywebView.setWebViewClient(new WebViewClient());
        mywebView.loadUrl("your web site");
        WebSettings webSettings=mywebView.getSettings();
        webSettings.setJavaScriptEnabled(true);
    }
<h4>In activity_main make like this</h4>

<?xml version="1.0" encoding="utf-8"?>
`<RelativeLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">`


    <WebView
        android:id="@+id/webview"
        android:layout_width="match_parent"
        android:layout_height="match_parent" />
`</RelativeLayout>`

<h3>In activity_main on Designe</h3>
<h4>add loyout webview</h4>

<h3>In res values in style or themes xml make this line like this</h3>
    <h4><style name="Theme.(your name of app)" parent="Theme.MaterialComponents.DayNight.DarkActionBar"></h4>

