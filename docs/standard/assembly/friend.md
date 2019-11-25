---
title: Дружественные сборки
ms.date: 08/20/2019
ms.assetid: b65ea7de-0801-477a-a39c-e914c2cc107c
dev_langs:
- csharp
- vb
ms.openlocfilehash: a74d4b74ead8492028a092e090f9281231802a87
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348167"
---
# <a name="friend-assemblies"></a><span data-ttu-id="e7786-102">Дружественные сборки</span><span class="sxs-lookup"><span data-stu-id="e7786-102">Friend assemblies</span></span>

<span data-ttu-id="e7786-103">*Дружественная сборка* — это сборка, которая может обращаться к [внутренним](../../csharp/language-reference/keywords/internal.md) (C#) или [дружественным](../../visual-basic/language-reference/modifiers/friend.md) (Visual Basic) типам и членам другой сборки.</span><span class="sxs-lookup"><span data-stu-id="e7786-103">A *friend assembly* is an assembly that can access another assembly's [internal](../../csharp/language-reference/keywords/internal.md) (C#) or [Friend](../../visual-basic/language-reference/modifiers/friend.md) (Visual Basic) types and members.</span></span> <span data-ttu-id="e7786-104">Если сборка определяется как дружественная, помечать типы и члены как открытые для того, чтобы другие сборки могли получить к ним доступ, больше не требуется.</span><span class="sxs-lookup"><span data-stu-id="e7786-104">If you identify an assembly as a friend assembly, you no longer have to mark types and members as public in order for them to be accessed by other assemblies.</span></span> <span data-ttu-id="e7786-105">Это особенно удобно в следующих ситуациях:</span><span class="sxs-lookup"><span data-stu-id="e7786-105">This is especially convenient in the following scenarios:</span></span>

- <span data-ttu-id="e7786-106">Во время модульного теста, если тестовый код выполняется в отдельной сборке, но требует доступа к членам тестируемой сборки, помеченным как `internal` в C# или `Friend` в Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="e7786-106">During unit testing, when test code runs in a separate assembly but requires access to members in the assembly being tested that are marked as `internal` in C# or `Friend` in Visual Basic.</span></span>

- <span data-ttu-id="e7786-107">При разработке библиотек классов, если дополнения к этой библиотеке содержатся в отдельных сборках, но требуют доступа к членам в существующих сборках, помеченным как `internal`в C# или `Friend` в Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="e7786-107">When you are developing a class library and additions to the library are contained in separate assemblies but require access to members in existing assemblies that are marked as `internal` in C# or `Friend` in Visual Basic.</span></span>

## <a name="remarks"></a><span data-ttu-id="e7786-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="e7786-108">Remarks</span></span>

<span data-ttu-id="e7786-109">С помощью атрибута <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> можно определить одну или несколько дружественных сборок для указанной сборки.</span><span class="sxs-lookup"><span data-stu-id="e7786-109">You can use the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute to identify one or more friend assemblies for a given assembly.</span></span> <span data-ttu-id="e7786-110">В следующем примере используется атрибут <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> в сборке *Assembly A*, а сборка *AssemblyB* указана в качестве дружественной.</span><span class="sxs-lookup"><span data-stu-id="e7786-110">The following example uses the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute in *Assembly A* and specifies assembly *AssemblyB* as a friend assembly.</span></span> <span data-ttu-id="e7786-111">В результате сборка *AssemblyB* получает доступ ко всем типам и членам в сборке *Assembly A*, помеченным как `internal` в C# или `Friend` в Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="e7786-111">This gives assembly *AssemblyB* access to all types and members in *Assembly A* that are marked as `internal` in C# or `Friend` in Visual Basic.</span></span>

> [!NOTE]
> <span data-ttu-id="e7786-112">При компиляции сборки, такой как *AssemblyB*, которая будет обращаться ко внутренним типам или членам другой сборки, такой как *Assembly A*, нужно явно указать имя выходного файла (*EXE* или *DLL*), используя параметр компилятора **-out**.</span><span class="sxs-lookup"><span data-stu-id="e7786-112">When you compile an assembly like *AssemblyB* that will access internal types or internal members of another assembly like *Assembly A*, you must explicitly specify the name of the output file (*.exe* or *.dll*) by using the **-out** compiler option.</span></span> <span data-ttu-id="e7786-113">Это необходимо потому, что компилятор еще не создал имя сборки, формируемой во время привязки к внешним ссылкам.</span><span class="sxs-lookup"><span data-stu-id="e7786-113">This is required because the compiler has not yet generated the name for the assembly it is building at the time it is binding to external references.</span></span> <span data-ttu-id="e7786-114">Дополнительные сведения см. в разделе [-out (C#)](../../csharp/language-reference/compiler-options/out-compiler-option.md) или [-out (Visual Basic)](../../visual-basic/reference/command-line-compiler/out.md).</span><span class="sxs-lookup"><span data-stu-id="e7786-114">For more information, see [-out (C#)](../../csharp/language-reference/compiler-options/out-compiler-option.md) or [-out (Visual Basic)](../../visual-basic/reference/command-line-compiler/out.md).</span></span>

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

```vb
Imports System.Runtime.CompilerServices
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

<span data-ttu-id="e7786-115">Доступ к типам и членам `internal` (C#) или `Friend` (Visual Basic) могут получить только те сборки, которые будут явно обозначены как дружественные.</span><span class="sxs-lookup"><span data-stu-id="e7786-115">Only assemblies that you explicitly specify as friends can access `internal` (C#) or `Friend` (Visual Basic) types and members.</span></span> <span data-ttu-id="e7786-116">Например, если сборка *AssemblyB* является дружественной для сборки *Assembly A*, а сборка *Assembly C* ссылается на сборку *AssemblyB*, сборка *Assembly C* не получает доступ к типам `internal` (C#) или `Friend` (Visual Basic) в сборке *Assembly A*.</span><span class="sxs-lookup"><span data-stu-id="e7786-116">For example, if *AssemblyB* is a friend of *Assembly A* and *Assembly C* references *AssemblyB*, *Assembly C* does not have access to `internal` (C#) or `Friend` (Visual Basic) types in *Assembly A*.</span></span>

<span data-ttu-id="e7786-117">Компилятор выполняет некоторые основные проверки имени дружественной сборки, передаваемого в атрибут <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>.</span><span class="sxs-lookup"><span data-stu-id="e7786-117">The compiler performs some basic validation of the friend assembly name passed to the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute.</span></span> <span data-ttu-id="e7786-118">Если сборка *Assembly A* объявляет *AssemblyB* как дружественную сборку, действуют следующие правила проверки:</span><span class="sxs-lookup"><span data-stu-id="e7786-118">If *Assembly A* declares *AssemblyB* as a friend assembly, the validation rules are as follows:</span></span>

- <span data-ttu-id="e7786-119">Если сборка *Assembly A* имеет строгое имя, сборка *AssemblyB* должна также иметь строгое имя.</span><span class="sxs-lookup"><span data-stu-id="e7786-119">If *Assembly A* is strong named, *AssemblyB* must also be strong named.</span></span> <span data-ttu-id="e7786-120">Имя дружественной сборки, передаваемое в атрибут, должно состоять из имени сборки и открытого ключа из ключа строгого имени, который используется для подписи сборки *AssemblyB*.</span><span class="sxs-lookup"><span data-stu-id="e7786-120">The friend assembly name that is passed to the attribute must consist of the assembly name and the public key of the strong-name key that is used to sign *AssemblyB*.</span></span>

     <span data-ttu-id="e7786-121">Имя дружественной сборки, передаваемое в атрибут <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>, не может быть строгим именем сборки *AssemblyB*.</span><span class="sxs-lookup"><span data-stu-id="e7786-121">The friend assembly name that is passed to the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute cannot be the strong name of *AssemblyB*.</span></span> <span data-ttu-id="e7786-122">Не следует включать версию сборки, язык и региональные параметры, архитектуру или маркер открытого ключа.</span><span class="sxs-lookup"><span data-stu-id="e7786-122">Don't include the assembly version, culture, architecture, or public key token.</span></span>

- <span data-ttu-id="e7786-123">Если сборка *Assembly A* не имеет строгого имени, имя дружественной сборки должно состоять только из имени сборки.</span><span class="sxs-lookup"><span data-stu-id="e7786-123">If *Assembly A* is not strong named, the friend assembly name should consist of only the assembly name.</span></span> <span data-ttu-id="e7786-124">Дополнительные сведения см. в разделе [Практическое руководство. Создание неподписанных дружественных сборок](create-unsigned-friend.md).</span><span class="sxs-lookup"><span data-stu-id="e7786-124">For more information, see [How to: Create unsigned friend assemblies](create-unsigned-friend.md).</span></span>

- <span data-ttu-id="e7786-125">Если сборка *AssemblyB* имеет строгое имя, нужно указать ключ строгого имени для сборки *AssemblyB*, используя параметр проекта или параметр компилятора командной строки `/keyfile`.</span><span class="sxs-lookup"><span data-stu-id="e7786-125">If *AssemblyB* is strong named, you must specify the strong-name key for *AssemblyB* by using the project setting or the command-line `/keyfile` compiler option.</span></span> <span data-ttu-id="e7786-126">Дополнительные сведения см. в разделе [Практическое руководство. Создание подписанных дружественных сборок](create-signed-friend.md).</span><span class="sxs-lookup"><span data-stu-id="e7786-126">For more information, see [How to: Create signed friend assemblies](create-signed-friend.md).</span></span>

 <span data-ttu-id="e7786-127">Класс <xref:System.Security.Permissions.StrongNameIdentityPermission> также позволяет обеспечить общий доступ к типам, но имеет следующие отличия:</span><span class="sxs-lookup"><span data-stu-id="e7786-127">The <xref:System.Security.Permissions.StrongNameIdentityPermission> class also provides the ability to share types, with the following differences:</span></span>

- <span data-ttu-id="e7786-128">Класс <xref:System.Security.Permissions.StrongNameIdentityPermission> применяется к отдельному типу, тогда как дружественная сборка относится ко всей сборке.</span><span class="sxs-lookup"><span data-stu-id="e7786-128"><xref:System.Security.Permissions.StrongNameIdentityPermission> applies to an individual type, while a friend assembly applies to the whole assembly.</span></span>

- <span data-ttu-id="e7786-129">Если в сборке *Assembly A* существуют сотни типов, которые должны использоваться совместно со сборкой *AssemblyB*, к каждому из них необходимо добавить <xref:System.Security.Permissions.StrongNameIdentityPermission>.</span><span class="sxs-lookup"><span data-stu-id="e7786-129">If there are hundreds of types in *Assembly A* that you want to share with *AssemblyB*, you have to add <xref:System.Security.Permissions.StrongNameIdentityPermission> to all of them.</span></span> <span data-ttu-id="e7786-130">Если используется дружественная сборка, достаточно объявить дружественные отношения всего один раз.</span><span class="sxs-lookup"><span data-stu-id="e7786-130">If you use a friend assembly, you only need to declare the friend relationship once.</span></span>

- <span data-ttu-id="e7786-131">Если вы используете <xref:System.Security.Permissions.StrongNameIdentityPermission>, типы для общего доступа необходимо объявить как открытые.</span><span class="sxs-lookup"><span data-stu-id="e7786-131">If you use <xref:System.Security.Permissions.StrongNameIdentityPermission>, the types you want to share have to be declared as public.</span></span> <span data-ttu-id="e7786-132">При использовании дружественной сборки общие типы объявляются как `internal` (C#) или `Friend` (Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="e7786-132">If you use a friend assembly, the shared types are declared as `internal` (C#) or `Friend` (Visual Basic).</span></span>

<span data-ttu-id="e7786-133">Сведения о том, как получить доступ к типам и методам `internal` (C#) или `Friend` (Visual Basic) сборки из файла модуля (файла с расширением *NETMODULE*), см. в разделе [-moduleassemblyname (C#)](../../csharp/language-reference/compiler-options/moduleassemblyname-compiler-option.md) или [-moduleassemblyname (Visual Basic)](../../visual-basic/reference/command-line-compiler/moduleassemblyname.md).</span><span class="sxs-lookup"><span data-stu-id="e7786-133">For information about how to access an assembly's `internal` (C#) or `Friend` (Visual Basic) types and methods from a module file (a file with the *.netmodule* extension), see [-moduleassemblyname (C#)](../../csharp/language-reference/compiler-options/moduleassemblyname-compiler-option.md) or [-moduleassemblyname (Visual Basic)](../../visual-basic/reference/command-line-compiler/moduleassemblyname.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="e7786-134">См. также</span><span class="sxs-lookup"><span data-stu-id="e7786-134">See also</span></span>

- <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>
- <xref:System.Security.Permissions.StrongNameIdentityPermission>
- [<span data-ttu-id="e7786-135">Практическое руководство. Создание неподписанных дружественных сборок</span><span class="sxs-lookup"><span data-stu-id="e7786-135">How to: Create unsigned friend assemblies</span></span>](create-unsigned-friend.md)
- [<span data-ttu-id="e7786-136">Практическое руководство. Создание подписанных дружественных сборок</span><span class="sxs-lookup"><span data-stu-id="e7786-136">How to: Create signed friend assemblies</span></span>](create-signed-friend.md)
- [<span data-ttu-id="e7786-137">Сборки в .NET</span><span class="sxs-lookup"><span data-stu-id="e7786-137">Assemblies in .NET</span></span>](index.md)
- [<span data-ttu-id="e7786-138">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="e7786-138">C# programming guide</span></span>](../../csharp/programming-guide/index.md)
- [<span data-ttu-id="e7786-139">Основные понятия программирования (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e7786-139">Programming concepts (Visual Basic)</span></span>](../../visual-basic/programming-guide/concepts/index.md)
