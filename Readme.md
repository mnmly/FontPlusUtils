# FontPlusUtils

[Annotated source](http://mnmly.github.com/FontPlusUtils)

### Example Usage
    <script type="text/javascript" src="http://webfont.fontplus.jp/accessor/script/fontplus.js?{someapi-ish-keys}" charset="utf-8"></script>
    <script type="text/javascript" src="https://raw.github.com/mnmly/FontPlusUtils/master/fontplus.utils.js" charset="utf-8"></script>
    <script type="text/javascript" src="https://www.google.com/jsapi"></script>
    <script type="text/javascript">
      google.load("webfont", "1");

      google.setOnLoadCallback(function() {
        // Create the instance of FontPlusUtils with WebFont loaded via google api
        fontPlusUtils = new FontPlusUtils(WebFont);

        fontFamilies = [ "HOT-白舟太草書 Std B", "MatissePro-DB", "FOT-Rodin Pro L" ];
        
        uid = 0
        
        // `initialactive` is triggered when typefaces from stylsheets have been loaded.
        fontPlusUtils.bind('initialactive', function(_uid, fontFamily, fontDescription){
          // it will return uniqueid for each request
          uid = fontPlusUtils.getFontForText(fontFamilies, "abcdefghijklmnopqrstuvwxyzなにかしらー");
        });

        fontPlusUtils.bind('fontactive', function(_uid, fontFamily, fontDescription, text){
          // it will return uniqueid for each request
          console.log('fontActive binded', arguments);
        });

        fontPlusUtils.bind('active', function(_uid){
          // now you can use the text you requested on this particular `uid` :)
          console.log(uid, _uid);
        });

        window.fontPlusUtils = fontPlusUtils;
      });
    </script>
