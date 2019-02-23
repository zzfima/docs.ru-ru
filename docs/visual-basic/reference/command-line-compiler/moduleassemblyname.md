---
title: -moduleassemblyname
ms.date: 03/13/2018
helpviewer_keywords:
- moduleassemblyname compiler option [Visual Basic]
- /moduleassemblyname compiler option [Visual Basic]
- -moduleassemblyname compiler option [Visual Basic]
ms.assetid: 013a57b6-f425-4dd3-b333-512d72c42f55
ms.openlocfilehash: f88a0001bb2ba55c0a3eac3ed208f14292d86734
ms.sourcegitcommit: 8f95d3a37e591963ebbb9af6e90686fd5f3b8707
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2019
ms.locfileid: "56745668"
---
# <a name="-moduleassemblyname"></a><span data-ttu-id="fb927-102">-moduleassemblyname</span><span class="sxs-lookup"><span data-stu-id="fb927-102">-moduleassemblyname</span></span>
<span data-ttu-id="fb927-103">Задает имя сборки, частью которой будет этот модуль.</span><span class="sxs-lookup"><span data-stu-id="fb927-103">Specifies the name of the assembly that this module will be a part of.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fb927-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fb927-104">Syntax</span></span>  
  
```  
-moduleassemblyname:assembly_name  
```  
  
## <a name="arguments"></a><span data-ttu-id="fb927-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="fb927-105">Arguments</span></span>  
  
|<span data-ttu-id="fb927-106">Термин</span><span class="sxs-lookup"><span data-stu-id="fb927-106">Term</span></span>|<span data-ttu-id="fb927-107">Определение</span><span class="sxs-lookup"><span data-stu-id="fb927-107">Definition</span></span>|  
|---|---|  
|`assembly_name`|<span data-ttu-id="fb927-108">Имя сборки, которая будет частью данный модуль.</span><span class="sxs-lookup"><span data-stu-id="fb927-108">The name of the assembly that this module will be a part of.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fb927-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="fb927-109">Remarks</span></span>  
 <span data-ttu-id="fb927-110">Компилятор выполняет `-moduleassemblyname` только если параметр `-target:module` был указан параметр.</span><span class="sxs-lookup"><span data-stu-id="fb927-110">The compiler processes the `-moduleassemblyname` option only if the `-target:module` option has been specified.</span></span> <span data-ttu-id="fb927-111">В этом случае компилятор для создания модуля.</span><span class="sxs-lookup"><span data-stu-id="fb927-111">This causes the compiler to create a module.</span></span> <span data-ttu-id="fb927-112">Модуль, созданный компилятором допустим только для сборки, указанной в `-moduleassemblyname` параметр.</span><span class="sxs-lookup"><span data-stu-id="fb927-112">The module created by the compiler is valid only for the assembly specified with the `-moduleassemblyname` option.</span></span> <span data-ttu-id="fb927-113">Если вы поместите модуль в другой сборке, возникнут ошибки времени выполнения.</span><span class="sxs-lookup"><span data-stu-id="fb927-113">If you place the module in a different assembly, run-time errors will occur.</span></span>  
  
 <span data-ttu-id="fb927-114">`-moduleassemblyname` Параметр требуется только в том случае, при выполнении следующих условий:</span><span class="sxs-lookup"><span data-stu-id="fb927-114">The `-moduleassemblyname` option is needed only when the following are true:</span></span>  
  
-   <span data-ttu-id="fb927-115">Тип данных в модуле необходим доступ к `Friend` тип в сборке, на которую указывает ссылка.</span><span class="sxs-lookup"><span data-stu-id="fb927-115">A data type in the module needs access to a `Friend` type in a referenced assembly.</span></span>  
  
-   <span data-ttu-id="fb927-116">Свойства ссылки был предоставлен доступ к дружественной сборке на сборку, в которую будет встроен модуль.</span><span class="sxs-lookup"><span data-stu-id="fb927-116">The referenced assembly has granted friend assembly access to the assembly into which the module will be built.</span></span>  
  
 <span data-ttu-id="fb927-117">Дополнительные сведения о создании модуля см. в разделе [/Target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md).</span><span class="sxs-lookup"><span data-stu-id="fb927-117">For more information about creating a module, see [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md).</span></span> <span data-ttu-id="fb927-118">Дополнительные сведения о дружественных сборок, см. в разделе [дружественных сборок](../../programming-guide/concepts/assemblies-gac/friend-assemblies.md).</span><span class="sxs-lookup"><span data-stu-id="fb927-118">For more information about friend assemblies, see [Friend Assemblies](../../programming-guide/concepts/assemblies-gac/friend-assemblies.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fb927-119">`-moduleassemblyname` Не доступна из среды разработки Visual Studio; она доступна только при компиляции из командной строки.</span><span class="sxs-lookup"><span data-stu-id="fb927-119">The `-moduleassemblyname` option is not available from within the Visual Studio development environment; it is available only when you compile from a command prompt.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb927-120">См. также</span><span class="sxs-lookup"><span data-stu-id="fb927-120">See also</span></span>
- [<span data-ttu-id="fb927-121">Практическое руководство. Создание многофайловой сборки</span><span class="sxs-lookup"><span data-stu-id="fb927-121">How to: Build a Multifile Assembly</span></span>](../../../framework/app-domains/how-to-build-a-multifile-assembly.md)
- [<span data-ttu-id="fb927-122">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="fb927-122">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="fb927-123">-target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fb927-123">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)
- [<span data-ttu-id="fb927-124">-main</span><span class="sxs-lookup"><span data-stu-id="fb927-124">-main</span></span>](../../../visual-basic/reference/command-line-compiler/main.md)
- [<span data-ttu-id="fb927-125">-ссылке (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fb927-125">-reference (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/reference.md)
- [<span data-ttu-id="fb927-126">-addmodule</span><span class="sxs-lookup"><span data-stu-id="fb927-126">-addmodule</span></span>](../../../visual-basic/reference/command-line-compiler/addmodule.md)
- [<span data-ttu-id="fb927-127">Сборки в .NET</span><span class="sxs-lookup"><span data-stu-id="fb927-127">Assemblies in .NET</span></span>](../../../standard/assembly/index.md)
- [<span data-ttu-id="fb927-128">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="fb927-128">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="fb927-129">Дружественные сборки</span><span class="sxs-lookup"><span data-stu-id="fb927-129">Friend Assemblies</span></span>](../../programming-guide/concepts/assemblies-gac/friend-assemblies.md)
