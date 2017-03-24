---
title: "Практическое руководство: Создание подписанных дружественных сборок (Visual Basic) | Документы Microsoft"
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
ms.assetid: f2afd83d-b044-484b-a56d-56d0a8a40647
caps.latest.revision: 4
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 1a69f7e833800ec7417bc35fad763f1001b3e7f9
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-create-signed-friend-assemblies-visual-basic"></a>Практическое руководство: Создание подписанных дружественных сборок (Visual Basic)
В этом примере показано использование дружественных сборок со сборками, имеющими строгие имена. Обе сборки должны иметь строгое имя. Хотя обе сборки этого примера используют одинаковые ключи, для двух сборок можно использовать различные ключи.  
  
### <a name="to-create-a-signed-assembly-and-a-friend-assembly"></a>Для создания подписанной и дружественной сборки  
  
1.  Откройте окно командной строки.  
  
2.  Используйте следующую последовательность команд с помощью программы строгих имен для формирования файла ключа и отображения его открытого ключа. Дополнительные сведения см. на странице [Sn.exe (Strong Name Tool)](https://msdn.microsoft.com/library/k5b5tt23) (Sn.exe: средство строгих имен).  
  
    1.  Создание ключа строгого имени для этого примера и сохранить его в файл FriendAssemblies.snk:  
  
         `sn -k FriendAssemblies.snk`  
  
    2.  Извлечь открытый ключ из FriendAssemblies.snk и перевести ее в FriendAssemblies.publickey:  
  
         `sn -p FriendAssemblies.snk FriendAssemblies.publickey`  
  
    3.  Для отображения открытого ключа, хранящегося в файле FriendAssemblies.publickey:  
  
         `sn -tp FriendAssemblies.publickey`  
  
3.  Создайте файл Visual Basic с именем `friend_signed_A` , содержащий следующий код. Код использует <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>атрибут для объявления friend_signed_B в качестве дружественной сборки.</xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>  
  
     Программа строгих имен создает новый открытый ключ, каждый раз при его запуске. Таким образом необходимо заменить открытый ключ в следующем коде с помощью открытого ключа, который только что созданную, как показано в следующем примере.  
  
    ```vb  
    ' friend_signed_A.vb  
    ' Compile with:   
    ' Vbc /target:library /keyfile:FriendAssemblies.snk friend_signed_A.vb  
    Imports System.Runtime.CompilerServices  
  
    <Assembly: InternalsVisibleTo("friend_signed_B, PublicKey=0024000004800000940000000602000000240000525341310004000001000100e3aedce99b7e10823920206f8e46cd5558b4ec7345bd1a5b201ffe71660625dcb8f9a08687d881c8f65a0dcf042f81475d2e88f3e3e273c8311ee40f952db306c02fbfc5d8bc6ee1e924e6ec8fe8c01932e0648a0d3e5695134af3bb7fab370d3012d083fa6b83179dd3d031053f72fc1f7da8459140b0af5afc4d2804deccb6")>   
    Public Class Class1  
        Public Sub Test()  
            System.Console.WriteLine("Class1.Test")  
            System.Console.ReadLine()  
        End Sub  
    End Class  
    ```  
  
4.  Откомпилируйте и подпишите сборку friend_signed_A с помощью следующей команды.  
  
    ```vb  
    Vbc /target:library /keyfile:FriendAssemblies.snk friend_signed_A.vb  
    ```  
  
5.  Создайте файл Visual Basic с именем `friend_signed_B` и содержит следующий код. Поскольку сборку friend_signed_A указывает сборку friend_signed_B в качестве дружественной сборки, могут обращаться к кода в сборку friend_signed_B `Friend` типы и члены в сборку friend_signed_A. Файл содержит следующий код.  
  
    ```vb  
    ' friend_signed_B.vb  
    ' Compile with:   
    ' Vbc /keyfile:FriendAssemblies.snk /r:friend_signed_A.dll friend_signed_B.vb  
    Module Sample  
        Public Sub Main()  
            Dim inst As New Class1  
            inst.Test()  
        End Sub  
    End Module  
    ```  
  
6.  Откомпилируйте и подпишите сборку friend_signed_B с помощью следующей команды.  
  
    ```vb  
    Vbc /keyfile:FriendAssemblies.snk /r:friend_signed_A.dll friend_signed_B.vb  
    ```  
  
     Имя сборки, созданный компилятором, должно соответствовать имя дружественной сборки, передаваемый <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>атрибут.</xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> Можно явно задать сборку, используя `/out` параметр компилятора. Дополнительные сведения см. в разделе [/out (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/out.md).  
  
7.  Запустите файл friend_signed_B.exe.  
  
     Программа выводит строку «Class1.Test».  
  
## <a name="net-framework-security"></a>Безопасность платформы .NET Framework  
 Существует сходство между <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>атрибутом и <xref:System.Security.Permissions.StrongNameIdentityPermission>класса.</xref:System.Security.Permissions.StrongNameIdentityPermission> </xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> Основное различие заключается в, <xref:System.Security.Permissions.StrongNameIdentityPermission>может потребовать разрешения безопасности для выполнения определенного раздела кода, тогда как <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>атрибут управляет видимостью `Friend` типы и члены.</xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> </xref:System.Security.Permissions.StrongNameIdentityPermission>  
  
## <a name="see-also"></a>См. также  
 <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute></xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>   
 [Сборки и глобальный кэш сборок (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)   
 [Дружественные сборки (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/friend-assemblies.md)   
 [Практическое руководство: создание неподписанных дружественных сборок (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-unsigned-friend-assemblies.md)   
 [/ keyfile](../../../../visual-basic/reference/command-line-compiler/keyfile.md)   
 [Sn.exe (средство строгих имен)](https://msdn.microsoft.com/library/k5b5tt23)   
 [Создание и использование сборок со строгими именами](https://msdn.microsoft.com/library/xwb8f617)   
 [Основные понятия программирования](../../../../visual-basic/programming-guide/concepts/index.md)
