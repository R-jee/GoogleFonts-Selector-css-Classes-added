# GoogleFonts-Selector-css-Classes-added
GoogleFonts Selector css Classes added

```
function changeGFontOnSelectorChange (elementfontSelector ) {
  $("#"+ elementfontSelector).on("change", function (){
    // console.log($(this).attr("name"));
    if ($(this) && $(this).attr("name") && $(this).val() ) {
      var googleFontLink = document.getElementById("googlefont__" + elementfontSelector);
      if (!googleFontLink) {
        googleFontLink = document.createElement("link");
        googleFontLink.id = "googlefont__" + elementfontSelector;
        googleFontLink.type = "text/css";
        googleFontLink.rel = "stylesheet";
        googleFontLink.media = "screen";
        document.head.appendChild(googleFontLink);
      }
      var anonymousPro = $(this).val()+"|"+$(this).val()+":300|"+$(this).val()+":regular|"+$(this).val()+":500|"+$(this).val()+":600|"+$(this).val()+":700|"+$(this).val()+":800|"+$(this).val()+":italic|"+$(this).val()+":500italic|"+$(this).val()+":600italic|"+$(this).val()+":700italic|"+$(this).val()+":800italic";
      var apiUrl = [];
      apiUrl.push('https://fonts.googleapis.com/css?family=');
      apiUrl.push(anonymousPro.replace(/ /g, '+'));
      // url: 'https://fonts.googleapis.com/css?family=Roboto|Roboto:300|Roboto:regular|Roboto:500|Roboto:600|Roboto:700|Roboto:800|Roboto:italic|Roboto:500italic|Roboto:600italic|Roboto:700italic|Roboto:800italic'
      var url = apiUrl.join('');
      // googleFontLink.href = "https://fonts.googleapis.com/css2?family=" + encodeURIComponent(selectedFont.family);
      // console.log(url);
      googleFontLink.href = url;
    }
  });
}
changeGFontOnSelectorChange ("rjee_faqs_header_text_font");
```
