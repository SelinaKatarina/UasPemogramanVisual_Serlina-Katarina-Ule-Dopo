# UasPemogramanVisual_Serlina-Katarina-Ule-Dopo
Program Milkshake Menu
Imports System.IO

Public Class Form1
    Private myStreamReader As StreamReader

    Private Sub cmbMenu_SelectedIndexChanged(sender As Object, e As EventArgs) Handles cmbMenu.SelectedIndexChanged
        If cmbMenu.Text = "Original MilkShake" Then
            txtharga.Text = 18000

        ElseIf cmbMenu.Text = "Chocolate MilkShake" Then
            txtharga.Text = 25000

        ElseIf cmbMenu.Text = "Millo MilkShake" Then
            txtharga.Text = 45000

        ElseIf cmbMenu.Text = "Strawberry MilkShake" Then
            txtharga.Text = 30000

        ElseIf cmbMenu.Text = "Orange MilkShake" Then
            txtharga.Text = 25000

        ElseIf cmbMenu.Text = "THaiTea MilkShake" Then
            txtharga.Text = 20000

        End If
    End Sub

    Private Sub tmblTotal_Click(sender As Object, e As EventArgs) Handles tmblTotal.Click
        txtTotalBayar.Text = txtharga.Text * txtPesanan.Text
    End Sub



    Private Sub deletebutton_Click(sender As Object, e As EventArgs) Handles deletebutton.Click
        cmbMenu.Text = " "
        txtTotalBayar.Text = " "
        txtharga.Text = " "
        Text = " "
        txtPesanan.Text = " "

    End Sub

    Private Sub txtPesanan_TextChanged(sender As Object, e As EventArgs) Handles txtPesanan.TextChanged

    End Sub


    Private Sub Form1_Load(sender As Object, e As EventArgs) Handles MyBase.Load
        For i As Integer = 1 To 2
            MsgBox("Selamat datang di Milkshake Shop!")
        Next

        ReadFile("C:\boxtext\mytextfile.txt")
    End Sub


    Private Sub ReadFile(filePath As String)
        If File.Exists(filePath) Then
            Try
                myStreamReader = New StreamReader(filePath)
                Dim line As String
                While Not myStreamReader.EndOfStream
                    line = myStreamReader.ReadLine()
                    MsgBox(line)
                End While
                myStreamReader.Close()
            Catch ex As Exception
                MsgBox("Terjadi kesalahan saat membaca file: " & ex.Message, MsgBoxStyle.Critical, "Error")
            End Try
        Else
            MsgBox("File tidak ditemukan!", MsgBoxStyle.Exclamation, "Error")
        End If

    End Sub

    'CloseProgram
    Private Sub closeprogram_Click(sender As Object, e As EventArgs) Handles closeprogram.Click
        Dim result As DialogResult = MessageBox.Show("Apakah anda ingin keluar?", "Konfirmasi", MessageBoxButtons.YesNo, MessageBoxIcon.Question)
        For i As Integer = 1 To 1
            MsgBox("Terima Kasih sudah Berkunjung!!")
            MsgBox("Selamat Menikmati!!")

        Next

        If result = DialogResult.Yes Then
            Me.Close()
        End If
    End Sub


End Class



