---
title: /utf8output (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- -utf8output compiler option [Visual Basic]
- utf8output compiler option [Visual Basic]
- /utf8output compiler option [Visual Basic]
ms.assetid: 8ab36b1e-027a-49ac-85b4-f48997d9e4d6
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 23c7c308865a6b6afb07443a42090fff3d9e2efb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="utf8output-visual-basic"></a><span data-ttu-id="33fa5-102">/utf8output (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="33fa5-102">/utf8output (Visual Basic)</span></span>
<span data-ttu-id="33fa5-103">Отображает выходные данные компилятора в кодировке UTF-8.</span><span class="sxs-lookup"><span data-stu-id="33fa5-103">Displays compiler output using UTF-8 encoding.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="33fa5-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="33fa5-104">Syntax</span></span>  
  
```  
/utf8output[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="33fa5-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="33fa5-105">Arguments</span></span>  
 <span data-ttu-id="33fa5-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="33fa5-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="33fa5-107">Необязательно.</span><span class="sxs-lookup"><span data-stu-id="33fa5-107">Optional.</span></span> <span data-ttu-id="33fa5-108">Значение по умолчанию для этого параметра — `/utf8output-`, что означает, что выходные данные компилятора не использует кодировку UTF-8.</span><span class="sxs-lookup"><span data-stu-id="33fa5-108">The default for this option is `/utf8output-`, which means compiler output does not use UTF-8 encoding.</span></span> <span data-ttu-id="33fa5-109">Указание `/utf8output` же эффект достигается указанием `/utf8output+`.</span><span class="sxs-lookup"><span data-stu-id="33fa5-109">Specifying `/utf8output` is the same as specifying `/utf8output+`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="33fa5-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="33fa5-110">Remarks</span></span>  
 <span data-ttu-id="33fa5-111">В некоторых конфигурациях для различных языков выходные данные компилятора не может неправильно отображаться на консоли.</span><span class="sxs-lookup"><span data-stu-id="33fa5-111">In some international configurations, compiler output cannot be displayed correctly in the console.</span></span> <span data-ttu-id="33fa5-112">В этом случае следует использовать `/utf8output` и перенаправлять выходные данные компилятора в файл.</span><span class="sxs-lookup"><span data-stu-id="33fa5-112">In such situations, use `/utf8output` and redirect compiler output to a file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="33fa5-113">`/utf8output` Параметр недоступен в среде разработки Visual Studio; она доступна только при компиляции из командной строки.</span><span class="sxs-lookup"><span data-stu-id="33fa5-113">The `/utf8output` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="33fa5-114">Пример</span><span class="sxs-lookup"><span data-stu-id="33fa5-114">Example</span></span>  
 <span data-ttu-id="33fa5-115">Следующий код компилирует `In.vb` , а компилятор для отображения вывода с использованием кодировки UTF-8.</span><span class="sxs-lookup"><span data-stu-id="33fa5-115">The following code compiles `In.vb` and directs the compiler to display output using UTF-8 encoding.</span></span>  
  
```  
vbc /utf8output in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="33fa5-116">См. также</span><span class="sxs-lookup"><span data-stu-id="33fa5-116">See Also</span></span>  
 [<span data-ttu-id="33fa5-117">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="33fa5-117">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="33fa5-118">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="33fa5-118">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
