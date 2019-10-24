---
title: -highentropyva (Visual Basic)
ms.date: 03/10/2018
helpviewer_keywords:
- highentropyva compiler option (Visual Basic)
- /highentropyva compiler option (Visual Basic)
ms.assetid: ff25f20a-6ca2-467b-9e52-5cf439f5028e
ms.openlocfilehash: 203380bbe2b2828e159ee36d795b6cd4a24e2917
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/22/2019
ms.locfileid: "72775659"
---
# <a name="-highentropyva-visual-basic"></a><span data-ttu-id="c519a-102">-highentropyva (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c519a-102">-highentropyva (Visual Basic)</span></span>
<span data-ttu-id="c519a-103">Указывает, является ли 64-разрядный исполняемый файл или исполняемый файл, помеченный параметром компилятора [-Platform: anycpu](../../../visual-basic/reference/command-line-compiler/platform.md) , поддержкой случайного расположения макета адресного пространства (ASLR) с высокой энтропией.</span><span class="sxs-lookup"><span data-stu-id="c519a-103">Indicates whether a 64-bit executable or an executable that's marked by the [-platform:anycpu](../../../visual-basic/reference/command-line-compiler/platform.md) compiler option supports high entropy Address Space Layout Randomization (ASLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c519a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c519a-104">Syntax</span></span>  
  
```console  
-highentropyva[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="c519a-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="c519a-105">Arguments</span></span>  
 <span data-ttu-id="c519a-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="c519a-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="c519a-107">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="c519a-107">Optional.</span></span> <span data-ttu-id="c519a-108">Параметр отключен по умолчанию или при указании `-highentropyva-`.</span><span class="sxs-lookup"><span data-stu-id="c519a-108">The option is off by default or if you specify `-highentropyva-`.</span></span> <span data-ttu-id="c519a-109">Параметр включен, если вы указываете `-highentropyva` или `-highentropyva+`.</span><span class="sxs-lookup"><span data-stu-id="c519a-109">The option is on if you specify `-highentropyva` or `-highentropyva+`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c519a-110">Заметки</span><span class="sxs-lookup"><span data-stu-id="c519a-110">Remarks</span></span>  
 <span data-ttu-id="c519a-111">Если указан этот параметр, совместимые версии ядра Windows могут использовать более высокие уровни энтропии, когда ядро случайным образом разметка адресного пространства процесса в рамках ASLR.</span><span class="sxs-lookup"><span data-stu-id="c519a-111">If you specify this option, compatible versions of the Windows kernel can use higher degrees of entropy when the kernel randomizes the address space layout of a process as part of ASLR.</span></span> <span data-ttu-id="c519a-112">Если ядро использует более высокие степени энтропии, то для областей памяти, таких как стеки и кучи, можно выделить большее количество адресов.</span><span class="sxs-lookup"><span data-stu-id="c519a-112">If the kernel uses higher degrees of entropy, a larger number of addresses can be allocated to memory regions such as stacks and heaps.</span></span> <span data-ttu-id="c519a-113">Из-за этого сложнее подобрать расположение определенной области памяти.</span><span class="sxs-lookup"><span data-stu-id="c519a-113">As a result, it is more difficult to guess the location of a particular memory region.</span></span>  
  
 <span data-ttu-id="c519a-114">Если параметр включен, целевой исполняемый файл и все модули, от которых он зависит, должны иметь возможность обрабатывать значения указателя, превышающие 4 гигабайта (ГБ), если эти модули работают как 64-разрядные процессы.</span><span class="sxs-lookup"><span data-stu-id="c519a-114">When the option is on, the target executable and any modules on which it depends must be able to handle pointer values that are larger than 4 gigabytes (GB) when those modules are running as 64-bit processes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c519a-115">См. также</span><span class="sxs-lookup"><span data-stu-id="c519a-115">See also</span></span>

- [<span data-ttu-id="c519a-116">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="c519a-116">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="c519a-117">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="c519a-117">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
