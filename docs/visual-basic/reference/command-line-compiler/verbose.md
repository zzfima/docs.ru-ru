---
title: -verbose
ms.date: 03/13/2018
helpviewer_keywords:
- verbose compiler option [Visual Basic]
- -verbose compiler option [Visual Basic]
- /verbose compiler option [Visual Basic]
ms.assetid: d1aec0c1-0261-421d-9adc-5b13756100be
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a5f257fce67d8e348b69404411c12ded785cfd68
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33652133"
---
# <a name="-verbose"></a><span data-ttu-id="1764b-102">-verbose</span><span class="sxs-lookup"><span data-stu-id="1764b-102">-verbose</span></span>
<span data-ttu-id="1764b-103">Указывает компилятору создавать подробные сообщения о состоянии и ошибки.</span><span class="sxs-lookup"><span data-stu-id="1764b-103">Causes the compiler to produce verbose status and error messages.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1764b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1764b-104">Syntax</span></span>  
  
```  
-verbose[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="1764b-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="1764b-105">Arguments</span></span>  
 <span data-ttu-id="1764b-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="1764b-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="1764b-107">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="1764b-107">Optional.</span></span> <span data-ttu-id="1764b-108">Указание `-verbose` же эффект достигается указанием `-verbose+`, который указывает компилятору выдавать подробные сообщения.</span><span class="sxs-lookup"><span data-stu-id="1764b-108">Specifying `-verbose` is the same as specifying `-verbose+`, which causes the compiler to emit verbose messages.</span></span> <span data-ttu-id="1764b-109">Значение по умолчанию для этого параметра — `-verbose-`.</span><span class="sxs-lookup"><span data-stu-id="1764b-109">The default for this option is `-verbose-`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1764b-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="1764b-110">Remarks</span></span>  
 <span data-ttu-id="1764b-111">`-verbose` Параметр отображаются сведения о общее количество ошибок, выдаваемых компилятором, сообщает, какие сборки загружаются модулем и отображает, какие файлы в данный момент компилируется.</span><span class="sxs-lookup"><span data-stu-id="1764b-111">The `-verbose` option displays information about the total number of errors issued by the compiler, reports which assemblies are being loaded by a module, and displays which files are currently being compiled.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1764b-112">`-verbose` Параметр недоступен в среде разработки Visual Studio; она доступна только при компиляции из командной строки.</span><span class="sxs-lookup"><span data-stu-id="1764b-112">The `-verbose` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1764b-113">Пример</span><span class="sxs-lookup"><span data-stu-id="1764b-113">Example</span></span>  
 <span data-ttu-id="1764b-114">Следующий код компилирует `In.vb` , а компилятор, чтобы отобразить подробные сведения о состоянии.</span><span class="sxs-lookup"><span data-stu-id="1764b-114">The following code compiles `In.vb` and directs the compiler to display verbose status information.</span></span>  
  
```console  
vbc -verbose in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="1764b-115">См. также</span><span class="sxs-lookup"><span data-stu-id="1764b-115">See Also</span></span>  
 [<span data-ttu-id="1764b-116">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="1764b-116">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="1764b-117">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="1764b-117">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
