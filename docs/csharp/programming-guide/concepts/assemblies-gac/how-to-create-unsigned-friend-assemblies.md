---
title: Как выполнить Создание неподписанных дружественных сборок (C#)
ms.date: 07/20/2015
ms.assetid: 78cbc4f0-b021-4141-a4ff-eb4edbd814ca
ms.openlocfilehash: 6bc2d807b3d1cf6c82a9ba6303139b9758581f35
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59318238"
---
# <a name="how-to-create-unsigned-friend-assemblies-c"></a>Как выполнить Создание неподписанных дружественных сборок (C#)
В этом примере показано использование дружественных сборок с неподписанными сборками.  
  
### <a name="to-create-an-assembly-and-a-friend-assembly"></a>Создание сборки и дружественной сборки  
  
1. Откройте окно командной строки.  
  
2. Создайте файл C# с именем `friend_unsigned_A.`, содержащий приведенный ниже код. Атрибут <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> используется в коде для объявления friend_unsigned_В в качестве дружественной сборки.  
  
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
  
3. Скомпилируйте и подпишите сборку friend_unsigned_A с помощью следующей команды.  
  
    ```csharp  
    csc /target:library friend_unsigned_A.cs  
    ```  
  
4. Создайте файл C# с именем `friend_unsigned_B`, содержащий приведенный ниже код. Так как файл friend_unsigned_A задает friend_unsigned_B в качестве дружественной сборки, код friend_unsigned_B может обращаться к типам и членам `internal` из friend_unsigned_A.  
  
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
  
5. Скомпилируйте сборку friend_unsigned_В с помощью следующей команды.  
  
    ```csharp  
    csc /r:friend_unsigned_A.dll /out:friend_unsigned_B.exe friend_unsigned_B.cs  
    ```  
  
     Имя сборки, созданной компилятором, должно соответствовать имени дружественной сборки, передаваемой атрибуту <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>. Необходимо явно указать имя выходной сборки (EXE или DLL) с помощью параметра компилятора `/out`. Дополнительные сведения см. в разделе [/out (параметры компилятора C#)](../../../../csharp/language-reference/compiler-options/out-compiler-option.md).  
  
6. Запустите файл friend_unsigned_B.exe.  
  
     Программа выведет две строки: Class1.Test и Class2.Test.  
  
## <a name="net-framework-security"></a>Безопасность платформы .NET Framework  
 Между атрибутом <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> и классом <xref:System.Security.Permissions.StrongNameIdentityPermission> существует определенное сходство. Основное отличие заключается в том, что для выполнения <xref:System.Security.Permissions.StrongNameIdentityPermission> в определенном разделе кода могут потребоваться разрешения системы безопасности, тогда как атрибут <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> определяет видимость членов и типов `internal`.  
  
## <a name="see-also"></a>См. также

- <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>
- [Сборки в .NET](../../../../standard/assembly/index.md)
- [Дружественные сборки](../../../../standard/assembly/friend-assemblies.md)
- [Практическое руководство. Создание подписанных дружественных сборок в C#](../../../../csharp/programming-guide/concepts/assemblies-gac/how-to-create-signed-friend-assemblies.md)
- [Руководство по программированию на C#](../../../../csharp/programming-guide/index.md)
