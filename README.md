# clickerby-isaac
Public Class Form1
    Dim Seconds As String
    Private Sub Button1_MouseDown(ByVal sender As Object, ByVal e As System.Windows.Forms.MouseEventArgs) Handles CloseButton.MouseDown
        Seconds = 0
        CloseLongTimer.Interval = 1000
        CloseLongTimer.Start()
    End Sub
    Private Sub CloseLongTimer_Tick(ByVal sender As Object, ByVal e As EventArgs) Handles CloseLongTimer.Tick
        Seconds += 1
    End Sub
    Private Sub CloseButton_MouseUp(ByVal sender As Object, ByVal e As System.Windows.Forms.MouseEventArgs) Handles CloseButton.MouseUp
        CloseLongTimer.Stop()
        If Seconds < 5 Then
            Me.Close()
        Else
            System.Environment.Exit(1)
        End If
    End Sub
End Class
