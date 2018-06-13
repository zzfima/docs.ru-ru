---
title: Дружественные сборки (C#)
ms.date: 07/20/2015
ms.assetid: b65ea7de-0801-477a-a39c-e914c2cc107c
ms.openlocfilehash: c9265a6ce53d97f1d0b8aaeb0f1aae3b7b75f2cf
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33320870"
---
# <a name="friend-assemblies-c"></a><span data-ttu-id="d31c7-102">Дружественные сборки (C#)</span><span class="sxs-lookup"><span data-stu-id="d31c7-102">Friend Assemblies (C#)</span></span>
<span data-ttu-id="d31c7-103">*Дружественная сборка* — это сборка, которая может обращаться к [внутренним](../../../../csharp/language-reference/keywords/internal.md) типам и членам другой сборки.</span><span class="sxs-lookup"><span data-stu-id="d31c7-103">A *friend assembly* is an assembly that can access another assembly's [internal](../../../../csharp/language-reference/keywords/internal.md) types and members.</span></span> <span data-ttu-id="d31c7-104">Если сборка определяется как дружественная, помечать типы и члены как открытые для того, чтобы другие сборки могли получить к ним доступ, больше не требуется.</span><span class="sxs-lookup"><span data-stu-id="d31c7-104">If you identify an assembly as a friend assembly, you no longer have to mark types and members as public in order for them to be accessed by other assemblies.</span></span> <span data-ttu-id="d31c7-105">Это особенно удобно в следующих ситуациях:</span><span class="sxs-lookup"><span data-stu-id="d31c7-105">This is especially convenient in the following scenarios:</span></span>  
  
-   <span data-ttu-id="d31c7-106">Во время модульного теста, если тестовый код выполняется в отдельной сборке, но требует доступа к членам тестируемой сборки, помеченным как `internal`.</span><span class="sxs-lookup"><span data-stu-id="d31c7-106">During unit testing, when test code runs in a separate assembly but requires access to members in the assembly being tested that are marked as `internal` .</span></span>  
  
-   <span data-ttu-id="d31c7-107">При разработке библиотек классов, если дополнения к этой библиотеке содержатся в отдельных сборках, но требуют доступа к членам в существующих сборках, помеченным как `internal`.</span><span class="sxs-lookup"><span data-stu-id="d31c7-107">When you are developing a class library and additions to the library are contained in separate assemblies but require access to members in existing assemblies that are marked as `internal` .</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d31c7-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="d31c7-108">Remarks</span></span>  
 <span data-ttu-id="d31c7-109">С помощью атрибута <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> можно определить одну или несколько дружественных сборок для указанной сборки.</span><span class="sxs-lookup"><span data-stu-id="d31c7-109">You can use the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute to identify one or more friend assemblies for a given assembly.</span></span> <span data-ttu-id="d31c7-110">В следующем примере используется атрибут <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> в сборке A, а сборка `AssemblyB` указывается в качестве дружественной.</span><span class="sxs-lookup"><span data-stu-id="d31c7-110">The following example uses the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute in assembly A and specifies assembly `AssemblyB` as a friend assembly.</span></span> <span data-ttu-id="d31c7-111">В результате сборка `AssemblyB` получает доступ ко всем типам и членам в сборке А, помеченным как `internal`.</span><span class="sxs-lookup"><span data-stu-id="d31c7-111">This gives assembly `AssemblyB` access to all types and members in assembly A that are marked as `internal`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d31c7-112">При компиляции сборки (сборки `AssemblyB`), которая будет обращаться ко внутренним типам или членам другой сборки (сборки *А*), необходимо прямо указать имя выходного файла (EXE или DLL), используя параметр компилятора **/out**.</span><span class="sxs-lookup"><span data-stu-id="d31c7-112">When you compile an assembly (assembly `AssemblyB`) that will access internal types or internal members of another assembly (assembly *A*), you must explicitly specify the name of the output file (.exe or .dll) by using the **/out** compiler option.</span></span> <span data-ttu-id="d31c7-113">Это необходимо потому, что компилятор еще не создал имя сборки, формируемой во время привязки к внешним ссылкам.</span><span class="sxs-lookup"><span data-stu-id="d31c7-113">This is required because the compiler has not yet generated the name for the assembly it is building at the time it is binding to external references.</span></span> <span data-ttu-id="d31c7-114">Дополнительные сведения см. в разделе [/out (C#)](../../../../csharp/language-reference/compiler-options/out-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="d31c7-114">For more information, see [/out (C#)](../../../../csharp/language-reference/compiler-options/out-compiler-option.md) .</span></span>  
  
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
  
 <span data-ttu-id="d31c7-115">Доступ к типам и членам `internal` могут получить только те сборки, которые будут прямо обозначены как дружественные.</span><span class="sxs-lookup"><span data-stu-id="d31c7-115">Only assemblies that you explicitly specify as friends can access `internal` types and members.</span></span> <span data-ttu-id="d31c7-116">Например, если сборка B является дружественной для сборки A, а сборка C ссылается на сборку B, сборка C не получает доступ к типам `internal` в A.</span><span class="sxs-lookup"><span data-stu-id="d31c7-116">For example, if assembly B is a friend of assembly A and assembly C references assembly B, C does not have access to `internal` types in A.</span></span>  
  
 <span data-ttu-id="d31c7-117">Компилятор выполняет некоторые основные проверки имени дружественной сборки, передаваемого в атрибут <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>.</span><span class="sxs-lookup"><span data-stu-id="d31c7-117">The compiler performs some basic validation of the friend assembly name passed to the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute.</span></span> <span data-ttu-id="d31c7-118">Если сборка *A* объявляет *B* как дружественную сборку, действуют следующие правила проверки:</span><span class="sxs-lookup"><span data-stu-id="d31c7-118">If assembly *A* declares *B* as a friend assembly, the validation rules are as follows:</span></span>  
  
-   <span data-ttu-id="d31c7-119">Если сборка *A* имеет строгое имя, сборка *B* должна также иметь строгое имя.</span><span class="sxs-lookup"><span data-stu-id="d31c7-119">If assembly *A* is strong named, assembly *B* must also be strong named.</span></span> <span data-ttu-id="d31c7-120">Имя дружественной сборки, передаваемое в атрибут, должно состоять из имени сборки и открытого ключа из ключа строгого имени, который используется для подписи сборки *B*.</span><span class="sxs-lookup"><span data-stu-id="d31c7-120">The friend assembly name that is passed to the attribute must consist of the assembly name and the public key of the strong-name key that is used to sign assembly *B*.</span></span>  
  
     <span data-ttu-id="d31c7-121">Имя дружественной сборки, передаваемое в атрибут <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>, не может быть строгим именем сборки *B*, поэтому включать в него версию сборки, язык и региональные параметры, архитектуру или маркер открытого ключа не следует.</span><span class="sxs-lookup"><span data-stu-id="d31c7-121">The friend assembly name that is passed to the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute cannot be the strong name of assembly *B*: do not include the assembly version, culture, architecture, or public key token.</span></span>  
  
-   <span data-ttu-id="d31c7-122">Если сборка *A* не имеет строгого имени, имя дружественной сборки должно состоять только из имени сборки.</span><span class="sxs-lookup"><span data-stu-id="d31c7-122">If assembly *A* is not strong named, the friend assembly name should consist of only the assembly name.</span></span> <span data-ttu-id="d31c7-123">Дополнительные сведения см. в разделе [Практическое руководство. Создание неподписанных дружественных сборок (C#)](../../../../csharp/programming-guide/concepts/assemblies-gac/how-to-create-unsigned-friend-assemblies.md).</span><span class="sxs-lookup"><span data-stu-id="d31c7-123">For more information, see [How to: Create Unsigned Friend Assemblies (C#)](../../../../csharp/programming-guide/concepts/assemblies-gac/how-to-create-unsigned-friend-assemblies.md).</span></span>  
  
-   <span data-ttu-id="d31c7-124">Если сборка *B* имеет строгое имя, необходимо указать ключ строгого имени для сборки *B*, используя параметр проекта или параметр компилятора командной строки `/keyfile`.</span><span class="sxs-lookup"><span data-stu-id="d31c7-124">If assembly *B* is strong named, you must specify the strong-name key for assembly *B* by using the project setting or the command-line `/keyfile` compiler option.</span></span> <span data-ttu-id="d31c7-125">Дополнительные сведения см. в разделе [Практическое руководство. Создание подписанных дружественных сборок (C#)](../../../../csharp/programming-guide/concepts/assemblies-gac/how-to-create-signed-friend-assemblies.md).</span><span class="sxs-lookup"><span data-stu-id="d31c7-125">For more information, see [How to: Create Signed Friend Assemblies (C#)](../../../../csharp/programming-guide/concepts/assemblies-gac/how-to-create-signed-friend-assemblies.md).</span></span>  
  
 <span data-ttu-id="d31c7-126">Класс <xref:System.Security.Permissions.StrongNameIdentityPermission> также позволяет обеспечить общий доступ к типам, но имеет следующие отличия:</span><span class="sxs-lookup"><span data-stu-id="d31c7-126">The <xref:System.Security.Permissions.StrongNameIdentityPermission> class also provides the ability to share types, with the following differences:</span></span>  
  
-   <span data-ttu-id="d31c7-127">Класс <xref:System.Security.Permissions.StrongNameIdentityPermission> применяется к отдельному типу, тогда как дружественная сборка относится ко всей сборке.</span><span class="sxs-lookup"><span data-stu-id="d31c7-127"><xref:System.Security.Permissions.StrongNameIdentityPermission> applies to an individual type, while a friend assembly applies to the whole assembly.</span></span>  
  
-   <span data-ttu-id="d31c7-128">Если в сборке *A* существуют сотни типов, которые должны использоваться совместно со сборкой *B*, к каждому из них необходимо добавить <xref:System.Security.Permissions.StrongNameIdentityPermission>.</span><span class="sxs-lookup"><span data-stu-id="d31c7-128">If there are hundreds of types in assembly *A* that you want to share with assembly *B*, you have to add <xref:System.Security.Permissions.StrongNameIdentityPermission> to all of them.</span></span> <span data-ttu-id="d31c7-129">Если используется дружественная сборка, достаточно объявить дружественные отношения всего один раз.</span><span class="sxs-lookup"><span data-stu-id="d31c7-129">If you use a friend assembly, you only need to declare the friend relationship once.</span></span>  
  
-   <span data-ttu-id="d31c7-130">Если вы используете <xref:System.Security.Permissions.StrongNameIdentityPermission>, типы для общего доступа необходимо объявить как открытые.</span><span class="sxs-lookup"><span data-stu-id="d31c7-130">If you use <xref:System.Security.Permissions.StrongNameIdentityPermission>, the types you want to share have to be declared as public.</span></span> <span data-ttu-id="d31c7-131">При использовании дружественной сборки общие типы объявляются как `internal`.</span><span class="sxs-lookup"><span data-stu-id="d31c7-131">If you use a friend assembly, the shared types are declared as `internal`.</span></span>  
  
 <span data-ttu-id="d31c7-132">Сведения о том, как получить доступ к типам и методам сборки `internal` из файла модуля (файла с расширением NETMODULE), см. в разделе [/moduleassemblyname (C#)](../../../../csharp/language-reference/compiler-options/moduleassemblyname-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="d31c7-132">For information about how to access an assembly's `internal` types and methods from a module file (a file with the .netmodule extension), see [/moduleassemblyname (C#)](../../../../csharp/language-reference/compiler-options/moduleassemblyname-compiler-option.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d31c7-133">См. также</span><span class="sxs-lookup"><span data-stu-id="d31c7-133">See Also</span></span>  
 <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>  
 <xref:System.Security.Permissions.StrongNameIdentityPermission>  
 [<span data-ttu-id="d31c7-134">Практическое руководство. Создание неподписанных дружественных сборок (C#)</span><span class="sxs-lookup"><span data-stu-id="d31c7-134">How to: Create Unsigned Friend Assemblies (C#)</span></span>](../../../../csharp/programming-guide/concepts/assemblies-gac/how-to-create-unsigned-friend-assemblies.md)  
 [<span data-ttu-id="d31c7-135">Практическое руководство. Создание подписанных дружественных сборок (C#)</span><span class="sxs-lookup"><span data-stu-id="d31c7-135">How to: Create Signed Friend Assemblies (C#)</span></span>](../../../../csharp/programming-guide/concepts/assemblies-gac/how-to-create-signed-friend-assemblies.md)  
 [<span data-ttu-id="d31c7-136">Сборки и глобальный кэш сборок (C#)</span><span class="sxs-lookup"><span data-stu-id="d31c7-136">Assemblies and the Global Assembly Cache (C#)</span></span>](../../../../csharp/programming-guide/concepts/assemblies-gac/index.md)  
 [<span data-ttu-id="d31c7-137">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="d31c7-137">C# Programming Guide</span></span>](../../../../csharp/programming-guide/index.md)
