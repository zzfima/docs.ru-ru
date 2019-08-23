---
title: -moduleassemblyname
ms.date: 03/13/2018
helpviewer_keywords:
- moduleassemblyname compiler option [Visual Basic]
- /moduleassemblyname compiler option [Visual Basic]
- -moduleassemblyname compiler option [Visual Basic]
ms.assetid: 013a57b6-f425-4dd3-b333-512d72c42f55
ms.openlocfilehash: 052d6937846df39bd94d532e1b63ebe522dbf6c7
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964680"
---
# <a name="-moduleassemblyname"></a><span data-ttu-id="63dcc-102">-moduleassemblyname</span><span class="sxs-lookup"><span data-stu-id="63dcc-102">-moduleassemblyname</span></span>
<span data-ttu-id="63dcc-103">Задает имя сборки, частью которой будет этот модуль.</span><span class="sxs-lookup"><span data-stu-id="63dcc-103">Specifies the name of the assembly that this module will be a part of.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="63dcc-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="63dcc-104">Syntax</span></span>  
  
```  
-moduleassemblyname:assembly_name  
```  
  
## <a name="arguments"></a><span data-ttu-id="63dcc-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="63dcc-105">Arguments</span></span>  
  
|<span data-ttu-id="63dcc-106">Термин</span><span class="sxs-lookup"><span data-stu-id="63dcc-106">Term</span></span>|<span data-ttu-id="63dcc-107">Определение</span><span class="sxs-lookup"><span data-stu-id="63dcc-107">Definition</span></span>|  
|---|---|  
|`assembly_name`|<span data-ttu-id="63dcc-108">Имя сборки, частью которой будет этот модуль.</span><span class="sxs-lookup"><span data-stu-id="63dcc-108">The name of the assembly that this module will be a part of.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="63dcc-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="63dcc-109">Remarks</span></span>  
 <span data-ttu-id="63dcc-110">Компилятор обрабатывает `-moduleassemblyname` параметр, только `-target:module` если указан параметр.</span><span class="sxs-lookup"><span data-stu-id="63dcc-110">The compiler processes the `-moduleassemblyname` option only if the `-target:module` option has been specified.</span></span> <span data-ttu-id="63dcc-111">В результате компилятор создаст модуль.</span><span class="sxs-lookup"><span data-stu-id="63dcc-111">This causes the compiler to create a module.</span></span> <span data-ttu-id="63dcc-112">Модуль, созданный компилятором, действителен только для сборки, указанной с помощью `-moduleassemblyname` параметра.</span><span class="sxs-lookup"><span data-stu-id="63dcc-112">The module created by the compiler is valid only for the assembly specified with the `-moduleassemblyname` option.</span></span> <span data-ttu-id="63dcc-113">Если модуль размещается в другой сборке, возникнут ошибки во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="63dcc-113">If you place the module in a different assembly, run-time errors will occur.</span></span>  
  
 <span data-ttu-id="63dcc-114">Этот `-moduleassemblyname` параметр необходим только в том случае, если выполняются следующие условия.</span><span class="sxs-lookup"><span data-stu-id="63dcc-114">The `-moduleassemblyname` option is needed only when the following are true:</span></span>  
  
- <span data-ttu-id="63dcc-115">Для типа данных в модуле требуется доступ к `Friend` типу в сборке, на которую имеется ссылка.</span><span class="sxs-lookup"><span data-stu-id="63dcc-115">A data type in the module needs access to a `Friend` type in a referenced assembly.</span></span>  
  
- <span data-ttu-id="63dcc-116">Сборка, на которую указывает ссылка, предоставила дружественной сборке доступ к сборке, в которую будет построен модуль.</span><span class="sxs-lookup"><span data-stu-id="63dcc-116">The referenced assembly has granted friend assembly access to the assembly into which the module will be built.</span></span>  
  
 <span data-ttu-id="63dcc-117">Дополнительные сведения о создании модуля см. в разделе [/Target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md).</span><span class="sxs-lookup"><span data-stu-id="63dcc-117">For more information about creating a module, see [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md).</span></span> <span data-ttu-id="63dcc-118">Дополнительные сведения о дружественных сборках см. в разделе [дружественные сборки](../../../standard/assembly/friend-assemblies.md).</span><span class="sxs-lookup"><span data-stu-id="63dcc-118">For more information about friend assemblies, see [Friend Assemblies](../../../standard/assembly/friend-assemblies.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="63dcc-119">Этот `-moduleassemblyname` параметр недоступен в среде разработки Visual Studio. он доступен только при компиляции из командной строки.</span><span class="sxs-lookup"><span data-stu-id="63dcc-119">The `-moduleassemblyname` option is not available from within the Visual Studio development environment; it is available only when you compile from a command prompt.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63dcc-120">См. также</span><span class="sxs-lookup"><span data-stu-id="63dcc-120">See also</span></span>

- [<span data-ttu-id="63dcc-121">Практическое руководство. Создание многофайловой сборки</span><span class="sxs-lookup"><span data-stu-id="63dcc-121">How to: Build a Multifile Assembly</span></span>](../../../framework/app-domains/how-to-build-a-multifile-assembly.md)
- [<span data-ttu-id="63dcc-122">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="63dcc-122">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="63dcc-123">-Target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="63dcc-123">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)
- [<span data-ttu-id="63dcc-124">-main</span><span class="sxs-lookup"><span data-stu-id="63dcc-124">-main</span></span>](../../../visual-basic/reference/command-line-compiler/main.md)
- [<span data-ttu-id="63dcc-125">-Reference (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="63dcc-125">-reference (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/reference.md)
- [<span data-ttu-id="63dcc-126">-addmodule</span><span class="sxs-lookup"><span data-stu-id="63dcc-126">-addmodule</span></span>](../../../visual-basic/reference/command-line-compiler/addmodule.md)
- [<span data-ttu-id="63dcc-127">Сборки в .NET</span><span class="sxs-lookup"><span data-stu-id="63dcc-127">Assemblies in .NET</span></span>](../../../standard/assembly/index.md)
- [<span data-ttu-id="63dcc-128">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="63dcc-128">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="63dcc-129">Дружественные сборки</span><span class="sxs-lookup"><span data-stu-id="63dcc-129">Friend Assemblies</span></span>](../../../standard/assembly/friend-assemblies.md)
