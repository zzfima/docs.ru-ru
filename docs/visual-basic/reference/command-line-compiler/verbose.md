---
title: "/ verbose | Документы Microsoft"
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
- verbose compiler option [Visual Basic]
- -verbose compiler option [Visual Basic]
- /verbose compiler option [Visual Basic]
ms.assetid: d1aec0c1-0261-421d-9adc-5b13756100be
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
ms.openlocfilehash: 62285a727217aa897a83a9e746588c80a2c519c0
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="verbose"></a><span data-ttu-id="940a2-102">/verbose</span><span class="sxs-lookup"><span data-stu-id="940a2-102">/verbose</span></span>
<span data-ttu-id="940a2-103">Указывает компилятору создавать подробные сообщения об ошибках и состоянии.</span><span class="sxs-lookup"><span data-stu-id="940a2-103">Causes the compiler to produce verbose status and error messages.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="940a2-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="940a2-104">Syntax</span></span>  
  
```  
/verbose[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="940a2-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="940a2-105">Arguments</span></span>  
 <span data-ttu-id="940a2-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="940a2-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="940a2-107">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="940a2-107">Optional.</span></span> <span data-ttu-id="940a2-108">Указание `/verbose` же эффект достигается указанием `/verbose+`, который указывает компилятору выводить подробные сообщения.</span><span class="sxs-lookup"><span data-stu-id="940a2-108">Specifying `/verbose` is the same as specifying `/verbose+`, which causes the compiler to emit verbose messages.</span></span> <span data-ttu-id="940a2-109">Значение по умолчанию для этого параметра — `/verbose-`.</span><span class="sxs-lookup"><span data-stu-id="940a2-109">The default for this option is `/verbose-`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="940a2-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="940a2-110">Remarks</span></span>  
 <span data-ttu-id="940a2-111">`/verbose` Отображает сведения о общее количество ошибок, выдаваемых компилятором, сообщает, какие сборки загружаются модулем и отображает компилируемые файлы.</span><span class="sxs-lookup"><span data-stu-id="940a2-111">The `/verbose` option displays information about the total number of errors issued by the compiler, reports which assemblies are being loaded by a module, and displays which files are currently being compiled.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="940a2-112">`/verbose` Параметр недоступен из среды разработки Visual Studio; она доступна только при компиляции из командной строки.</span><span class="sxs-lookup"><span data-stu-id="940a2-112">The `/verbose` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="940a2-113">Пример</span><span class="sxs-lookup"><span data-stu-id="940a2-113">Example</span></span>  
 <span data-ttu-id="940a2-114">Следующий код компилирует `In.vb` , а компилятор, чтобы отобразить подробные сведения о состоянии.</span><span class="sxs-lookup"><span data-stu-id="940a2-114">The following code compiles `In.vb` and directs the compiler to display verbose status information.</span></span>  
  
```  
vbc /verbose in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="940a2-115">См. также</span><span class="sxs-lookup"><span data-stu-id="940a2-115">See Also</span></span>  
 <span data-ttu-id="940a2-116">[Компилятор командной строки Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="940a2-116">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="940a2-117"> [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span><span class="sxs-lookup"><span data-stu-id="940a2-117"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span></span>
