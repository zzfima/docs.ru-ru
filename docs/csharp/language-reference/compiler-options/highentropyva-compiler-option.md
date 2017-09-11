---
title: "-highentropyva (параметры компилятора C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /highentropyva
dev_langs:
- CSharp
helpviewer_keywords:
- /highentropyva compiler option [C#]
- -highentropyva compiler option [C#]
- highentropyva compiler option [C#]
ms.assetid: eaf409b3-384e-49dd-9417-62453658f421
caps.latest.revision: 8
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 4cb21c109fc33a30da016fd6a42285a3a3da02e2
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="highentropyva-c-compiler-options"></a><span data-ttu-id="2085b-102">/highentropyva (параметры компилятора C#)</span><span class="sxs-lookup"><span data-stu-id="2085b-102">/highentropyva (C# Compiler Options)</span></span>
<span data-ttu-id="2085b-103">Параметр компилятора **/highentropyva** сообщает ядру Windows, поддерживает ли указанный исполняемый файл технологию Address Space Layout Randomization (ASLR) с высокой энтропией.</span><span class="sxs-lookup"><span data-stu-id="2085b-103">The **/highentropyva** compiler option tells the Windows kernel whether a particular executable supports high entropy Address Space Layout Randomization (ASLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2085b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2085b-104">Syntax</span></span>  
  
```console  
/highentropyva[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="2085b-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="2085b-105">Arguments</span></span>  
 <span data-ttu-id="2085b-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="2085b-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="2085b-107">Этот параметр указывает, что 64-битный исполняемый файл или исполняемый файл, отмеченный параметром компилятора [/platform:anycpu](../../../csharp/language-reference/compiler-options/platform-compiler-option.md), поддерживает виртуальное адресное пространство с высокой энтропией.</span><span class="sxs-lookup"><span data-stu-id="2085b-107">This option specifies that a 64-bit executable or an executable that is marked by the [/platform:anycpu](../../../csharp/language-reference/compiler-options/platform-compiler-option.md) compiler option supports a high entropy virtual address space.</span></span> <span data-ttu-id="2085b-108">Этот параметр отключен по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="2085b-108">The option is disabled by default.</span></span> <span data-ttu-id="2085b-109">Чтобы включить его, используйте параметр **/highentropyva+** или **/highentropyva**.</span><span class="sxs-lookup"><span data-stu-id="2085b-109">Use **/highentropyva+** or **/highentropyva** to enable it.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2085b-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="2085b-110">Remarks</span></span>  
 <span data-ttu-id="2085b-111">Параметр **/highentropyva** позволяет совместимым версиям ядра Windows использовать более высокие степени энтропии во время смешивания структуры адресного пространства процесса в рамках ASLR.</span><span class="sxs-lookup"><span data-stu-id="2085b-111">The **/highentropyva** option enables compatible versions of the Windows kernel to use higher degrees of entropy when randomizing the address space layout of a process as part of ASLR.</span></span> <span data-ttu-id="2085b-112">Использование более высоких степеней энтропии означает, что можно выделить больше адресов таким областям памяти, как стеки и кучи.</span><span class="sxs-lookup"><span data-stu-id="2085b-112">Using higher degrees of entropy means that a larger number of addresses can be allocated to memory regions such as stacks and heaps.</span></span> <span data-ttu-id="2085b-113">Из-за этого сложнее подобрать расположение определенной области памяти.</span><span class="sxs-lookup"><span data-stu-id="2085b-113">As a result, it is more difficult to guess the location of a particular memory region.</span></span>  
  
 <span data-ttu-id="2085b-114">Если указан параметр компилятора **/highentropyva**, целевой исполняемый файл и все модули, от которых он зависит, должны быть способны обработать значения указателя, размер которых превышает 4 гигабайта (ГБ), если они выполняются как 64-разрядный процесс.</span><span class="sxs-lookup"><span data-stu-id="2085b-114">When the **/highentropyva** compiler option is specified, the target executable and any modules that it depends on must be able to handle pointer values that are larger than 4 gigabytes (GB) when they are running as a 64-bit process.</span></span>

