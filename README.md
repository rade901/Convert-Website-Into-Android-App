# Convert Website Into Android App

<h4><uses-permission  android:name="android.permission.INTERNET"></uses-permission></h4>

<h2>In AndroidManifest</h2>
<h3><manifest xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools">
    <uses-permission  android:name="android.permission.INTERNET"></uses-permission>
    </h3>


android:id="@+id/webview"

import android.webkit.WebSettings; 
import android.webkit.WebView; 
import android.webkit.WebViewClient;


private WebView mywebView;


 mywebView=(WebView) findViewById(R.id.webview);
 mywebView.setWebViewClient(new WebViewClient());
 mywebView.loadUrl("Your website address");
 WebSettings webSettings=mywebView.getSettings();
 webSettings.setJavaScriptEnabled(true);
 
 
 public class mywebClient extends WebViewClient{
        @Override
        public void onPageStarted(WebView view, String url, Bitmap favicon){
            super.onPageStarted(view,url,favicon);
        }
        @Override
        public boolean shouldOverrideUrlLoading(WebView view,String url){
            view.loadUrl(url);
            return true;
        }
    }
@Override
    public void onBackPressed(){
        if(mywebView.canGoBack()) {
            mywebView.goBack();
        }
    else{
        super.onBackPressed();
            }
}
