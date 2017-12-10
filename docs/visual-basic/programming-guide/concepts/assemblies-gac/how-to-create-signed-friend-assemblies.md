---
title: "Как: Создание подписанных дружественных сборок (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f2afd83d-b044-484b-a56d-56d0a8a40647
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 9e549eeb67c41b3172dd5a5885d59aa6069716a0
ms.sourcegitcommit: 685143b62385500f59bc36274b8adb191f573a16
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/09/2017
---
# <a name="how-to-create-signed-friend-assemblies-visual-basic"></a>Как: Создание подписанных дружественных сборок (Visual Basic)
В этом примере демонстрируется использование дружественных сборок со сборками, имеющими строгие имена. Обе сборки должны иметь строгое имя. Хотя обе сборки в этом примере используют одинаковые ключи, вы можете использовать для двух сборок разные ключи.  
  
### <a name="to-create-a-signed-assembly-and-a-friend-assembly"></a>Создание подписанной и дружественной сборки  
  
1.  Откройте окно командной строки.  
  
2.  Используйте следующую последовательность команд в средстве задания строгих имен для формирования файла ключа и отображения его открытого ключа. Дополнительные сведения см. на странице [Sn.exe (Strong Name Tool)](https://msdn.microsoft.com/library/k5b5tt23) (Sn.exe: средство строгих имен).  
  
    1.  Создайте ключ строгого имени для этого примера и сохраните его в файле FriendAssemblies.snk:  
  
         `sn -k FriendAssemblies.snk`  
  
    2.  Извлеките открытый ключ из FriendAssemblies.snk и поместите его в файл FriendAssemblies.publickey:  
  
         `sn -p FriendAssemblies.snk FriendAssemblies.publickey`  
  
    3.  Выведите на экран открытый ключ, хранящийся в файле FriendAssemblies.publickey:  
  
         `sn -tp FriendAssemblies.publickey`  
  
3.  Создайте файл Visual Basic с именем `friend_signed_A` , содержащий следующий код. Атрибут <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> используется в коде для объявления friend_signed_B в качестве дружественной сборки.  
  
     Средство задания строгих имен создает новый открытый ключ при каждом запуске. Таким образом, необходимо заменить открытый ключ в следующем коде только что созданным открытым ключом, как показано в следующем примере.  
  
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
  
4.  Скомпилируйте и подпишите сборку friend_signed_A с помощью приведенной ниже команды.  
  
    ```vb  
    Vbc /target:library /keyfile:FriendAssemblies.snk friend_signed_A.vb  
    ```  
  
5.  Создать файл Visual Basic, который называется `friend_signed_B` и содержит следующий код. Поскольку сборка friend_signed_A указывает сборку friend_signed_B в качестве дружественной сборки, код в сборке friend_signed_B может обращаться к типам и членам `Friend` в сборке friend_signed_A. Файл содержит следующий код.  
  
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
  
     Имя сборки, созданной компилятором, должно соответствовать имени дружественной сборки, передаваемой атрибуту <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>. Можно явно задать сборку с помощью `/out` параметр компилятора. Дополнительные сведения см. в разделе [/out (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/out.md).  
  
7.  Запустите файл friend_signed_B.exe.  
  
     Программа выводит строку "Class1.Test".  
  
## <a name="net-framework-security"></a>Безопасность платформы .NET Framework  
 Между атрибутом <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> и классом <xref:System.Security.Permissions.StrongNameIdentityPermission> существует определенное сходство. Основное отличие заключается в том, что для выполнения <xref:System.Security.Permissions.StrongNameIdentityPermission> в определенном разделе кода могут потребоваться разрешения системы безопасности, тогда как атрибут <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> определяет видимость членов и типов `Friend`.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>  
 [Сборки и глобальный кэш сборок (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)  
 [Дружественные сборки (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/friend-assemblies.md)  
 [Как: создание неподписанных дружественных сборок (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-unsigned-friend-assemblies.md)  
 [/keyfile](../../../../visual-basic/reference/command-line-compiler/keyfile.md)  
 [Sn.exe (средство строгих имен)](https://msdn.microsoft.com/library/k5b5tt23)  
 [Создание и использование сборок со строгими именами](../../../../../docs/framework/app-domains/create-and-use-strong-named-assemblies.md)  
 [Основные понятия программирования](../../../../visual-basic/programming-guide/concepts/index.md)
