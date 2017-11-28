---
title: "-moduleassemblyname (параметры компилятора C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: /moduleassemblyname
helpviewer_keywords:
- moduleassemblyname compiler option [C#]
- /moduleassemblyname compiler option [C#]
- .moduleassemblyname compiler option [C#]
ms.assetid: d464d9b9-f18d-423b-95e9-66c7878fd53a
caps.latest.revision: "10"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: c8ebd6f7498adead4586c9e90ec58ca8efe81aaa
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="moduleassemblyname-c-compiler-option"></a><span data-ttu-id="eea07-102">/moduleassemblyname (параметры компилятора C#)</span><span class="sxs-lookup"><span data-stu-id="eea07-102">/moduleassemblyname (C# Compiler Option)</span></span>
<span data-ttu-id="eea07-103">Указывает сборку, к неоткрытым типам которой может обращаться .netmodule.</span><span class="sxs-lookup"><span data-stu-id="eea07-103">Specifies an assembly whose non-public types a .netmodule can access.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eea07-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="eea07-104">Syntax</span></span>  
  
```console  
/moduleassemblyname:assembly_name  
```  
  
## <a name="arguments"></a><span data-ttu-id="eea07-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="eea07-105">Arguments</span></span>  
 `assembly_name`  
 <span data-ttu-id="eea07-106">Имя сборки, к неоткрытым типам которой может обращаться .netmodule.</span><span class="sxs-lookup"><span data-stu-id="eea07-106">The name of the assembly whose non-public types the .netmodule can access.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="eea07-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="eea07-107">Remarks</span></span>  
 <span data-ttu-id="eea07-108">Параметр **/moduleassemblyname** должен использоваться при построении .netmodule и выполнении следующий условий:</span><span class="sxs-lookup"><span data-stu-id="eea07-108">**/moduleassemblyname** should be used when building a .netmodule, and where the following conditions are true:</span></span>  
  
-   <span data-ttu-id="eea07-109">.netmodule требуется доступ к неоткрытым типам в существующей сборке.</span><span class="sxs-lookup"><span data-stu-id="eea07-109">The .netmodule needs access to non-public types in an existing assembly.</span></span>  
  
-   <span data-ttu-id="eea07-110">Известно имя сборки, в которой будет создан .netmodule.</span><span class="sxs-lookup"><span data-stu-id="eea07-110">You know the name of the assembly into which the .netmodule will be built.</span></span>  
  
-   <span data-ttu-id="eea07-111">Существующая сборка предоставила дружественной сборке доступ к сборке, в которую будет встроен .netmodule.</span><span class="sxs-lookup"><span data-stu-id="eea07-111">The existing assembly has granted friend assembly access to the assembly into which the .netmodule will be built.</span></span>  
  
 <span data-ttu-id="eea07-112">Дополнительные сведения о построении файлов .netmodule см. в разделе [/target:module (параметры компилятора C#)](../../../csharp/language-reference/compiler-options/target-module-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="eea07-112">For more information on building a .netmodule, see [/target:module (C# Compiler Options)](../../../csharp/language-reference/compiler-options/target-module-compiler-option.md).</span></span>  
  
 <span data-ttu-id="eea07-113">Дополнительные сведения см. в разделе [Дружественные сборки](../../programming-guide/concepts/assemblies-gac/friend-assemblies.md).</span><span class="sxs-lookup"><span data-stu-id="eea07-113">For more information on friend assemblies, see [Friend Assemblies](../../programming-guide/concepts/assemblies-gac/friend-assemblies.md).</span></span>  
  
 <span data-ttu-id="eea07-114">Этот параметр недоступен в среде разработки и может использоваться только при компиляции из командной строки.</span><span class="sxs-lookup"><span data-stu-id="eea07-114">This option is not available from within the development environment; it is only available when compiling from the command line.</span></span>  
  
 <span data-ttu-id="eea07-115">Этот параметр компилятора недоступен в Visual Studio и не может быть изменен программным способом.</span><span class="sxs-lookup"><span data-stu-id="eea07-115">This compiler option is unavailable in Visual Studio and cannot be changed programmatically.</span></span>  
  
## <a name="example"></a><span data-ttu-id="eea07-116">Пример</span><span class="sxs-lookup"><span data-stu-id="eea07-116">Example</span></span>  
 <span data-ttu-id="eea07-117">В этом примере выполняется построение сборки частного типа, которой предоставляется дружественный доступ к сборке csman_an_assembly.</span><span class="sxs-lookup"><span data-stu-id="eea07-117">This sample builds an assembly with a private type, and that gives friend assembly access to an assembly called csman_an_assembly.</span></span>  
  
```csharp  
// moduleassemblyname_1.cs  
// compile with: /target:library  
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
  
## <a name="example"></a><span data-ttu-id="eea07-118">Пример</span><span class="sxs-lookup"><span data-stu-id="eea07-118">Example</span></span>  
 <span data-ttu-id="eea07-119">Этот пример строит .netmodule, который обращается к неоткрытому типу в сборке moduleassemblyname_1.dll.</span><span class="sxs-lookup"><span data-stu-id="eea07-119">This sample builds a .netmodule that accesses a non-public type in the assembly moduleassemblyname_1.dll.</span></span> <span data-ttu-id="eea07-120">Мы знаем, что .netmodule будет встроен в сборку csman_an_assembly, поэтому можем задать **/moduleassemblyname**, чтобы позволить .netmodule обращаться к неоткрытым типам в сборке, которой предоставлен доступ к дружественной сборке csman_an_assembly.</span><span class="sxs-lookup"><span data-stu-id="eea07-120">By knowing that this .netmodule will be built into an assembly called csman_an_assembly, we can specify **/moduleassemblyname**, allowing the .netmodule to access non-public types in an assembly that has granted friend assembly access to csman_an_assembly.</span></span>  
  
```csharp  
// moduleassemblyname_2.cs  
// compile with: /moduleassemblyname:csman_an_assembly /target:module /reference:moduleassemblyname_1.dll  
class B {  
    public void Test() {  
        An_Internal_Class x = new An_Internal_Class();  
        x.Test();  
    }  
}  
```  
  
## <a name="example"></a><span data-ttu-id="eea07-121">Пример</span><span class="sxs-lookup"><span data-stu-id="eea07-121">Example</span></span>  
 <span data-ttu-id="eea07-122">В следующем примере кода выполнено построение сборки csman_an_assembly со ссылками на ранее построенную сборку и .netmodule.</span><span class="sxs-lookup"><span data-stu-id="eea07-122">This code sample builds the assembly csman_an_assembly, referencing the previously-built assembly and .netmodule.</span></span>  
  
```csharp  
// csman_an_assembly.cs  
// compile with: /addmodule:moduleassemblyname_2.netmodule /reference:moduleassemblyname_1.dll  
class A {  
    public static void Main() {  
        B bb = new B();  
        bb.Test();  
    }  
}  
```  
  
 <span data-ttu-id="eea07-123">**Вызывается An_Internal_Class.Test**</span><span class="sxs-lookup"><span data-stu-id="eea07-123">**An_Internal_Class.Test called**</span></span>  
## <a name="see-also"></a><span data-ttu-id="eea07-124">См. также</span><span class="sxs-lookup"><span data-stu-id="eea07-124">See Also</span></span>  
 [<span data-ttu-id="eea07-125">Параметры компилятора C# </span><span class="sxs-lookup"><span data-stu-id="eea07-125">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)  
 [<span data-ttu-id="eea07-126">Управление свойствами проектов и решений</span><span class="sxs-lookup"><span data-stu-id="eea07-126">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
