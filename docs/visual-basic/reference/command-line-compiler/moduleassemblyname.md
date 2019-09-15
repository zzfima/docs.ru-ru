---
title: -moduleassemblyname
ms.date: 03/13/2018
helpviewer_keywords:
- moduleassemblyname compiler option [Visual Basic]
- /moduleassemblyname compiler option [Visual Basic]
- -moduleassemblyname compiler option [Visual Basic]
ms.assetid: 013a57b6-f425-4dd3-b333-512d72c42f55
ms.openlocfilehash: dc4c0336c8a67a1b4e70f71ba5f5406da1fbb2ff
ms.sourcegitcommit: 7b1ce327e8c84f115f007be4728d29a89efe11ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/13/2019
ms.locfileid: "70972378"
---
# <a name="-moduleassemblyname"></a><span data-ttu-id="cd50a-102">-moduleassemblyname</span><span class="sxs-lookup"><span data-stu-id="cd50a-102">-moduleassemblyname</span></span>
<span data-ttu-id="cd50a-103">Задает имя сборки, частью которой будет этот модуль.</span><span class="sxs-lookup"><span data-stu-id="cd50a-103">Specifies the name of the assembly that this module will be a part of.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cd50a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cd50a-104">Syntax</span></span>  
  
```  
-moduleassemblyname:assembly_name  
```  
  
## <a name="arguments"></a><span data-ttu-id="cd50a-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="cd50a-105">Arguments</span></span>  
  
|<span data-ttu-id="cd50a-106">Термин</span><span class="sxs-lookup"><span data-stu-id="cd50a-106">Term</span></span>|<span data-ttu-id="cd50a-107">Определение</span><span class="sxs-lookup"><span data-stu-id="cd50a-107">Definition</span></span>|  
|---|---|  
|`assembly_name`|<span data-ttu-id="cd50a-108">Имя сборки, частью которой будет этот модуль.</span><span class="sxs-lookup"><span data-stu-id="cd50a-108">The name of the assembly that this module will be a part of.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cd50a-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="cd50a-109">Remarks</span></span>  
 <span data-ttu-id="cd50a-110">Компилятор обрабатывает `-moduleassemblyname` параметр, только `-target:module` если указан параметр.</span><span class="sxs-lookup"><span data-stu-id="cd50a-110">The compiler processes the `-moduleassemblyname` option only if the `-target:module` option has been specified.</span></span> <span data-ttu-id="cd50a-111">В результате компилятор создаст модуль.</span><span class="sxs-lookup"><span data-stu-id="cd50a-111">This causes the compiler to create a module.</span></span> <span data-ttu-id="cd50a-112">Модуль, созданный компилятором, действителен только для сборки, указанной с помощью `-moduleassemblyname` параметра.</span><span class="sxs-lookup"><span data-stu-id="cd50a-112">The module created by the compiler is valid only for the assembly specified with the `-moduleassemblyname` option.</span></span> <span data-ttu-id="cd50a-113">Если модуль размещается в другой сборке, возникнут ошибки во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="cd50a-113">If you place the module in a different assembly, run-time errors will occur.</span></span>  
  
 <span data-ttu-id="cd50a-114">Этот `-moduleassemblyname` параметр необходим только в том случае, если выполняются следующие условия.</span><span class="sxs-lookup"><span data-stu-id="cd50a-114">The `-moduleassemblyname` option is needed only when the following are true:</span></span>  
  
- <span data-ttu-id="cd50a-115">Для типа данных в модуле требуется доступ к `Friend` типу в сборке, на которую имеется ссылка.</span><span class="sxs-lookup"><span data-stu-id="cd50a-115">A data type in the module needs access to a `Friend` type in a referenced assembly.</span></span>  
  
- <span data-ttu-id="cd50a-116">Сборка, на которую указывает ссылка, предоставила дружественной сборке доступ к сборке, в которую будет построен модуль.</span><span class="sxs-lookup"><span data-stu-id="cd50a-116">The referenced assembly has granted friend assembly access to the assembly into which the module will be built.</span></span>  
  
 <span data-ttu-id="cd50a-117">Дополнительные сведения о создании модуля см. в разделе [/Target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md).</span><span class="sxs-lookup"><span data-stu-id="cd50a-117">For more information about creating a module, see [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md).</span></span> <span data-ttu-id="cd50a-118">Дополнительные сведения о дружественных сборках см. в разделе [дружественные сборки](../../../standard/assembly/friend.md).</span><span class="sxs-lookup"><span data-stu-id="cd50a-118">For more information about friend assemblies, see [Friend Assemblies](../../../standard/assembly/friend.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="cd50a-119">Этот `-moduleassemblyname` параметр недоступен в среде разработки Visual Studio. он доступен только при компиляции из командной строки.</span><span class="sxs-lookup"><span data-stu-id="cd50a-119">The `-moduleassemblyname` option is not available from within the Visual Studio development environment; it is available only when you compile from a command prompt.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd50a-120">См. также</span><span class="sxs-lookup"><span data-stu-id="cd50a-120">See also</span></span>

- [<span data-ttu-id="cd50a-121">Практическое руководство. Создание многофайловой сборки</span><span class="sxs-lookup"><span data-stu-id="cd50a-121">How to: Build a Multifile Assembly</span></span>](../../../framework/app-domains/build-multifile-assembly.md)
- [<span data-ttu-id="cd50a-122">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="cd50a-122">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="cd50a-123">-Target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cd50a-123">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)
- [<span data-ttu-id="cd50a-124">-main</span><span class="sxs-lookup"><span data-stu-id="cd50a-124">-main</span></span>](../../../visual-basic/reference/command-line-compiler/main.md)
- [<span data-ttu-id="cd50a-125">-Reference (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cd50a-125">-reference (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/reference.md)
- [<span data-ttu-id="cd50a-126">-addmodule</span><span class="sxs-lookup"><span data-stu-id="cd50a-126">-addmodule</span></span>](../../../visual-basic/reference/command-line-compiler/addmodule.md)
- [<span data-ttu-id="cd50a-127">Сборки в .NET</span><span class="sxs-lookup"><span data-stu-id="cd50a-127">Assemblies in .NET</span></span>](../../../standard/assembly/index.md)
- [<span data-ttu-id="cd50a-128">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="cd50a-128">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="cd50a-129">Дружественные сборки</span><span class="sxs-lookup"><span data-stu-id="cd50a-129">Friend Assemblies</span></span>](../../../standard/assembly/friend.md)
