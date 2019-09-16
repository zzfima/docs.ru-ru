---
title: -moduleassemblyname (параметры компилятора C#)
ms.date: 07/20/2015
f1_keywords:
- /moduleassemblyname
helpviewer_keywords:
- moduleassemblyname compiler option [C#]
- /moduleassemblyname compiler option [C#]
- .moduleassemblyname compiler option [C#]
ms.assetid: d464d9b9-f18d-423b-95e9-66c7878fd53a
ms.openlocfilehash: 7562c0609d61b2388f5063bc480a4dfc715155db
ms.sourcegitcommit: 7b1ce327e8c84f115f007be4728d29a89efe11ef
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/13/2019
ms.locfileid: "70970076"
---
# <a name="-moduleassemblyname-c-compiler-option"></a><span data-ttu-id="e5e09-102">-moduleassemblyname (параметры компилятора C#)</span><span class="sxs-lookup"><span data-stu-id="e5e09-102">-moduleassemblyname (C# Compiler Option)</span></span>
<span data-ttu-id="e5e09-103">Указывает сборку, к неоткрытым типам которой может обращаться .netmodule.</span><span class="sxs-lookup"><span data-stu-id="e5e09-103">Specifies an assembly whose non-public types a .netmodule can access.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5e09-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e5e09-104">Syntax</span></span>  
  
```console  
-moduleassemblyname:assembly_name  
```  
  
## <a name="arguments"></a><span data-ttu-id="e5e09-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="e5e09-105">Arguments</span></span>  
 `assembly_name`  
 <span data-ttu-id="e5e09-106">Имя сборки, к неоткрытым типам которой может обращаться .netmodule.</span><span class="sxs-lookup"><span data-stu-id="e5e09-106">The name of the assembly whose non-public types the .netmodule can access.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e5e09-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="e5e09-107">Remarks</span></span>  
 <span data-ttu-id="e5e09-108">Параметр **-moduleassemblyname** нужно использовать при сборке модуля NETMODULE и выполнении следующий условий:</span><span class="sxs-lookup"><span data-stu-id="e5e09-108">**-moduleassemblyname** should be used when building a .netmodule, and where the following conditions are true:</span></span>  
  
- <span data-ttu-id="e5e09-109">.netmodule требуется доступ к неоткрытым типам в существующей сборке.</span><span class="sxs-lookup"><span data-stu-id="e5e09-109">The .netmodule needs access to non-public types in an existing assembly.</span></span>  
  
- <span data-ttu-id="e5e09-110">Известно имя сборки, в которой будет создан .netmodule.</span><span class="sxs-lookup"><span data-stu-id="e5e09-110">You know the name of the assembly into which the .netmodule will be built.</span></span>  
  
- <span data-ttu-id="e5e09-111">Существующая сборка предоставила дружественной сборке доступ к сборке, в которую будет встроен .netmodule.</span><span class="sxs-lookup"><span data-stu-id="e5e09-111">The existing assembly has granted friend assembly access to the assembly into which the .netmodule will be built.</span></span>  
  
 <span data-ttu-id="e5e09-112">Дополнительные сведения о сборке NETMODULE см. в разделе [-target:module (параметры компилятора C#)](./target-module-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="e5e09-112">For more information on building a .netmodule, see [-target:module (C# Compiler Options)](./target-module-compiler-option.md).</span></span>  
  
 <span data-ttu-id="e5e09-113">Дополнительные сведения см. в разделе [Дружественные сборки](../../../standard/assembly/friend.md).</span><span class="sxs-lookup"><span data-stu-id="e5e09-113">For more information on friend assemblies, see [Friend Assemblies](../../../standard/assembly/friend.md).</span></span>  
  
 <span data-ttu-id="e5e09-114">Этот параметр недоступен в среде разработки и может использоваться только при компиляции из командной строки.</span><span class="sxs-lookup"><span data-stu-id="e5e09-114">This option is not available from within the development environment; it is only available when compiling from the command line.</span></span>  
  
 <span data-ttu-id="e5e09-115">Этот параметр компилятора недоступен в Visual Studio и не может быть изменен программным способом.</span><span class="sxs-lookup"><span data-stu-id="e5e09-115">This compiler option is unavailable in Visual Studio and cannot be changed programmatically.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e5e09-116">Пример</span><span class="sxs-lookup"><span data-stu-id="e5e09-116">Example</span></span>  
 <span data-ttu-id="e5e09-117">В этом примере выполняется построение сборки частного типа, которой предоставляется дружественный доступ к сборке csman_an_assembly.</span><span class="sxs-lookup"><span data-stu-id="e5e09-117">This sample builds an assembly with a private type, and that gives friend assembly access to an assembly called csman_an_assembly.</span></span>  
  
```csharp  
// moduleassemblyname_1.cs  
// compile with: -target:library  
using System;  
using System.Runtime.CompilerServices;  
  
[assembly:InternalsVisibleTo ("csman_an_assembly")]  
  
class An_Internal_Class   
{  
    public void Test()   
    {   
        Console.WriteLine("An_Internal_Class.Test called");   
    }  
}  
```  
  
## <a name="example"></a><span data-ttu-id="e5e09-118">Пример</span><span class="sxs-lookup"><span data-stu-id="e5e09-118">Example</span></span>  
 <span data-ttu-id="e5e09-119">Этот пример строит .netmodule, который обращается к неоткрытому типу в сборке moduleassemblyname_1.dll.</span><span class="sxs-lookup"><span data-stu-id="e5e09-119">This sample builds a .netmodule that accesses a non-public type in the assembly moduleassemblyname_1.dll.</span></span> <span data-ttu-id="e5e09-120">Мы знаем, что модуль NETMODULE будет встроен в сборку csman_an_assembly, поэтому можем задать **-moduleassemblyname**, чтобы позволить NETMODULE обращаться к неоткрытым типам в сборке, которой предоставлен доступ к дружественной сборке csman_an_assembly.</span><span class="sxs-lookup"><span data-stu-id="e5e09-120">By knowing that this .netmodule will be built into an assembly called csman_an_assembly, we can specify **-moduleassemblyname**, allowing the .netmodule to access non-public types in an assembly that has granted friend assembly access to csman_an_assembly.</span></span>  
  
```csharp  
// moduleassemblyname_2.cs  
// compile with: -moduleassemblyname:csman_an_assembly -target:module -reference:moduleassemblyname_1.dll  
class B {  
    public void Test() {  
        An_Internal_Class x = new An_Internal_Class();  
        x.Test();  
    }  
}  
```  
  
## <a name="example"></a><span data-ttu-id="e5e09-121">Пример</span><span class="sxs-lookup"><span data-stu-id="e5e09-121">Example</span></span>  
 <span data-ttu-id="e5e09-122">В следующем примере кода выполнено построение сборки csman_an_assembly со ссылками на ранее построенную сборку и .netmodule.</span><span class="sxs-lookup"><span data-stu-id="e5e09-122">This code sample builds the assembly csman_an_assembly, referencing the previously-built assembly and .netmodule.</span></span>  
  
```csharp  
// csman_an_assembly.cs  
// compile with: -addmodule:moduleassemblyname_2.netmodule -reference:moduleassemblyname_1.dll  
class A {  
    public static void Main() {  
        B bb = new B();  
        bb.Test();  
    }  
}  
```  
  
<span data-ttu-id="e5e09-123">**Вызывается An_Internal_Class.Test**</span><span class="sxs-lookup"><span data-stu-id="e5e09-123">**An_Internal_Class.Test called**</span></span>

## <a name="see-also"></a><span data-ttu-id="e5e09-124">См. также</span><span class="sxs-lookup"><span data-stu-id="e5e09-124">See also</span></span>

- [<span data-ttu-id="e5e09-125">Параметры компилятора C# </span><span class="sxs-lookup"><span data-stu-id="e5e09-125">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="e5e09-126">Управление свойствами проектов и решений</span><span class="sxs-lookup"><span data-stu-id="e5e09-126">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
