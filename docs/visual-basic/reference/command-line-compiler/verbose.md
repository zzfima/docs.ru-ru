---
title: -verbose
ms.date: 03/13/2018
helpviewer_keywords:
- verbose compiler option [Visual Basic]
- -verbose compiler option [Visual Basic]
- /verbose compiler option [Visual Basic]
ms.assetid: d1aec0c1-0261-421d-9adc-5b13756100be
ms.openlocfilehash: e70496b552ced8e07cbe3cde34cda377d94da9f4
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2018
ms.locfileid: "50188421"
---
# <a name="-verbose"></a><span data-ttu-id="9d0fd-102">-verbose</span><span class="sxs-lookup"><span data-stu-id="9d0fd-102">-verbose</span></span>
<span data-ttu-id="9d0fd-103">Указывает компилятору создавать подробные сообщения о состоянии и ошибки.</span><span class="sxs-lookup"><span data-stu-id="9d0fd-103">Causes the compiler to produce verbose status and error messages.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9d0fd-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9d0fd-104">Syntax</span></span>  
  
```  
-verbose[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="9d0fd-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="9d0fd-105">Arguments</span></span>  
 <span data-ttu-id="9d0fd-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="9d0fd-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="9d0fd-107">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="9d0fd-107">Optional.</span></span> <span data-ttu-id="9d0fd-108">Указание `-verbose` же эффект достигается указанием `-verbose+`, который указывает компилятору выдавать подробные сообщения.</span><span class="sxs-lookup"><span data-stu-id="9d0fd-108">Specifying `-verbose` is the same as specifying `-verbose+`, which causes the compiler to emit verbose messages.</span></span> <span data-ttu-id="9d0fd-109">Значение по умолчанию для этого параметра — `-verbose-`.</span><span class="sxs-lookup"><span data-stu-id="9d0fd-109">The default for this option is `-verbose-`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9d0fd-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="9d0fd-110">Remarks</span></span>  
 <span data-ttu-id="9d0fd-111">`-verbose` Отображает сведения о общее количество ошибок, выдаваемых компилятором, сообщает, какие сборки загружаются в модуле и отображает, какие файлы компилируемые.</span><span class="sxs-lookup"><span data-stu-id="9d0fd-111">The `-verbose` option displays information about the total number of errors issued by the compiler, reports which assemblies are being loaded by a module, and displays which files are currently being compiled.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9d0fd-112">`-verbose` Не доступна из среды разработки Visual Studio; она доступна только при компиляции из командной строки.</span><span class="sxs-lookup"><span data-stu-id="9d0fd-112">The `-verbose` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9d0fd-113">Пример</span><span class="sxs-lookup"><span data-stu-id="9d0fd-113">Example</span></span>  
 <span data-ttu-id="9d0fd-114">Следующий код компилирует `In.vb` и предписывает компилятору отобразить подробные сведения о состоянии.</span><span class="sxs-lookup"><span data-stu-id="9d0fd-114">The following code compiles `In.vb` and directs the compiler to display verbose status information.</span></span>  
  
```console  
vbc -verbose in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="9d0fd-115">См. также</span><span class="sxs-lookup"><span data-stu-id="9d0fd-115">See Also</span></span>  
 [<span data-ttu-id="9d0fd-116">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="9d0fd-116">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="9d0fd-117">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="9d0fd-117">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
