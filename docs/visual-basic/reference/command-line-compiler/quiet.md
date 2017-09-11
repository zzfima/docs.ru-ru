---
title: "/ quiet | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- /quiet
- quiet
dev_langs:
- VB
helpviewer_keywords:
- -quiet compiler option [Visual Basic]
- /quiet compiler option [Visual Basic]
- quiet compiler option [Visual Basic]
ms.assetid: 5d77fa23-4c50-4708-8535-649912b098e8
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
ms.openlocfilehash: bc21be8982fea52bf25d0bedeec2b78eee1e705f
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="quiet"></a><span data-ttu-id="2566f-102">/quiet</span><span class="sxs-lookup"><span data-stu-id="2566f-102">/quiet</span></span>
<span data-ttu-id="2566f-103">Запрещает компилятору показывать код синтаксических ошибок и предупреждений.</span><span class="sxs-lookup"><span data-stu-id="2566f-103">Prevents the compiler from displaying code for syntax-related errors and warnings.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2566f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2566f-104">Syntax</span></span>  
  
```  
/quiet  
```  
  
## <a name="remarks"></a><span data-ttu-id="2566f-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="2566f-105">Remarks</span></span>  
 <span data-ttu-id="2566f-106">По умолчанию `/quiet` не действует.</span><span class="sxs-lookup"><span data-stu-id="2566f-106">By default, `/quiet` is not in effect.</span></span> <span data-ttu-id="2566f-107">Когда компилятор сообщает синтаксические ошибки или предупреждения, он выводит строку из исходного кода.</span><span class="sxs-lookup"><span data-stu-id="2566f-107">When the compiler reports a syntax-related error or warning, it also outputs the line from source code.</span></span> <span data-ttu-id="2566f-108">Для приложений, анализирует выходные данные компилятора может быть более удобным, компилятор выводит только результат диагностики.</span><span class="sxs-lookup"><span data-stu-id="2566f-108">For applications that parse compiler output, it may be more convenient for the compiler to output only the text of the diagnostic.</span></span>  
  
 <span data-ttu-id="2566f-109">В следующем примере `Module1` выводит ошибку, содержащую исходный код при компиляции без `/quiet`.</span><span class="sxs-lookup"><span data-stu-id="2566f-109">In the following example, `Module1` outputs an error that includes source code when compiled without `/quiet`.</span></span>  
  
```  
Module Module1  
    Sub Main()  
        x()  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="2566f-110">Результат</span><span class="sxs-lookup"><span data-stu-id="2566f-110">Output:</span></span>  
  
 `E:\test\t2.vb(3) : error BC30451: Name 'x' is not declared.`  
  
 `x`  
  
 `~`  
  
 <span data-ttu-id="2566f-111">Компиляция производится с помощью `/quiet`, компилятор выводит следующие данные:</span><span class="sxs-lookup"><span data-stu-id="2566f-111">Compiled with `/quiet`, the compiler outputs only the following:</span></span>  
  
 `E:\test\t2.vb(3) : error BC30451: Name 'x' is not declared.`  
  
> [!NOTE]
>  <span data-ttu-id="2566f-112">`/quiet` Параметр недоступен из среды разработки Visual Studio; она доступна только при компиляции из командной строки.</span><span class="sxs-lookup"><span data-stu-id="2566f-112">The `/quiet` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2566f-113">Пример</span><span class="sxs-lookup"><span data-stu-id="2566f-113">Example</span></span>  
 <span data-ttu-id="2566f-114">Следующий код компилирует `T2.vb` и не отображает код для компилятора синтаксические диагностики:</span><span class="sxs-lookup"><span data-stu-id="2566f-114">The following code compiles `T2.vb` and does not display code for syntax-related compiler diagnostics:</span></span>  
  
```  
vbc /quiet t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="2566f-115">См. также</span><span class="sxs-lookup"><span data-stu-id="2566f-115">See Also</span></span>  
 <span data-ttu-id="2566f-116">[Компилятор командной строки Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="2566f-116">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="2566f-117"> [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span><span class="sxs-lookup"><span data-stu-id="2566f-117"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span></span>
