Public Function MyStock(StockCode)
 
Dim exobj As New WinHttp.WinHttpRequest  
Dim tmp As String  
Dim HtmlPath, Sp As String   HtmlPath = "[http://finance.naver.com/item/main.nhn?code=](http://finance.naver.com/item/main.nhn?code=)" & StockCode
 
exobj.Open "GET", HtmlPath  
exobj.Send  
exobj.WaitForResponse   tmp = exobj.ResponseText   Sp = Split(tmp, "현재가")(1)  
Sp = Split(Sp, "전일대비")(0)   MyStock = Sp   End Function