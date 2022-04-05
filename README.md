
# Rapport

**Skriv din rapport här!**

_Du kan ta bort all text som finns sedan tidigare_.

## Följande grundsyn gäller dugga-svar:

- Ett kortfattat svar är att föredra. Svar som är längre än en sida text (skärmdumpar och programkod exkluderat) är onödigt långt.
- Svaret skall ha minst en snutt programkod.
- Svaret skall inkludera en kort övergripande förklarande text som redogör för vad respektive snutt programkod gör eller som svarar på annan teorifråga.
- Svaret skall ha minst en skärmdump. Skärmdumpar skall illustrera exekvering av relevant programkod. Eventuell text i skärmdumpar måste vara läsbar.
- I de fall detta efterfrågas, dela upp delar av ditt svar i för- och nackdelar. Dina för- respektive nackdelar skall vara i form av punktlistor med kortare stycken (3-4 meningar).

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
Bilder läggs i samma mapp som markdown-filen.

![](android.png)

Läs gärna:

- Boulos, M.N.K., Warren, J., Gong, J. & Yue, P. (2010) Web GIS in practice VIII: HTML5 and the canvas element for interactive online mapping. International journal of health geographics 9, 14. Shin, Y. &
- Wunsche, B.C. (2013) A smartphone-based golf simulation exercise game for supporting arthritis patients. 2013 28th International Conference of Image and Vision Computing New Zealand (IVCNZ), IEEE, pp. 459–464.
- Wohlin, C., Runeson, P., Höst, M., Ohlsson, M.C., Regnell, B., Wesslén, A. (2012) Experimentation in Software Engineering, Berlin, Heidelberg: Springer Berlin Heidelberg.
