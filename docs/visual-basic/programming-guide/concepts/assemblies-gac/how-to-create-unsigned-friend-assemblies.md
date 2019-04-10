---
title: Практическое руководство. Создание неподписанных дружественных сборок (Visual Basic)
ms.date: 03/14/2018
ms.assetid: 5735eb79-9729-4c46-ac1f-537ada3acaa7
ms.openlocfilehash: 4771d0fe116d1532c270cf41b209665d5403a9b8
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2019
ms.locfileid: "59339181"
---
# <a name="how-to-create-unsigned-friend-assemblies-visual-basic"></a>Практическое руководство. Создание неподписанных дружественных сборок (Visual Basic)
В этом примере показано использование дружественных сборок с неподписанными сборками.  
  
### <a name="to-create-an-assembly-and-a-friend-assembly"></a>Создание сборки и дружественной сборки  
  
1. Откройте окно командной строки.  
  
2. Создайте файл Visual Basic `friend_signed_A.` , содержащий следующий код. Атрибут <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> используется в коде для объявления friend_signed_B в качестве дружественной сборки.  
  
    ```vb  
    ' friend_unsigned_A.vb  
    ' Compile with:   
    ' vbc -target:library friend_unsigned_A.vb  
    Imports System.Runtime.CompilerServices  
    Imports System  
  
    <Assembly: InternalsVisibleTo("friend_unsigned_B")>   
  
    ' Friend type.  
    Friend Class Class1  
        Public Sub Test()  
            Console.WriteLine("Class1.Test")  
        End Sub  
    End Class  
  
    ' Public type with Friend member.  
    Public Class Class2  
        Friend Sub Test()  
            Console.WriteLine("Class2.Test")  
        End Sub  
    End Class  
    ```  
  
3. Скомпилируйте и подпишите сборку friend_signed_A с помощью приведенной ниже команды.  
  
    ```console  
    vbc -target:library friend_unsigned_A.vb  
    ```  
  
4. Создайте файл Visual Basic `friend_unsigned_B` , содержащий следующий код. Так как файл friend_unsigned_A задает friend_unsigned_B в качестве дружественной сборки, код friend_unsigned_B может обращаться к типам и членам `Friend` из friend_unsigned_A.  
  
    ```vb  
    ' friend_unsigned_B.vb  
    ' Compile with:   
    ' vbc -r:friend_unsigned_A.dll friend_unsigned_B.vb  
    Module Module1  
        Sub Main()  
            ' Access a Friend type.  
            Dim inst1 As New Class1()  
            inst1.Test()  
  
            Dim inst2 As New Class2()  
            ' Access a Friend member of a public type.  
            inst2.Test()  
  
            System.Console.ReadLine()  
        End Sub  
    End Module  
    ```  
  
5. Скомпилируйте сборку friend_signed_B с помощью приведенной ниже команды.  
  
    ```console
    vbc -r:friend_unsigned_A.dll friend_unsigned_B.vb  
    ```  
  
     Имя сборки, созданной компилятором, должно соответствовать имени дружественной сборки, передаваемой атрибуту <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>. Можно явно задать сборку с помощью `/out` параметр компилятора.  
  
6. Запустите файл friend_signed_B.exe.  
  
     Программа выводит две строки: Class1.Test и Class2.Test.  
  
## <a name="net-framework-security"></a>Безопасность платформы .NET Framework  
 Между атрибутом <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> и классом <xref:System.Security.Permissions.StrongNameIdentityPermission> существует определенное сходство. Основное отличие заключается в том, что для выполнения <xref:System.Security.Permissions.StrongNameIdentityPermission> в определенном разделе кода могут потребоваться разрешения системы безопасности, тогда как атрибут <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> определяет видимость членов и типов `Friend`.  
  
## <a name="see-also"></a>См. также

- <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>
- [Сборки в .NET](../../../../standard/assembly/index.md)
- [Дружественные сборки](../../../../standard/assembly/friend-assemblies.md)
- [Практическое руководство. Создание подписанных дружественных сборок (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-signed-friend-assemblies.md)
- [Основные понятия о программировании руководство](../../../../visual-basic/programming-guide/concepts/index.md)
