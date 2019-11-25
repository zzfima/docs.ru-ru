---
title: Практическое руководство. Создание неподписанных дружественных сборок
ms.date: 08/19/2019
ms.assetid: 78cbc4f0-b021-4141-a4ff-eb4edbd814ca
dev_langs:
- csharp
- vb
ms.openlocfilehash: f8fec064507553b8208083578165965de2303a33
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352438"
---
# <a name="how-to-create-unsigned-friend-assemblies"></a>Практическое руководство. Создание неподписанных дружественных сборок

В этом примере показано использование дружественных сборок с неподписанными сборками.

## <a name="create-an-assembly-and-a-friend-assembly"></a>Создание сборки и дружественной сборки

1. Откройте окно командной строки.

2. Создайте файл C# или Visual Basic с именем *friend_unsigned_A*, содержащий приведенный ниже код. Атрибут <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> используется в коде для объявления *friend_unsigned_B* в качестве дружественной сборки.

   ```csharp
   // friend_unsigned_A.cs
   // Compile with:
   // csc /target:library friend_unsigned_A.cs
   using System.Runtime.CompilerServices;
   using System;

   [assembly: InternalsVisibleTo("friend_unsigned_B")]

   // Type is internal by default.
   class Class1
   {
       public void Test()
       {
           Console.WriteLine("Class1.Test");
       }
   }

   // Public type with internal member.
   public class Class2
   {
       internal void Test()
       {
           Console.WriteLine("Class2.Test");
       }
   }
   ```

   ```vb
   ' friend_unsigned_A.vb
   ' Compile with:
   ' vbc -target:library friend_unsigned_A.vb
   Imports System.Runtime.CompilerServices

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

3. Скомпилируйте и подпишите сборку *friend_unsigned_A* с помощью следующей команды:

   ```csharp
   csc /target:library friend_unsigned_A.cs
   ```

   ```vb
   vbc -target:library friend_unsigned_A.vb
   ```

4. Создайте файл C# или Visual Basic с именем *friend_unsigned_B*, содержащий приведенный ниже код. Так как сборка *friend_unsigned_A* указывает сборку *friend_unsigned_B* в качестве дружественной, код в сборке *friend_unsigned_B* может обращаться к типам и членам `internal` (C#) или `Friend` (Visual Basic) в сборке *friend_unsigned_A*.

   ```csharp
   // friend_unsigned_B.cs
   // Compile with:
   // csc /r:friend_unsigned_A.dll /out:friend_unsigned_B.exe friend_unsigned_B.cs
   public class Program
   {
       static void Main()
       {
           // Access an internal type.
           Class1 inst1 = new Class1();
           inst1.Test();

           Class2 inst2 = new Class2();
           // Access an internal member of a public type.
           inst2.Test();

           System.Console.ReadLine();
       }
   }
   ```

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

5. Скомпилируйте сборку *friend_unsigned_B* с помощью приведенной ниже команды.

   ```csharp
   csc /r:friend_unsigned_A.dll /out:friend_unsigned_B.exe friend_unsigned_B.cs
   ```

   ```vb
   vbc -r:friend_unsigned_A.dll friend_unsigned_B.vb
   ```

   Имя сборки, созданной компилятором, должно соответствовать имени дружественной сборки, передаваемой атрибуту <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>. Необходимо явно указать имя выходной сборки (*EXE* или *DLL*) с помощью параметра компилятора `-out`. Дополнительные сведения см. в разделе [-out (параметры компилятора C#)](../../csharp/language-reference/compiler-options/out-compiler-option.md) или [-out (Visual Basic)](../../visual-basic/reference/command-line-compiler/out.md).

6. Запустите файл *friend_unsigned_B.exe*.

   Программа выводит две строки: **Class1.Test** и **Class2.Test**.

## <a name="net-security"></a>Безопасность в .NET

Между атрибутом <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> и классом <xref:System.Security.Permissions.StrongNameIdentityPermission> существует определенное сходство. Основное отличие заключается в том, что для выполнения <xref:System.Security.Permissions.StrongNameIdentityPermission> в определенном разделе кода могут потребоваться разрешения системы безопасности, тогда как атрибут <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> определяет видимость членов и типов `internal` или `Friend` (Visual Basic).

## <a name="see-also"></a>См. также

- <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>
- [Сборки в .NET](index.md)
- [Дружественные сборки](friend.md)
- [Практическое руководство. Создание подписанных дружественных сборок](create-signed-friend.md)
- [Руководство по программированию на C#](../../csharp/programming-guide/index.md)
- [Основные понятия программирования (Visual Basic)](../../visual-basic/programming-guide/concepts/index.md)
