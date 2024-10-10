Func _File_Unblock($sFilePath)

    Local $hFile = FileOpen($sFilePath & ":Zone.Identifier", 2)
    If $hFile = -1 Then Return SetError(1, 0, False)
    FileWrite($hFile, "")
    FileClose($hFile)
    Return True

EndFunc
