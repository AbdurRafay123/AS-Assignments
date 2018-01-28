# AS-Assignments
Task 1.1

Module Module1

    Sub Main()
        Dim MemberName As String
        Dim MemberID As Integer
        Dim MoreRec As Char

        MemberName = ""
        MemberID = 0
        MoreRec = "Y"

        FileOpen(1, "d:\FilePractice\Records.txt", OpenMode.Output)

        While MoreRec = "Y" Or MoreRec = "y"
            Console.Write("Enter Member Name:")
            MemberName = Console.ReadLine
            Console.Write("Enter Member ID:")
            MemberID = Console.ReadLine
            WriteLine(1, MemberName)
            WriteLine(1, MemberID)
            Console.Write("Do you want to enter more records (Y/N)?:")
            MoreRec = Console.ReadLine
        End While

        FileClose(1)

       
    End Sub
    
End Module

Task 1.2

Module Module1

    Sub Main()
        Dim MemberName As String
        Dim MemberID As Integer

        MemberName = ""
        MemberID = 0

        FileOpen(1, "d:\FilePractice\Records.txt", OpenMode.Input)

        While Not EOF(1)
            Input(1, MemberName)
            Input(1, MemberID)
            Console.WriteLine("Member Name :" & MemberName)
            Console.WriteLine("Member ID :" & MemberID)
        End While

        FileClose(1)

        Console.ReadLine()


    End Sub

End Module

Task 1.3

Module Module1

    Sub Main()
        Dim MemberName, SearchedMemName As String
        Dim MemberID As Integer
        Dim IsFound As Boolean

        MemberName = ""
        MemberID = 0
        IsFound = False
        SearchedMemName = ""

        Console.Write("Enter Member Name to search for:")
        SearchedMemName = Console.ReadLine

        FileOpen(1, "d:\FilePractice\Records.txt", OpenMode.Input)

        While Not EOF(1) And IsFound = False
            Input(1, MemberName)
            Input(1, MemberID)
            If String.Compare(MemberName, SearchedMemName, True) = 0 Then
                IsFound = True
                Console.WriteLine("Member ID:" & MemberID)
            End If
        End While

        FileClose(1)

        If IsFound = False Then
            Console.WriteLine("Record Not Found")
        End If

        Console.ReadKey()

    End Sub

End Module

Task 1.4

Module Module1

    Sub Main()
        Dim MemberName As String
        Dim MemberId As Integer
        Dim MoreRec As Char

        MemberName = ""
        MemberId = 0
        MoreRec = "Y"

        FileOpen(1, "d:\FilePractice\Records.txt", OpenMode.Append)

        While MoreRec = "Y" Or MoreRec = "y"
            Console.Write("Enter Name of Member you want to add:")
            MemberName = Console.ReadLine
            Console.Write("Enter ID of member you want to add:")
            MemberId = Console.ReadLine
            WriteLine(1, MemberName)
            WriteLine(1, MemberId)
            Console.Write("Do you want to add more records? (Y/N):")
            MoreRec = Console.ReadLine
        End While

    End Sub

End Module

Task 1.5

Module Module1

    Sub Main()
        Dim MemberName As String
        Dim MemberID As Integer
        Dim TelephoneNo As String
        Dim MembershipStartDate As String

        MemberName = ""
        MemberID = 0
        TelephoneNo = ""
        MembershipStartDate = ""

        FileOpen(1, "d:\FilePractice\Records.txt", OpenMode.Input)
        FileOpen(2, "d:\FilePractice\UpdatedRecords.txt", OpenMode.Output)

        While Not EOF(1)
            Input(1, MemberName)
            Input(1, MemberID)
            Console.WriteLine("Enter telephone number for " & MemberName & ", MemberID: " & MemberID)
            TelephoneNo = Console.ReadLine
            Console.WriteLine("Enter membership start date for " & MemberName & ", MemberID: " & MemberID)
            MembershipStartDate = Console.ReadLine
            WriteLine(2, MemberName)
            WriteLine(2, MemberID)
            WriteLine(2, TelephoneNo)
            WriteLine(2, MembershipStartDate)
        End While

        FileClose(1)
        FileClose(2)

    End Sub

End Module
