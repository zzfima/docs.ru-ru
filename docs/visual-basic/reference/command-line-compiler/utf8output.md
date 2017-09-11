---
title: "/ utf8output (Visual Basic) | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- -utf8output compiler option [Visual Basic]
- utf8output compiler option [Visual Basic]
- /utf8output compiler option [Visual Basic]
ms.assetid: 8ab36b1e-027a-49ac-85b4-f48997d9e4d6
caps.latest.revision: 11
author: dotnet-bot
ms.author: dotnetcontent
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 45361fb1dca34f2cdc849184d0e316b27d9545b6
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="utf8output-visual-basic"></a><span data-ttu-id="00e22-102">/utf8output (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="00e22-102">/utf8output (Visual Basic)</span></span>
<span data-ttu-id="00e22-103">Отображает выходные данные компилятора в кодировке UTF-8.</span><span class="sxs-lookup"><span data-stu-id="00e22-103">Displays compiler output using UTF-8 encoding.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="00e22-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="00e22-104">Syntax</span></span>  
  
```  
/utf8output[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="00e22-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="00e22-105">Arguments</span></span>  
 <span data-ttu-id="00e22-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="00e22-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="00e22-107">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="00e22-107">Optional.</span></span> <span data-ttu-id="00e22-108">Значение по умолчанию для этого параметра — `/utf8output-`, что означает, что выходные данные компилятора не используется кодировка UTF-8.</span><span class="sxs-lookup"><span data-stu-id="00e22-108">The default for this option is `/utf8output-`, which means compiler output does not use UTF-8 encoding.</span></span> <span data-ttu-id="00e22-109">Указание `/utf8output` же эффект достигается указанием `/utf8output+`.</span><span class="sxs-lookup"><span data-stu-id="00e22-109">Specifying `/utf8output` is the same as specifying `/utf8output+`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="00e22-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="00e22-110">Remarks</span></span>  
 <span data-ttu-id="00e22-111">В некоторых конфигурациях для различных языков выходные данные компилятора, могут отображаться неправильно в консоли.</span><span class="sxs-lookup"><span data-stu-id="00e22-111">In some international configurations, compiler output cannot be displayed correctly in the console.</span></span> <span data-ttu-id="00e22-112">В этом случае следует использовать `/utf8output` и перенаправления выходных данных компилятора в файл.</span><span class="sxs-lookup"><span data-stu-id="00e22-112">In such situations, use `/utf8output` and redirect compiler output to a file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="00e22-113">`/utf8output` Параметр недоступен из среды разработки Visual Studio; она доступна только при компиляции из командной строки.</span><span class="sxs-lookup"><span data-stu-id="00e22-113">The `/utf8output` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="00e22-114">Пример</span><span class="sxs-lookup"><span data-stu-id="00e22-114">Example</span></span>  
 <span data-ttu-id="00e22-115">Следующий код компилирует `In.vb` и направляет компилятор для отображения вывода в кодировке UTF-8.</span><span class="sxs-lookup"><span data-stu-id="00e22-115">The following code compiles `In.vb` and directs the compiler to display output using UTF-8 encoding.</span></span>  
  
```  
vbc /utf8output in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="00e22-116">См. также</span><span class="sxs-lookup"><span data-stu-id="00e22-116">See Also</span></span>  
 <span data-ttu-id="00e22-117">[Компилятор командной строки Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="00e22-117">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="00e22-118"> [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span><span class="sxs-lookup"><span data-stu-id="00e22-118"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span></span>
