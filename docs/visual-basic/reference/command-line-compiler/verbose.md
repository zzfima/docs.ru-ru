---
title: /verbose
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- verbose compiler option [Visual Basic]
- -verbose compiler option [Visual Basic]
- /verbose compiler option [Visual Basic]
ms.assetid: d1aec0c1-0261-421d-9adc-5b13756100be
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 5480f828fa1f0b6d71fa649bf44513ce806bb440
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="verbose"></a><span data-ttu-id="6ec4e-102">/verbose</span><span class="sxs-lookup"><span data-stu-id="6ec4e-102">/verbose</span></span>
<span data-ttu-id="6ec4e-103">Указывает компилятору создавать подробные сообщения о состоянии и ошибки.</span><span class="sxs-lookup"><span data-stu-id="6ec4e-103">Causes the compiler to produce verbose status and error messages.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6ec4e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6ec4e-104">Syntax</span></span>  
  
```  
/verbose[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="6ec4e-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="6ec4e-105">Arguments</span></span>  
 <span data-ttu-id="6ec4e-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="6ec4e-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="6ec4e-107">Необязательно.</span><span class="sxs-lookup"><span data-stu-id="6ec4e-107">Optional.</span></span> <span data-ttu-id="6ec4e-108">Указание `/verbose` же эффект достигается указанием `/verbose+`, который указывает компилятору выдавать подробные сообщения.</span><span class="sxs-lookup"><span data-stu-id="6ec4e-108">Specifying `/verbose` is the same as specifying `/verbose+`, which causes the compiler to emit verbose messages.</span></span> <span data-ttu-id="6ec4e-109">Значение по умолчанию для этого параметра — `/verbose-`.</span><span class="sxs-lookup"><span data-stu-id="6ec4e-109">The default for this option is `/verbose-`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6ec4e-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="6ec4e-110">Remarks</span></span>  
 <span data-ttu-id="6ec4e-111">`/verbose` Параметр отображаются сведения о общее количество ошибок, выдаваемых компилятором, сообщает, какие сборки загружаются модулем и отображает, какие файлы в данный момент компилируется.</span><span class="sxs-lookup"><span data-stu-id="6ec4e-111">The `/verbose` option displays information about the total number of errors issued by the compiler, reports which assemblies are being loaded by a module, and displays which files are currently being compiled.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6ec4e-112">`/verbose` Параметр недоступен в среде разработки Visual Studio; она доступна только при компиляции из командной строки.</span><span class="sxs-lookup"><span data-stu-id="6ec4e-112">The `/verbose` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6ec4e-113">Пример</span><span class="sxs-lookup"><span data-stu-id="6ec4e-113">Example</span></span>  
 <span data-ttu-id="6ec4e-114">Следующий код компилирует `In.vb` , а компилятор, чтобы отобразить подробные сведения о состоянии.</span><span class="sxs-lookup"><span data-stu-id="6ec4e-114">The following code compiles `In.vb` and directs the compiler to display verbose status information.</span></span>  
  
```  
vbc /verbose in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="6ec4e-115">См. также</span><span class="sxs-lookup"><span data-stu-id="6ec4e-115">See Also</span></span>  
 [<span data-ttu-id="6ec4e-116">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="6ec4e-116">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="6ec4e-117">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="6ec4e-117">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
