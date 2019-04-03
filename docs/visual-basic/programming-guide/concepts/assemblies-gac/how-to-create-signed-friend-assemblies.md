---
title: Практическое руководство. Создание подписанных дружественных сборок (Visual Basic)
ms.date: 03/14/2018
ms.assetid: f2afd83d-b044-484b-a56d-56d0a8a40647
ms.openlocfilehash: 28cbd0c538441978464033df896d69f80a8396a6
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2019
ms.locfileid: "58836744"
---
# <a name="how-to-create-signed-friend-assemblies-visual-basic"></a>Практическое руководство. Создание подписанных дружественных сборок (Visual Basic)
В этом примере демонстрируется использование дружественных сборок со сборками, имеющими строгие имена. Обе сборки должны иметь строгое имя. Хотя обе сборки в этом примере используют одинаковые ключи, вы можете использовать для двух сборок разные ключи.  
  
### <a name="to-create-a-signed-assembly-and-a-friend-assembly"></a>Создание подписанной и дружественной сборки  
  
1.  Откройте окно командной строки.  
  
2.  Используйте следующую последовательность команд в средстве задания строгих имен для формирования файла ключа и отображения его открытого ключа. Дополнительные сведения см. в разделе [Sn.exe (средство строгих имен)](../../../../framework/tools/sn-exe-strong-name-tool.md)).  
  
    1.  Создайте ключ строгого имени для этого примера и сохраните его в файле FriendAssemblies.snk:  
  
         `sn -k FriendAssemblies.snk`  
  
    2.  Извлеките открытый ключ из FriendAssemblies.snk и поместите его в файл FriendAssemblies.publickey:  
  
         `sn -p FriendAssemblies.snk FriendAssemblies.publickey`  
  
    3.  Выведите на экран открытый ключ, хранящийся в файле FriendAssemblies.publickey:  
  
         `sn -tp FriendAssemblies.publickey`  
  
3.  Создайте файл Visual Basic `friend_signed_A` , содержащий следующий код. Атрибут <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> используется в коде для объявления friend_signed_B в качестве дружественной сборки.  
  
     Средство задания строгих имен создает новый открытый ключ при каждом запуске. Таким образом, необходимо заменить открытый ключ в следующем коде только что созданным открытым ключом, как показано в следующем примере.  
  
    ```vb  
    ' friend_signed_A.vb  
    ' Compile with:   
    ' Vbc -target:library -keyfile:FriendAssemblies.snk friend_signed_A.vb  
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
  
    ```console  
    Vbc -target:library -keyfile:FriendAssemblies.snk friend_signed_A.vb  
    ```  
  
5.  Создайте файл Visual Basic с именем `friend_signed_B` и содержит следующий код. Поскольку сборка friend_signed_A указывает сборку friend_signed_B в качестве дружественной сборки, код в сборке friend_signed_B может обращаться к типам и членам `Friend` в сборке friend_signed_A. Файл содержит следующий код.  
  
    ```vb  
    ' friend_signed_B.vb  
    ' Compile with:   
    ' Vbc -keyfile:FriendAssemblies.snk -r:friend_signed_A.dll friend_signed_B.vb  
    Module Sample  
        Public Sub Main()  
            Dim inst As New Class1  
            inst.Test()  
        End Sub  
    End Module  
    ```  
  
6.  Откомпилируйте и подпишите сборку friend_signed_B с помощью следующей команды.  
  
    ```console  
    vbc -keyfile:FriendAssemblies.snk -r:friend_signed_A.dll friend_signed_B.vb  
    ```  
  
     Имя сборки, созданной компилятором, должно соответствовать имени дружественной сборки, передаваемой атрибуту <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>. Можно явно задать сборку с помощью `-out` параметр компилятора. Дополнительные сведения см. в разделе [-out (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/out.md).  
  
7.  Запустите файл friend_signed_B.exe.  
  
     Программа отображает строку «Class1.Test».  
  
## <a name="net-framework-security"></a>Безопасность платформы .NET Framework  
 Между атрибутом <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> и классом <xref:System.Security.Permissions.StrongNameIdentityPermission> существует определенное сходство. Основное отличие заключается в том, что для выполнения <xref:System.Security.Permissions.StrongNameIdentityPermission> в определенном разделе кода могут потребоваться разрешения системы безопасности, тогда как атрибут <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> определяет видимость членов и типов `Friend`.  
  
## <a name="see-also"></a>См. также

- <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>
- [Сборки в .NET](../../../../standard/assembly/index.md)
- [Дружественные сборки](../../../../standard/assembly/friend-assemblies.md)
- [Практическое руководство. Создание неподписанных дружественных сборок (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-unsigned-friend-assemblies.md)
- [-keyfile](../../../../visual-basic/reference/command-line-compiler/keyfile.md)
- [Sn.exe (средство строгих имен)](../../../../framework/tools/sn-exe-strong-name-tool.md))
- [Создание и использование сборок со строгими именами](../../../../framework/app-domains/create-and-use-strong-named-assemblies.md)
- [Основные понятия программирования](../../../../visual-basic/programming-guide/concepts/index.md)
