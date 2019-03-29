## Rangeを引数で渡す関数呼び出しの際に「オブジェクトが必要です」エラーが出る

``` vba
Sub Worksheet_Change(ByVal Target As Range)
    ' この位置でエラー発生
    Test(Target)
    
    ' これなら問題なくよびだせる
    Call Test(Target)
    ' これでもOK
    Test Target
End Sub

Public Sub Test(Target As Range)
    ' なんらかの処理
End Sub
```
