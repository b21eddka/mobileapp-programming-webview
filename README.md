

Ändrade namnet på min app till mitt namn "Eddin". Aktiverade tillgång till internet. Ersatte TextView elementet med WebView i content_main.xml samt gav den ett id: my_webview.
Skapade en privat medlemsvariabel "myWebView" av typen "WebView" och instansierade den i "onCreate" metoden. Med hjälp av id, hittas/ nås "WebView".
Aktivera användningen av Javascript i WebViewClient. Gjorde en assets fil "Index.html" samt skapade två headers för "InternalWebPage".
Implementerar metoderna "showInternalWebPage" och "showExternalWebPage". Kallar metoderna "showExternalWebPage" och "showInternalWebPage" i respektive if-sats.


```
<string name="app_name">Eddin</string>

```
...
 <uses-permission android:name="android.permission.INTERNET" />
...
...
<WebView
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Hello World!"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintLeft_toLeftOf="parent"
        app:layout_constraintRight_toRightOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        android:id="@+id/my_webview"/>
...
...
 private WebView myWebView;

    public void showExternalWebPage(){
        // TODO: Add your code for showing external web page here
        myWebView.loadUrl("https://google.com");
    }

    public void showInternalWebPage(){
        // TODO: Add your code for showing internal web page here
        myWebView.loadUrl("file:///android_asset/index.html");
    }

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        Toolbar toolbar = findViewById(R.id.toolbar);
        setSupportActionBar(toolbar);

        myWebView = findViewById(R.id.my_webview);
        WebViewClient client = new WebViewClient();
        myWebView.setWebViewClient(client);
        myWebView.getSettings().setJavaScriptEnabled(true);
...
...
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8"/>
    <title>Test</title>
</head>
<body>
<h1>
    Eddin är en riktig cooling
</h1>
<h1>
    Jag sa vad jag sa
</h1>
</body>
</html>
...


![](internal.png)
![](external.png)
