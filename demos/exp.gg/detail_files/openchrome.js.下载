function openInChrome(target) {
    var ifc = document.createElement("div");
    ifc.innerHTML = "<iframe src='googlechrome://navigate?url=" + target +
        "' style='width:0;height:0;border:0; border:none;visibility: hidden;'></iframe>";
    document.body.appendChild(ifc);
}

function isAndroid() {
    var ua = navigator.userAgent || navigator.vendor || window.opera;
    return ua.match(/Android/i)
}

(function tryOpenBrowser() {
    if (isAndroid()) {
        if (document.body){
            openInChrome(window.location.href);
        }else{
            window.requestAnimationFrame(tryOpenBrowser);
        }
    }
})()
