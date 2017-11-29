---
title: /highentropyva (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- highentropyva compiler option (Visual Basic)
- /highentropyva compiler option (Visual Basic)
ms.assetid: ff25f20a-6ca2-467b-9e52-5cf439f5028e
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 55568808bb94f98ce7a20016fc5a2a0a2ef23a38
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="highentropyva-visual-basic"></a><span data-ttu-id="376e6-102">/highentropyva (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="376e6-102">/highentropyva (Visual Basic)</span></span>
<span data-ttu-id="376e6-103">Указывает, 64-разрядный исполняемый файл или исполняемый файл, помеченный атрибутом [/Platform: anycpu](../../../visual-basic/reference/command-line-compiler/platform.md) параметр компилятора поддерживает технологию Address Space макета Randomization (ASLR) с высокой энтропией.</span><span class="sxs-lookup"><span data-stu-id="376e6-103">Indicates whether a 64-bit executable or an executable that's marked by the [/platform:anycpu](../../../visual-basic/reference/command-line-compiler/platform.md) compiler option supports high entropy Address Space Layout Randomization (ASLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="376e6-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="376e6-104">Syntax</span></span>  
  
```  
/highentropyva[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="376e6-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="376e6-105">Arguments</span></span>  
 <span data-ttu-id="376e6-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="376e6-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="376e6-107">Необязательно.</span><span class="sxs-lookup"><span data-stu-id="376e6-107">Optional.</span></span> <span data-ttu-id="376e6-108">Параметр отключен по умолчанию или при указании `/highentropyva-`.</span><span class="sxs-lookup"><span data-stu-id="376e6-108">The option is off by default or if you specify `/highentropyva-`.</span></span> <span data-ttu-id="376e6-109">Параметр — Если указать `/highentropyva` или `/highentropyva+`.</span><span class="sxs-lookup"><span data-stu-id="376e6-109">The option is on if you specify `/highentropyva` or `/highentropyva+`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="376e6-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="376e6-110">Remarks</span></span>  
 <span data-ttu-id="376e6-111">Если этот параметр указан, совместимые версии ядра Windows можно использовать более высокие степени энтропии при ядра случайный выбор из своего структуры адресного пространства процесса в рамках ASLR.</span><span class="sxs-lookup"><span data-stu-id="376e6-111">If you specify this option, compatible versions of the Windows kernel can use higher degrees of entropy when the kernel randomizes the address space layout of a process as part of ASLR.</span></span> <span data-ttu-id="376e6-112">Если ядро использует более высоких степеней энтропии, можно выделить больше адресов областей памяти как стеки и кучи.</span><span class="sxs-lookup"><span data-stu-id="376e6-112">If the kernel uses higher degrees of entropy, a larger number of addresses can be allocated to memory regions such as stacks and heaps.</span></span> <span data-ttu-id="376e6-113">Из-за этого сложнее подобрать расположение определенной области памяти.</span><span class="sxs-lookup"><span data-stu-id="376e6-113">As a result, it is more difficult to guess the location of a particular memory region.</span></span>  
  
 <span data-ttu-id="376e6-114">Когда включен этот параметр, целевой исполняемый файл и модули, на которых она зависит необходимо обработать значения указателя, размер которых превышает 4 гигабайта (ГБ), когда эти модули выполняются как 64-разрядные процессы.</span><span class="sxs-lookup"><span data-stu-id="376e6-114">When the option is on, the target executable and any modules on which it depends must be able to handle pointer values that are larger than 4 gigabytes (GB) when those modules are running as 64-bit processes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="376e6-115">См. также</span><span class="sxs-lookup"><span data-stu-id="376e6-115">See Also</span></span>  
 [<span data-ttu-id="376e6-116">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="376e6-116">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="376e6-117">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="376e6-117">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
