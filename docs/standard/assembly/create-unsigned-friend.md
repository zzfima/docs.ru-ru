---
title: Практическое руководство. Создание неподписанных дружественных сборок
ms.date: 08/19/2019
ms.assetid: 78cbc4f0-b021-4141-a4ff-eb4edbd814ca
dev_langs:
- csharp
- vb
ms.openlocfilehash: f8fec064507553b8208083578165965de2303a33
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "74352438"
---
# <a name="how-to-create-unsigned-friend-assemblies"></a><span data-ttu-id="cc744-102">Практическое руководство. Создание неподписанных дружественных сборок</span><span class="sxs-lookup"><span data-stu-id="cc744-102">How to: Create unsigned friend assemblies</span></span>

<span data-ttu-id="cc744-103">В этом примере показано использование дружественных сборок с неподписанными сборками.</span><span class="sxs-lookup"><span data-stu-id="cc744-103">This example shows how to use friend assemblies with assemblies that are unsigned.</span></span>

## <a name="create-an-assembly-and-a-friend-assembly"></a><span data-ttu-id="cc744-104">Создание сборки и дружественной сборки</span><span class="sxs-lookup"><span data-stu-id="cc744-104">Create an assembly and a friend assembly</span></span>

1. <span data-ttu-id="cc744-105">Откройте окно командной строки.</span><span class="sxs-lookup"><span data-stu-id="cc744-105">Open a command prompt.</span></span>

2. <span data-ttu-id="cc744-106">Создайте файл C# или Visual Basic с именем *friend_unsigned_A*, содержащий приведенный ниже код.</span><span class="sxs-lookup"><span data-stu-id="cc744-106">Create a C# or Visual Basic file named *friend_unsigned_A* that contains the following code.</span></span> <span data-ttu-id="cc744-107">Атрибут <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> используется в коде для объявления *friend_unsigned_B* в качестве дружественной сборки.</span><span class="sxs-lookup"><span data-stu-id="cc744-107">The code uses the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute to declare *friend_unsigned_B* as a friend assembly.</span></span>

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

3. <span data-ttu-id="cc744-108">Скомпилируйте и подпишите сборку *friend_unsigned_A* с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="cc744-108">Compile and sign *friend_unsigned_A* by using the following command:</span></span>

   ```csharp
   csc /target:library friend_unsigned_A.cs
   ```

   ```vb
   vbc -target:library friend_unsigned_A.vb
   ```

4. <span data-ttu-id="cc744-109">Создайте файл C# или Visual Basic с именем *friend_unsigned_B*, содержащий приведенный ниже код.</span><span class="sxs-lookup"><span data-stu-id="cc744-109">Create a C# or Visual Basic file named *friend_unsigned_B* that contains the following code.</span></span> <span data-ttu-id="cc744-110">Так как сборка *friend_unsigned_A* указывает сборку *friend_unsigned_B* в качестве дружественной, код в сборке *friend_unsigned_B* может обращаться к типам и членам `internal` (C#) или `Friend` (Visual Basic) в сборке *friend_unsigned_A*.</span><span class="sxs-lookup"><span data-stu-id="cc744-110">Because *friend_unsigned_A* specifies *friend_unsigned_B* as a friend assembly, the code in *friend_unsigned_B* can access `internal` (C#) or `Friend` (Visual Basic) types and members from *friend_unsigned_A*.</span></span>

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

5. <span data-ttu-id="cc744-111">Скомпилируйте сборку *friend_unsigned_B* с помощью приведенной ниже команды.</span><span class="sxs-lookup"><span data-stu-id="cc744-111">Compile *friend_unsigned_B* by using the following command.</span></span>

   ```csharp
   csc /r:friend_unsigned_A.dll /out:friend_unsigned_B.exe friend_unsigned_B.cs
   ```

   ```vb
   vbc -r:friend_unsigned_A.dll friend_unsigned_B.vb
   ```

   <span data-ttu-id="cc744-112">Имя сборки, созданной компилятором, должно соответствовать имени дружественной сборки, передаваемой атрибуту <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>.</span><span class="sxs-lookup"><span data-stu-id="cc744-112">The name of the assembly that is generated by the compiler must match the friend assembly name that is passed to the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute.</span></span> <span data-ttu-id="cc744-113">Необходимо явно указать имя выходной сборки (*EXE* или *DLL*) с помощью параметра компилятора `-out`.</span><span class="sxs-lookup"><span data-stu-id="cc744-113">You must explicitly specify the name of the output assembly (*.exe* or *.dll*) by using the `-out` compiler option.</span></span> <span data-ttu-id="cc744-114">Дополнительные сведения см. в разделе [-out (параметры компилятора C#)](../../csharp/language-reference/compiler-options/out-compiler-option.md) или [-out (Visual Basic)](../../visual-basic/reference/command-line-compiler/out.md).</span><span class="sxs-lookup"><span data-stu-id="cc744-114">For more information, see [-out (C# compiler options)](../../csharp/language-reference/compiler-options/out-compiler-option.md) or [-out (Visual Basic)](../../visual-basic/reference/command-line-compiler/out.md)..</span></span>

6. <span data-ttu-id="cc744-115">Запустите файл *friend_unsigned_B.exe*.</span><span class="sxs-lookup"><span data-stu-id="cc744-115">Run the *friend_unsigned_B.exe* file.</span></span>

   <span data-ttu-id="cc744-116">Программа выводит две строки: **Class1.Test** и **Class2.Test**.</span><span class="sxs-lookup"><span data-stu-id="cc744-116">The program outputs two strings: **Class1.Test** and **Class2.Test**.</span></span>

## <a name="net-security"></a><span data-ttu-id="cc744-117">Безопасность в .NET</span><span class="sxs-lookup"><span data-stu-id="cc744-117">.NET security</span></span>

<span data-ttu-id="cc744-118">Между атрибутом <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> и классом <xref:System.Security.Permissions.StrongNameIdentityPermission> существует определенное сходство.</span><span class="sxs-lookup"><span data-stu-id="cc744-118">There are similarities between the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute and the <xref:System.Security.Permissions.StrongNameIdentityPermission> class.</span></span> <span data-ttu-id="cc744-119">Основное отличие заключается в том, что для выполнения <xref:System.Security.Permissions.StrongNameIdentityPermission> в определенном разделе кода могут потребоваться разрешения системы безопасности, тогда как атрибут <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> определяет видимость членов и типов `internal` или `Friend` (Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="cc744-119">The main difference is that <xref:System.Security.Permissions.StrongNameIdentityPermission> can demand security permissions to run a particular section of code, whereas the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute controls the visibility of `internal`  or `Friend` (Visual Basic) types and members.</span></span>

## <a name="see-also"></a><span data-ttu-id="cc744-120">См. также</span><span class="sxs-lookup"><span data-stu-id="cc744-120">See also</span></span>

- <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>
- [<span data-ttu-id="cc744-121">Сборки в .NET</span><span class="sxs-lookup"><span data-stu-id="cc744-121">Assemblies in .NET</span></span>](index.md)
- [<span data-ttu-id="cc744-122">Дружественные сборки</span><span class="sxs-lookup"><span data-stu-id="cc744-122">Friend assemblies</span></span>](friend.md)
- [<span data-ttu-id="cc744-123">Практическое руководство. Создание подписанных дружественных сборок</span><span class="sxs-lookup"><span data-stu-id="cc744-123">How to: Create signed friend assemblies</span></span>](create-signed-friend.md)
- [<span data-ttu-id="cc744-124">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="cc744-124">C# programming guide</span></span>](../../csharp/programming-guide/index.md)
- [<span data-ttu-id="cc744-125">Основные понятия программирования (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cc744-125">Programming concepts (Visual Basic)</span></span>](../../visual-basic/programming-guide/concepts/index.md)
