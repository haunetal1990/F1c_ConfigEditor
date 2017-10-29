# ConfigEditor_F1c
F1 Challenge 99-02 Config Editor

What we need?
- 1 Button 
- 34 Textboxes
- 1 Combobox

Imports System
Imports System.Xml

Public Class Form1
Private Declare Ansi Function GetPrivateProfileString Lib "kernel32.dll" Alias "GetPrivateProfileStringA" (ByVal lpApplicationName As String, ByVal lpKeyName As String, ByVal lpDefault As String, ByVal lpReturnedString As String, ByVal nSize As Int32, ByVal lpFileName As String) As Int32
Private Declare Ansi Function WritePrivateProfileString Lib "kernel32.dll" Alias "WritePrivateProfileStringA" (ByVal lpApplicationName As String, ByVal lpKeyName As String, ByVal lpString As String, ByVal lpFileName As String) As Int32

    Private Sub Button1_Click(sender As Object, e As EventArgs) Handles Button1.Click
        INI_WriteValueToFile("COMPONENTS", "SEASONDIR", Textbox1.Text, ".\config.ini")
        INI_WriteValueToFile("COMPONENTS", "SOUNDDIR", Textbox2.Text, ".\config.ini")
        INI_WriteValueToFile("COMPONENTS", "VEHICLESOUND", TextBox3.Text, ".\config.ini")
        INI_WriteValueToFile("COMPONENTS", "OPTIONSANIM", TextBox4.Text, ".\config.ini")
        INI_WriteValueToFile("COMPONENTS", "OPTIONSFLAGS", TextBox5.Text, ".\config.ini")
        INI_WriteValueToFile("COMPONENTS", "OPTIONSSOUNDS", TextBox11.Text, ".\config.ini")
        INI_WriteValueToFile("COMPONENTS", "OPTIONSDIR", TextBox13.Text, ".\config.ini")
        INI_WriteValueToFile("COMPONENTS", "REPLAYDIR", TextBox8.Text, ".\config.ini")
        INI_WriteValueToFile("COMPONENTS", "MOVIEDIR", TextBox14.Text, ".\config.ini")
        INI_WriteValueToFile("COMPONENTS", "TRACKSDIR", TextBox12.Text, ".\config.ini")
        INI_WriteValueToFile("COMPONENTS", "VEHICLESDIR", TextBox16.Text, ".\config.ini")
        INI_WriteValueToFile("COMPONENTS", "DRIVERSDIR", TextBox18.Text, ".\config.ini")
        INI_WriteValueToFile("COMPONENTS", "LOGDIR", TextBox15.Text, ".\config.ini")
        INI_WriteValueToFile("COMPONENTS", "SAVEDIR", TextBox19.Text, ".\config.ini")
        INI_WriteValueToFile("COMPONENTS", "MUSICDIR", TextBox17.Text, ".\config.ini")
        INI_WriteValueToFile("COMPONENTS", "CAMERAEDITORRESOURCEDIR", TextBox25.Text, ".\config.ini")
        INI_WriteValueToFile("COMPONENTS", "GRIDSIZE", TextBox27.Text, ".\config.ini")
        INI_WriteValueToFile("COMPONENTS", "CPURATING", TextBox26.Text, ".\config.ini")
        INI_WriteValueToFile("COMPONENTS", "SYSTEMRAM", TextBox21.Text, ".\config.ini")
        INI_WriteValueToFile("COMPONENTS", "VIDEORAM", TextBox23.Text, ".\config.ini")
        INI_WriteValueToFile("COMPONENTS", "OBJDETAIL", TextBox20.Text, ".\config.ini")
        INI_WriteValueToFile("COMPONENTS", "TEXDETAIL", TextBox24.Text, ".\config.ini")
        INI_WriteValueToFile("COMPONENTS", "VIDEOGUID", TextBox22.Text, ".\config.ini")
        INI_WriteValueToFile("COMPONENTS", "VIDEODRIVER", TextBox29.Text, ".\config.ini")
        INI_WriteValueToFile("COMPONENTS", "VIDEOMODE", TextBox31.Text, ".\config.ini")
        INI_WriteValueToFile("COMPONENTS", "WINDOWEDMODE", TextBox28.Text, ".\config.ini")
        INI_WriteValueToFile("COMPONENTS", "RUNBENCHMARKS", TextBox32.Text, ".\config.ini")
        INI_WriteValueToFile("COMPONENTS", "FSAA", TextBox30.Text, ".\config.ini")
        INI_WriteValueToFile("COMPONENTS", "VSYNC", TextBox34.Text, ".\config.ini")
        INI_WriteValueToFile("COMPONENTS", "VBSTRATEGY", TextBox33.Text, ".\config.ini")

        INI_WriteValueToFile("INSTALL", "INSTALLFROM", TextBox6.Text, ".\config.ini")
        INI_WriteValueToFile("INSTALL", "INSTALLTO", TextBox7.Text, ".\config.ini")

        INI_WriteValueToFile("AUTOLAUNCH", "MODE", ComboBox1.Text, ".\config.ini")
        INI_WriteValueToFile("AUTOLAUNCH", "LAUNCHTIME", TextBox9.Text, ".\config.ini")

        INI_WriteValueToFile("VERSION", "VERSION", TextBox10.Text, ".\config.ini")
    End Sub

    Private Sub Form1_Load(sender As Object, e As EventArgs) Handles MyBase.Load
        If IO.File.Exists(".\Config.ini") Then
            Textbox1.Text = INI_ReadValueFromFile("COMPONENTS", "SEASONDIR", Textbox1.Text, ".\config.ini")
            Textbox2.Text = INI_ReadValueFromFile("COMPONENTS", "SOUNDDIR", Textbox2.Text, ".\config.ini")
            TextBox3.Text = INI_ReadValueFromFile("COMPONENTS", "VEHICLESOUND", TextBox3.Text, ".\config.ini")
            TextBox4.Text = INI_ReadValueFromFile("COMPONENTS", "OPTIONSANIM", TextBox4.Text, ".\config.ini")
            TextBox5.Text = INI_ReadValueFromFile("COMPONENTS", "OPTIONSFLAGS", TextBox5.Text, ".\config.ini")
            TextBox11.Text = INI_ReadValueFromFile("COMPONENTS", "OPTIONSSOUNDS", TextBox11.Text, ".\config.ini")
            TextBox13.Text = INI_ReadValueFromFile("COMPONENTS", "OPTIONSDIR", TextBox13.Text, ".\config.ini")
            TextBox8.Text = INI_ReadValueFromFile("COMPONENTS", "REPLAYDIR", TextBox8.Text, ".\config.ini")
            TextBox14.Text = INI_ReadValueFromFile("COMPONENTS", "MOVIEDIR", TextBox14.Text, ".\config.ini")
            TextBox12.Text = INI_ReadValueFromFile("COMPONENTS", "TRACKSDIR", TextBox12.Text, ".\config.ini")
            TextBox16.Text = INI_ReadValueFromFile("COMPONENTS", "VEHICLESDIR", TextBox16.Text, ".\config.ini")
            TextBox18.Text = INI_ReadValueFromFile("COMPONENTS", "DRIVERSDIR", TextBox18.Text, ".\config.ini")
            TextBox15.Text = INI_ReadValueFromFile("COMPONENTS", "LOGDIR", TextBox15.Text, ".\config.ini")
            TextBox19.Text = INI_ReadValueFromFile("COMPONENTS", "SAVEDIR", TextBox19.Text, ".\config.ini")
            TextBox17.Text = INI_ReadValueFromFile("COMPONENTS", "MUSICDIR", TextBox17.Text, ".\config.ini")
            TextBox25.Text = INI_ReadValueFromFile("COMPONENTS", "CAMERAEDITORRESOURCEDIR", TextBox25.Text, ".\config.ini")
            TextBox27.Text = INI_ReadValueFromFile("COMPONENTS", "GRIDSIZE", TextBox27.Text, ".\config.ini")
            TextBox26.Text = INI_ReadValueFromFile("COMPONENTS", "CPURATING", TextBox26.Text, ".\config.ini")
            TextBox21.Text = INI_ReadValueFromFile("COMPONENTS", "SYSTEMRAM", TextBox21.Text, ".\config.ini")
            TextBox23.Text = INI_ReadValueFromFile("COMPONENTS", "VIDEORAM", TextBox23.Text, ".\config.ini")
            TextBox20.Text = INI_ReadValueFromFile("COMPONENTS", "OBJDETAIL", TextBox20.Text, ".\config.ini")
            TextBox24.Text = INI_ReadValueFromFile("COMPONENTS", "TEXDETAIL", TextBox24.Text, ".\config.ini")
            TextBox22.Text = INI_ReadValueFromFile("COMPONENTS", "VIDEOGUID", TextBox22.Text, ".\config.ini")
            TextBox29.Text = INI_ReadValueFromFile("COMPONENTS", "VIDEODRIVER", TextBox29.Text, ".\config.ini")
            TextBox31.Text = INI_ReadValueFromFile("COMPONENTS", "VIDEOMODE", TextBox31.Text, ".\config.ini")
            TextBox28.Text = INI_ReadValueFromFile("COMPONENTS", "WINDOWEDMODE", TextBox28.Text, ".\config.ini")
            TextBox32.Text = INI_ReadValueFromFile("COMPONENTS", "RUNBENCHMARKS", TextBox32.Text, ".\config.ini")
            TextBox30.Text = INI_ReadValueFromFile("COMPONENTS", "FSAA", TextBox30.Text, ".\config.ini")
            TextBox34.Text = INI_ReadValueFromFile("COMPONENTS", "VSYNC", TextBox34.Text, ".\config.ini")
            TextBox33.Text = INI_ReadValueFromFile("COMPONENTS", "VBSTRATEGY", TextBox33.Text, ".\config.ini")

            TextBox6.Text = INI_ReadValueFromFile("INSTALL", "INSTALLFROM", TextBox6.Text, ".\config.ini")
            TextBox7.Text = INI_ReadValueFromFile("INSTALL", "INSTALLTO", TextBox7.Text, ".\config.ini")

            ComboBox1.Text = INI_ReadValueFromFile("AUTOLAUNCH", "MODE", ComboBox1.Text, ".\config.ini")
            TextBox9.Text = INI_ReadValueFromFile("AUTOLAUNCH", "LAUNCHTIME", TextBox9.Text, ".\config.ini")

            TextBox10.Text = INI_ReadValueFromFile("VERSION", "VERSION", TextBox10.Text, ".\config.ini")
        Else
            MessageBox.Show("Original Config.ini is not avaible ! Check the folder path", "ERROR: 100")
        End If

    End Sub

    Private Function INI_ReadValueFromFile(ByVal strSection As String, ByVal strKey As String, ByVal strDefault As String, ByVal strFile As String) As String
        'Funktion zum Lesen
        'strSection = Sektion in der INI-Datei
        'strKey = Name des Schlüssels
        'strDefault = Standardwert, wird zurückgegeben, wenn der Wert in der INI-Datei nicht gefunden wurde
        'strFile = Vollständiger Pfad zur INI-Datei
        Dim strTemp As String = Space(1024), lLength As Integer
        lLength = GetPrivateProfileString(strSection, strKey, strDefault, strTemp, strTemp.Length, strFile)
        Return (strTemp.Substring(0, lLength))
    End Function

    Public Function INI_WriteValueToFile(ByVal strSection As String, ByVal strKey As String, ByVal strValue As String, ByVal strFile As String) As Boolean
        'Funktion zum Schreiben
        'strSection = Sektion in der INI-Datei
        'strKey = Name des Schlüssels
        'strValue = Wert, der geschrieben werden soll
        'strFile = Vollständiger Pfad zur INI-Datei
        Return (Not (WritePrivateProfileString(strSection, strKey, strValue, strFile) = 0))
    End Function
    Private Sub TextBox9_KeyPress(sender As Object, e As KeyPressEventArgs) Handles TextBox9.KeyPress

    End Sub
End Class
