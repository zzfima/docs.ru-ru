---
title: -verbose
ms.date: 03/13/2018
helpviewer_keywords:
- verbose compiler option [Visual Basic]
- -verbose compiler option [Visual Basic]
- /verbose compiler option [Visual Basic]
ms.assetid: d1aec0c1-0261-421d-9adc-5b13756100be
ms.openlocfilehash: f6d896fb0d41a8fa3ed613d29bc3fca2bd14cc5e
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2019
ms.locfileid: "58832797"
---
# <a name="-verbose"></a><span data-ttu-id="59b72-102">-verbose</span><span class="sxs-lookup"><span data-stu-id="59b72-102">-verbose</span></span>
<span data-ttu-id="59b72-103">Указывает компилятору создавать подробные сообщения о состоянии и ошибки.</span><span class="sxs-lookup"><span data-stu-id="59b72-103">Causes the compiler to produce verbose status and error messages.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="59b72-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="59b72-104">Syntax</span></span>  
  
```  
-verbose[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="59b72-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="59b72-105">Arguments</span></span>  
 <span data-ttu-id="59b72-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="59b72-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="59b72-107">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="59b72-107">Optional.</span></span> <span data-ttu-id="59b72-108">Указание `-verbose` же эффект достигается указанием `-verbose+`, который указывает компилятору выдавать подробные сообщения.</span><span class="sxs-lookup"><span data-stu-id="59b72-108">Specifying `-verbose` is the same as specifying `-verbose+`, which causes the compiler to emit verbose messages.</span></span> <span data-ttu-id="59b72-109">Значение по умолчанию для этого параметра — `-verbose-`.</span><span class="sxs-lookup"><span data-stu-id="59b72-109">The default for this option is `-verbose-`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="59b72-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="59b72-110">Remarks</span></span>  
 <span data-ttu-id="59b72-111">`-verbose` Отображает сведения о общее количество ошибок, выдаваемых компилятором, сообщает, какие сборки загружаются в модуле и отображает, какие файлы компилируемые.</span><span class="sxs-lookup"><span data-stu-id="59b72-111">The `-verbose` option displays information about the total number of errors issued by the compiler, reports which assemblies are being loaded by a module, and displays which files are currently being compiled.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="59b72-112">`-verbose` Не доступна из среды разработки Visual Studio; она доступна только при компиляции из командной строки.</span><span class="sxs-lookup"><span data-stu-id="59b72-112">The `-verbose` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="59b72-113">Пример</span><span class="sxs-lookup"><span data-stu-id="59b72-113">Example</span></span>  
 <span data-ttu-id="59b72-114">Следующий код компилирует `In.vb` и предписывает компилятору отобразить подробные сведения о состоянии.</span><span class="sxs-lookup"><span data-stu-id="59b72-114">The following code compiles `In.vb` and directs the compiler to display verbose status information.</span></span>  
  
```console  
vbc -verbose in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="59b72-115">См. также</span><span class="sxs-lookup"><span data-stu-id="59b72-115">See also</span></span>

- [<span data-ttu-id="59b72-116">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="59b72-116">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="59b72-117">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="59b72-117">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
