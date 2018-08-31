---
title: -moduleassemblyname
ms.date: 03/13/2018
helpviewer_keywords:
- moduleassemblyname compiler option [Visual Basic]
- /moduleassemblyname compiler option [Visual Basic]
- -moduleassemblyname compiler option [Visual Basic]
ms.assetid: 013a57b6-f425-4dd3-b333-512d72c42f55
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 479f9f639548eb81351d1df3f8f08b29b393cba1
ms.sourcegitcommit: fe02afbc39e78afd78cc6050e4a9c12a75f579f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/30/2018
ms.locfileid: "43257253"
---
# <a name="-moduleassemblyname"></a><span data-ttu-id="ed4bd-102">-moduleassemblyname</span><span class="sxs-lookup"><span data-stu-id="ed4bd-102">-moduleassemblyname</span></span>
<span data-ttu-id="ed4bd-103">Задает имя сборки, частью которой будет этот модуль.</span><span class="sxs-lookup"><span data-stu-id="ed4bd-103">Specifies the name of the assembly that this module will be a part of.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ed4bd-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ed4bd-104">Syntax</span></span>  
  
```  
-moduleassemblyname:assembly_name  
```  
  
## <a name="arguments"></a><span data-ttu-id="ed4bd-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="ed4bd-105">Arguments</span></span>  
  
|<span data-ttu-id="ed4bd-106">Термин</span><span class="sxs-lookup"><span data-stu-id="ed4bd-106">Term</span></span>|<span data-ttu-id="ed4bd-107">Определение</span><span class="sxs-lookup"><span data-stu-id="ed4bd-107">Definition</span></span>|  
|---|---|  
|`assembly_name`|<span data-ttu-id="ed4bd-108">Имя сборки, которая будет частью данный модуль.</span><span class="sxs-lookup"><span data-stu-id="ed4bd-108">The name of the assembly that this module will be a part of.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ed4bd-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="ed4bd-109">Remarks</span></span>  
 <span data-ttu-id="ed4bd-110">Компилятор выполняет `-moduleassemblyname` только если параметр `-target:module` был указан параметр.</span><span class="sxs-lookup"><span data-stu-id="ed4bd-110">The compiler processes the `-moduleassemblyname` option only if the `-target:module` option has been specified.</span></span> <span data-ttu-id="ed4bd-111">В этом случае компилятор для создания модуля.</span><span class="sxs-lookup"><span data-stu-id="ed4bd-111">This causes the compiler to create a module.</span></span> <span data-ttu-id="ed4bd-112">Модуль, созданный компилятором допустим только для сборки, указанной в `-moduleassemblyname` параметр.</span><span class="sxs-lookup"><span data-stu-id="ed4bd-112">The module created by the compiler is valid only for the assembly specified with the `-moduleassemblyname` option.</span></span> <span data-ttu-id="ed4bd-113">Если вы поместите модуль в другой сборке, возникнут ошибки времени выполнения.</span><span class="sxs-lookup"><span data-stu-id="ed4bd-113">If you place the module in a different assembly, run-time errors will occur.</span></span>  
  
 <span data-ttu-id="ed4bd-114">`-moduleassemblyname` Параметр требуется только в том случае, при выполнении следующих условий:</span><span class="sxs-lookup"><span data-stu-id="ed4bd-114">The `-moduleassemblyname` option is needed only when the following are true:</span></span>  
  
-   <span data-ttu-id="ed4bd-115">Тип данных в модуле необходим доступ к `Friend` тип в сборке, на которую указывает ссылка.</span><span class="sxs-lookup"><span data-stu-id="ed4bd-115">A data type in the module needs access to a `Friend` type in a referenced assembly.</span></span>  
  
-   <span data-ttu-id="ed4bd-116">Свойства ссылки был предоставлен доступ к дружественной сборке на сборку, в которую будет встроен модуль.</span><span class="sxs-lookup"><span data-stu-id="ed4bd-116">The referenced assembly has granted friend assembly access to the assembly into which the module will be built.</span></span>  
  
 <span data-ttu-id="ed4bd-117">Дополнительные сведения о создании модуля см. в разделе [/Target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md).</span><span class="sxs-lookup"><span data-stu-id="ed4bd-117">For more information about creating a module, see [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md).</span></span> <span data-ttu-id="ed4bd-118">Дополнительные сведения о дружественных сборок, см. в разделе [дружественных сборок](../../programming-guide/concepts/assemblies-gac/friend-assemblies.md).</span><span class="sxs-lookup"><span data-stu-id="ed4bd-118">For more information about friend assemblies, see [Friend Assemblies](../../programming-guide/concepts/assemblies-gac/friend-assemblies.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ed4bd-119">`-moduleassemblyname` Не доступна из среды разработки Visual Studio; она доступна только при компиляции из командной строки.</span><span class="sxs-lookup"><span data-stu-id="ed4bd-119">The `-moduleassemblyname` option is not available from within the Visual Studio development environment; it is available only when you compile from a command prompt.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed4bd-120">См. также</span><span class="sxs-lookup"><span data-stu-id="ed4bd-120">See Also</span></span>  
 [<span data-ttu-id="ed4bd-121">Практическое руководство. Создание многофайловой сборки</span><span class="sxs-lookup"><span data-stu-id="ed4bd-121">How to: Build a Multifile Assembly</span></span>](../../../framework/app-domains/how-to-build-a-multifile-assembly.md)  
 [<span data-ttu-id="ed4bd-122">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="ed4bd-122">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="ed4bd-123">-target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ed4bd-123">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)  
 [<span data-ttu-id="ed4bd-124">-main</span><span class="sxs-lookup"><span data-stu-id="ed4bd-124">-main</span></span>](../../../visual-basic/reference/command-line-compiler/main.md)  
 [<span data-ttu-id="ed4bd-125">-ссылке (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ed4bd-125">-reference (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/reference.md)  
 [<span data-ttu-id="ed4bd-126">-addmodule</span><span class="sxs-lookup"><span data-stu-id="ed4bd-126">-addmodule</span></span>](../../../visual-basic/reference/command-line-compiler/addmodule.md)  
 [<span data-ttu-id="ed4bd-127">Сборки и глобальный кэш сборок</span><span class="sxs-lookup"><span data-stu-id="ed4bd-127">Assemblies and the Global Assembly Cache</span></span>](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)  
 [<span data-ttu-id="ed4bd-128">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="ed4bd-128">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [<span data-ttu-id="ed4bd-129">Дружественные сборки</span><span class="sxs-lookup"><span data-stu-id="ed4bd-129">Friend Assemblies</span></span>](../../programming-guide/concepts/assemblies-gac/friend-assemblies.md)
