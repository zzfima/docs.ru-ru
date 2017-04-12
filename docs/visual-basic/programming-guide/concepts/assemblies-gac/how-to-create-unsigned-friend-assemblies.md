---
title: "Практическое руководство: создание неподписанных дружественных сборок (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 5735eb79-9729-4c46-ac1f-537ada3acaa7
caps.latest.revision: 4
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: ceddb35c306f72c8927deda326d9fcca6c75d786
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-create-unsigned-friend-assemblies-visual-basic"></a>Практическое руководство: создание неподписанных дружественных сборок (Visual Basic)
В этом примере показано использование дружественных сборок с неподписанными сборками.  
  
### <a name="to-create-an-assembly-and-a-friend-assembly"></a>Для создания сборки и дружественной сборки  
  
1.  Откройте окно командной строки.  
  
2.  Создайте файл Visual Basic с именем `friend_signed_A.` , содержащий следующий код. Код использует <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>атрибут для объявления friend_signed_B в качестве дружественной сборки.</xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>  
  
    ```vb  
    ' friend_unsigned_A.vb  
    ' Compile with:   
    ' Vbc /target:library friend_unsigned_A.vb  
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
  
3.  Откомпилируйте и подпишите сборку friend_signed_A с помощью следующей команды.  
  
    ```vb  
    Vbc /target:library friend_unsigned_A.vb  
    ```  
  
4.  Создайте файл Visual Basic с именем `friend_unsigned_B` , содержащий следующий код. Поскольку friend_unsigned_A friend_unsigned_B указывает в качестве дружественной сборки, код в friend_unsigned_B можно получить доступ к `Friend` типов и членов из friend_unsigned_A.  
  
    ```vb  
    ' friend_unsigned_B.vb  
    ' Compile with:   
    ' Vbc /r:friend_unsigned_A.dll friend_unsigned_B.vb  
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
  
5.  Откомпилируйте сборку friend_signed_B с помощью следующей команды.  
  
    ```vb  
    Vbc /r:friend_unsigned_A.dll friend_unsigned_B.vb  
    ```  
  
     Имя сборки, созданных компилятором должно совпадать имя дружественной сборки, передаваемое <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>атрибут.</xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> Можно явно задать сборку, используя `/out` параметр компилятора.  
  
6.  Запустите файл friend_signed_B.exe.  
  
     Программа выводит две строки: «Class1.Test» и «Class2.Test».  
  
## <a name="net-framework-security"></a>Безопасность платформы .NET Framework  
 Существует сходство между <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>атрибутом и <xref:System.Security.Permissions.StrongNameIdentityPermission>класса.</xref:System.Security.Permissions.StrongNameIdentityPermission> </xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> Основное различие заключается в, <xref:System.Security.Permissions.StrongNameIdentityPermission>может потребовать разрешения безопасности для выполнения определенного раздела кода, тогда как <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>атрибут управляет видимостью `Friend` типы и члены.</xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> </xref:System.Security.Permissions.StrongNameIdentityPermission>  
  
## <a name="see-also"></a>См. также  
 <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute></xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>   
 [Сборки и глобальный кэш сборок (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)   
 [Дружественные сборки (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/friend-assemblies.md)   
 [Практическое руководство: Создание подписанных дружественных сборок (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-signed-friend-assemblies.md)   
 [Основные понятия программирования руководство](../../../../visual-basic/programming-guide/concepts/index.md)
