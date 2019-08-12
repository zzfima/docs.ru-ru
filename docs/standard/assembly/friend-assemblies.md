---
title: Дружественные сборки (C#)
ms.date: 03/03/2019
ms.assetid: b65ea7de-0801-477a-a39c-e914c2cc107c
ms.openlocfilehash: 770eb70a5350d7d26e03cb4e605b442100da2a53
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "68671199"
---
# <a name="friend-assemblies"></a><span data-ttu-id="c7b68-102">Дружественные сборки</span><span class="sxs-lookup"><span data-stu-id="c7b68-102">Friend assemblies</span></span>

<span data-ttu-id="c7b68-103">*Дружественная сборка* — это сборка, которая может обращаться к [внутренним](../../csharp/language-reference/keywords/internal.md) (в C#, [дружественным](../../visual-basic/language-reference/modifiers/friend.md) в Visual Basic) типам и членам другой сборки.</span><span class="sxs-lookup"><span data-stu-id="c7b68-103">A *friend assembly* is an assembly that can access another assembly's [internal](../../csharp/language-reference/keywords/internal.md) (in C# or [Friend](../../visual-basic/language-reference/modifiers/friend.md) in Visual Basic) types and members.</span></span> <span data-ttu-id="c7b68-104">Если сборка определяется как дружественная, помечать типы и члены как открытые для того, чтобы другие сборки могли получить к ним доступ, больше не требуется.</span><span class="sxs-lookup"><span data-stu-id="c7b68-104">If you identify an assembly as a friend assembly, you no longer have to mark types and members as public in order for them to be accessed by other assemblies.</span></span> <span data-ttu-id="c7b68-105">Это особенно удобно в следующих ситуациях:</span><span class="sxs-lookup"><span data-stu-id="c7b68-105">This is especially convenient in the following scenarios:</span></span>

- <span data-ttu-id="c7b68-106">Во время модульного теста, если тестовый код выполняется в отдельной сборке, но требует доступа к членам тестируемой сборки, помеченным как `internal` в C# или `Friend` в Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="c7b68-106">During unit testing, when test code runs in a separate assembly but requires access to members in the assembly being tested that are marked as `internal` in C# or `Friend` in Visual Basic.</span></span>

- <span data-ttu-id="c7b68-107">При разработке библиотек классов, если дополнения к этой библиотеке содержатся в отдельных сборках, но требуют доступа к членам в существующих сборках, помеченным как `internal`в C# или `Friend` в Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="c7b68-107">When you are developing a class library and additions to the library are contained in separate assemblies but require access to members in existing assemblies that are marked as `internal` in C# or `Friend` in Visual Basic.</span></span>

## <a name="remarks"></a><span data-ttu-id="c7b68-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="c7b68-108">Remarks</span></span>

<span data-ttu-id="c7b68-109">С помощью атрибута <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> можно определить одну или несколько дружественных сборок для указанной сборки.</span><span class="sxs-lookup"><span data-stu-id="c7b68-109">You can use the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute to identify one or more friend assemblies for a given assembly.</span></span> <span data-ttu-id="c7b68-110">В следующем примере используется атрибут <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> в сборке A, а сборка `AssemblyB` указывается в качестве дружественной.</span><span class="sxs-lookup"><span data-stu-id="c7b68-110">The following example uses the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute in assembly A and specifies assembly `AssemblyB` as a friend assembly.</span></span> <span data-ttu-id="c7b68-111">В результате сборка `AssemblyB` получает доступ ко всем типам и членам в сборке А, помеченным как `internal` в C# или `Friend` в Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="c7b68-111">This gives assembly `AssemblyB` access to all types and members in assembly A that are marked as `internal` in C# or `Friend` in Visual Basic.</span></span>

> [!NOTE]
> <span data-ttu-id="c7b68-112">При компиляции сборки (сборки `AssemblyB`), которая будет обращаться ко внутренним типам или членам другой сборки (сборки *А*), необходимо прямо указать имя выходного файла (EXE или DLL), используя параметр компилятора **/out**.</span><span class="sxs-lookup"><span data-stu-id="c7b68-112">When you compile an assembly (assembly `AssemblyB`) that will access internal types or internal members of another assembly (assembly *A*), you must explicitly specify the name of the output file (.exe or .dll) by using the **/out** compiler option.</span></span> <span data-ttu-id="c7b68-113">Это необходимо потому, что компилятор еще не создал имя сборки, формируемой во время привязки к внешним ссылкам.</span><span class="sxs-lookup"><span data-stu-id="c7b68-113">This is required because the compiler has not yet generated the name for the assembly it is building at the time it is binding to external references.</span></span> <span data-ttu-id="c7b68-114">Дополнительные сведения см. в разделах [/out (C#)](../../csharp/language-reference/compiler-options/out-compiler-option.md) или [/out (Visual Basic)](../../visual-basic/reference/command-line-compiler/out.md).</span><span class="sxs-lookup"><span data-stu-id="c7b68-114">For more information, see [/out (C#)](../../csharp/language-reference/compiler-options/out-compiler-option.md) or [/out (Visual Basic)](../../visual-basic/reference/command-line-compiler/out.md).</span></span>

# <a name="ctabcsharp"></a>[<span data-ttu-id="c7b68-115">C#</span><span class="sxs-lookup"><span data-stu-id="c7b68-115">C#</span></span>](#tab/csharp)

```csharp
using System.Runtime.CompilerServices;
using System;

[assembly: InternalsVisibleTo("AssemblyB")]

// The class is internal by default.
class FriendClass
{
    public void Test()
    {
        Console.WriteLine("Sample Class");
    }
}

// Public class that has an internal method.
public class ClassWithFriendMethod
{
    internal void Test()
    {
        Console.WriteLine("Sample Method");
    }

}
```

# <a name="visual-basictabvb"></a>[<span data-ttu-id="c7b68-116">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c7b68-116">Visual Basic</span></span>](#tab/vb)

```vb
Imports System.Runtime.CompilerServices
Imports System
<Assembly: InternalsVisibleTo("AssemblyB")>

' Friend class.
Friend Class FriendClass
    Public Sub Test()
        Console.WriteLine("Sample Class")
    End Sub
End Class

' Public class with a Friend method.
Public Class ClassWithFriendMethod
    Friend Sub Test()
        Console.WriteLine("Sample Method")
    End Sub
End Class
```

---

<span data-ttu-id="c7b68-117">Доступ к типам и членам `internal` (в C#, `Friend` в Visual Basic) могут получить только те сборки, которые будут прямо обозначены как дружественные.</span><span class="sxs-lookup"><span data-stu-id="c7b68-117">Only assemblies that you explicitly specify as friends can access `internal` (in C# or `Friend` in Visual Basic) types and members.</span></span> <span data-ttu-id="c7b68-118">Например, если сборка B является дружественной для сборки A, а сборка C ссылается на сборку B, сборка C не получает доступ к типам `internal` (в C#, `Friend` в Visual Basic) в A.</span><span class="sxs-lookup"><span data-stu-id="c7b68-118">For example, if assembly B is a friend of assembly A and assembly C references assembly B, C does not have access to `internal` (in C# or `Friend` in Visual Basic) types in A.</span></span>

<span data-ttu-id="c7b68-119">Компилятор выполняет некоторые основные проверки имени дружественной сборки, передаваемого в атрибут <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>.</span><span class="sxs-lookup"><span data-stu-id="c7b68-119">The compiler performs some basic validation of the friend assembly name passed to the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute.</span></span> <span data-ttu-id="c7b68-120">Если сборка *A* объявляет *B* как дружественную сборку, действуют следующие правила проверки:</span><span class="sxs-lookup"><span data-stu-id="c7b68-120">If assembly *A* declares *B* as a friend assembly, the validation rules are as follows:</span></span>

- <span data-ttu-id="c7b68-121">Если сборка *A* имеет строгое имя, сборка *B* должна также иметь строгое имя.</span><span class="sxs-lookup"><span data-stu-id="c7b68-121">If assembly *A* is strong named, assembly *B* must also be strong named.</span></span> <span data-ttu-id="c7b68-122">Имя дружественной сборки, передаваемое в атрибут, должно состоять из имени сборки и открытого ключа из ключа строгого имени, который используется для подписи сборки *B*.</span><span class="sxs-lookup"><span data-stu-id="c7b68-122">The friend assembly name that is passed to the attribute must consist of the assembly name and the public key of the strong-name key that is used to sign assembly *B*.</span></span>

     <span data-ttu-id="c7b68-123">Имя дружественной сборки, передаваемое в атрибут <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>, не может быть строгим именем сборки *B*, поэтому включать в него версию сборки, язык и региональные параметры, архитектуру или маркер открытого ключа не следует.</span><span class="sxs-lookup"><span data-stu-id="c7b68-123">The friend assembly name that is passed to the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute cannot be the strong name of assembly *B*: do not include the assembly version, culture, architecture, or public key token.</span></span>

- <span data-ttu-id="c7b68-124">Если сборка *A* не имеет строгого имени, имя дружественной сборки должно состоять только из имени сборки.</span><span class="sxs-lookup"><span data-stu-id="c7b68-124">If assembly *A* is not strong named, the friend assembly name should consist of only the assembly name.</span></span> <span data-ttu-id="c7b68-125">Дополнительные сведения см. в разделе [Практическое руководство. Создание неподписанных дружественных сборок (C#)](../../csharp/programming-guide/concepts/assemblies-gac/how-to-create-unsigned-friend-assemblies.md) или [Практическое руководство. Создание неподписанных дружественных сборок (Visual Basic)](../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-unsigned-friend-assemblies.md).</span><span class="sxs-lookup"><span data-stu-id="c7b68-125">For more information, see [How to: Create Unsigned Friend Assemblies (C#)](../../csharp/programming-guide/concepts/assemblies-gac/how-to-create-unsigned-friend-assemblies.md) or [How to: Create Unsigned Friend Assemblies (Visual Basic)](../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-unsigned-friend-assemblies.md).</span></span>

- <span data-ttu-id="c7b68-126">Если сборка *B* имеет строгое имя, необходимо указать ключ строгого имени для сборки *B*, используя параметр проекта или параметр компилятора командной строки `/keyfile`.</span><span class="sxs-lookup"><span data-stu-id="c7b68-126">If assembly *B* is strong named, you must specify the strong-name key for assembly *B* by using the project setting or the command-line `/keyfile` compiler option.</span></span> <span data-ttu-id="c7b68-127">Дополнительные сведения см. в разделе [Практическое руководство. Создание подписанных дружественных сборок (C#)](../../csharp/programming-guide/concepts/assemblies-gac/how-to-create-signed-friend-assemblies.md) или [Практическое руководство. Создание подписанных дружественных сборок (Visual Basic)](../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-signed-friend-assemblies.md).</span><span class="sxs-lookup"><span data-stu-id="c7b68-127">For more information, see [How to: Create Signed Friend Assemblies (C#)](../../csharp/programming-guide/concepts/assemblies-gac/how-to-create-signed-friend-assemblies.md) or [How to: Create Signed Friend Assemblies (Visual Basic)](../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-signed-friend-assemblies.md).</span></span>

 <span data-ttu-id="c7b68-128">Класс <xref:System.Security.Permissions.StrongNameIdentityPermission> также позволяет обеспечить общий доступ к типам, но имеет следующие отличия:</span><span class="sxs-lookup"><span data-stu-id="c7b68-128">The <xref:System.Security.Permissions.StrongNameIdentityPermission> class also provides the ability to share types, with the following differences:</span></span>

- <span data-ttu-id="c7b68-129">Класс <xref:System.Security.Permissions.StrongNameIdentityPermission> применяется к отдельному типу, тогда как дружественная сборка относится ко всей сборке.</span><span class="sxs-lookup"><span data-stu-id="c7b68-129"><xref:System.Security.Permissions.StrongNameIdentityPermission> applies to an individual type, while a friend assembly applies to the whole assembly.</span></span>

- <span data-ttu-id="c7b68-130">Если в сборке *A* существуют сотни типов, которые должны использоваться совместно со сборкой *B*, к каждому из них необходимо добавить <xref:System.Security.Permissions.StrongNameIdentityPermission>.</span><span class="sxs-lookup"><span data-stu-id="c7b68-130">If there are hundreds of types in assembly *A* that you want to share with assembly *B*, you have to add <xref:System.Security.Permissions.StrongNameIdentityPermission> to all of them.</span></span> <span data-ttu-id="c7b68-131">Если используется дружественная сборка, достаточно объявить дружественные отношения всего один раз.</span><span class="sxs-lookup"><span data-stu-id="c7b68-131">If you use a friend assembly, you only need to declare the friend relationship once.</span></span>

- <span data-ttu-id="c7b68-132">Если вы используете <xref:System.Security.Permissions.StrongNameIdentityPermission>, типы для общего доступа необходимо объявить как открытые.</span><span class="sxs-lookup"><span data-stu-id="c7b68-132">If you use <xref:System.Security.Permissions.StrongNameIdentityPermission>, the types you want to share have to be declared as public.</span></span> <span data-ttu-id="c7b68-133">При использовании дружественной сборки общие типы объявляются как `internal` (в C#, `Friend` в Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="c7b68-133">If you use a friend assembly, the shared types are declared as `internal` (in C# or `Friend` in Visual Basic).</span></span>

<span data-ttu-id="c7b68-134">Сведения о том, как получить доступ к типам и методам сборки `internal` (в C#, `Friend` в Visual Basic) из файла модуля (файла с расширением NETMODULE), см. в разделе [/moduleassemblyname (C#)](../../csharp/language-reference/compiler-options/moduleassemblyname-compiler-option.md) или [/moduleassemblyname (Visual Basic)](../../visual-basic/reference/command-line-compiler/moduleassemblyname.md).</span><span class="sxs-lookup"><span data-stu-id="c7b68-134">For information about how to access an assembly's `internal` (in C# or `Friend` in Visual Basic) types and methods from a module file (a file with the .netmodule extension), see [/moduleassemblyname (C#)](../../csharp/language-reference/compiler-options/moduleassemblyname-compiler-option.md) or [/moduleassemblyname (Visual Basic)](../../visual-basic/reference/command-line-compiler/moduleassemblyname.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="c7b68-135">См. также</span><span class="sxs-lookup"><span data-stu-id="c7b68-135">See also</span></span>

- <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>
- <xref:System.Security.Permissions.StrongNameIdentityPermission>
- [<span data-ttu-id="c7b68-136">Практическое руководство. Создание неподписанных дружественных сборок (C#)</span><span class="sxs-lookup"><span data-stu-id="c7b68-136">How to: Create Unsigned Friend Assemblies (C#)</span></span>](../../csharp/programming-guide/concepts/assemblies-gac/how-to-create-unsigned-friend-assemblies.md)
- [<span data-ttu-id="c7b68-137">Практическое руководство. Создание неподписанных дружественных сборок (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c7b68-137">How to: Create Unsigned Friend Assemblies (Visual Basic)</span></span>](../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-unsigned-friend-assemblies.md)
- [<span data-ttu-id="c7b68-138">Практическое руководство. Создание подписанных дружественных сборок в C#</span><span class="sxs-lookup"><span data-stu-id="c7b68-138">How to: Create Signed Friend Assemblies (C#)</span></span>](../../csharp/programming-guide/concepts/assemblies-gac/how-to-create-signed-friend-assemblies.md)
- [<span data-ttu-id="c7b68-139">Практическое руководство. Создание подписанных дружественных сборок (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c7b68-139">How to: Create Signed Friend Assemblies (Visual Basic)</span></span>](../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-signed-friend-assemblies.md)
- [<span data-ttu-id="c7b68-140">Сборки в .NET</span><span class="sxs-lookup"><span data-stu-id="c7b68-140">Assemblies in .NET</span></span>](index.md)
- [<span data-ttu-id="c7b68-141">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="c7b68-141">C# Programming Guide</span></span>](../../csharp/programming-guide/index.md)
- [<span data-ttu-id="c7b68-142">Основные понятия программирования</span><span class="sxs-lookup"><span data-stu-id="c7b68-142">Programming Concepts</span></span>](../../visual-basic/programming-guide/concepts/index.md)
