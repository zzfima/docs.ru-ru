---
title: -verbose
ms.date: 03/13/2018
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- verbose compiler option [Visual Basic]
- -verbose compiler option [Visual Basic]
- /verbose compiler option [Visual Basic]
ms.assetid: d1aec0c1-0261-421d-9adc-5b13756100be
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f0523409e53a8c7ea34de7dcc24b1bce2885a183
ms.sourcegitcommit: 498799639937c89de777361aab74261efe7b79ea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/22/2018
---
# <a name="-verbose"></a><span data-ttu-id="c7a57-102">-verbose</span><span class="sxs-lookup"><span data-stu-id="c7a57-102">-verbose</span></span>
<span data-ttu-id="c7a57-103">Указывает компилятору создавать подробные сообщения о состоянии и ошибки.</span><span class="sxs-lookup"><span data-stu-id="c7a57-103">Causes the compiler to produce verbose status and error messages.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c7a57-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c7a57-104">Syntax</span></span>  
  
```  
-verbose[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="c7a57-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="c7a57-105">Arguments</span></span>  
 <span data-ttu-id="c7a57-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="c7a57-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="c7a57-107">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="c7a57-107">Optional.</span></span> <span data-ttu-id="c7a57-108">Указание `-verbose` же эффект достигается указанием `-verbose+`, который указывает компилятору выдавать подробные сообщения.</span><span class="sxs-lookup"><span data-stu-id="c7a57-108">Specifying `-verbose` is the same as specifying `-verbose+`, which causes the compiler to emit verbose messages.</span></span> <span data-ttu-id="c7a57-109">Значение по умолчанию для этого параметра — `-verbose-`.</span><span class="sxs-lookup"><span data-stu-id="c7a57-109">The default for this option is `-verbose-`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c7a57-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="c7a57-110">Remarks</span></span>  
 <span data-ttu-id="c7a57-111">`-verbose` Параметр отображаются сведения о общее количество ошибок, выдаваемых компилятором, сообщает, какие сборки загружаются модулем и отображает, какие файлы в данный момент компилируется.</span><span class="sxs-lookup"><span data-stu-id="c7a57-111">The `-verbose` option displays information about the total number of errors issued by the compiler, reports which assemblies are being loaded by a module, and displays which files are currently being compiled.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c7a57-112">`-verbose` Параметр недоступен в среде разработки Visual Studio; она доступна только при компиляции из командной строки.</span><span class="sxs-lookup"><span data-stu-id="c7a57-112">The `-verbose` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c7a57-113">Пример</span><span class="sxs-lookup"><span data-stu-id="c7a57-113">Example</span></span>  
 <span data-ttu-id="c7a57-114">Следующий код компилирует `In.vb` , а компилятор, чтобы отобразить подробные сведения о состоянии.</span><span class="sxs-lookup"><span data-stu-id="c7a57-114">The following code compiles `In.vb` and directs the compiler to display verbose status information.</span></span>  
  
```console  
vbc -verbose in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="c7a57-115">См. также</span><span class="sxs-lookup"><span data-stu-id="c7a57-115">See Also</span></span>  
 [<span data-ttu-id="c7a57-116">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="c7a57-116">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="c7a57-117">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="c7a57-117">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
