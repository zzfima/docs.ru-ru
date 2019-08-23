---
title: -verbose
ms.date: 03/13/2018
helpviewer_keywords:
- verbose compiler option [Visual Basic]
- -verbose compiler option [Visual Basic]
- /verbose compiler option [Visual Basic]
ms.assetid: d1aec0c1-0261-421d-9adc-5b13756100be
ms.openlocfilehash: 5b3899462af7c4aa8e0f77377a8d7485975f9867
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69937257"
---
# <a name="-verbose"></a><span data-ttu-id="9e945-102">-verbose</span><span class="sxs-lookup"><span data-stu-id="9e945-102">-verbose</span></span>
<span data-ttu-id="9e945-103">Заставляет компилятор создавать подробные сведения о состоянии и сообщения об ошибках.</span><span class="sxs-lookup"><span data-stu-id="9e945-103">Causes the compiler to produce verbose status and error messages.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9e945-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9e945-104">Syntax</span></span>  
  
```  
-verbose[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="9e945-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="9e945-105">Arguments</span></span>  
 <span data-ttu-id="9e945-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="9e945-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="9e945-107">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="9e945-107">Optional.</span></span> <span data-ttu-id="9e945-108">Указание `-verbose` аналогично указанию `-verbose+`параметра, что приводит к тому, что компилятор выдает подробные сообщения.</span><span class="sxs-lookup"><span data-stu-id="9e945-108">Specifying `-verbose` is the same as specifying `-verbose+`, which causes the compiler to emit verbose messages.</span></span> <span data-ttu-id="9e945-109">Значение по умолчанию для этого `-verbose-`параметра —.</span><span class="sxs-lookup"><span data-stu-id="9e945-109">The default for this option is `-verbose-`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9e945-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="9e945-110">Remarks</span></span>  
 <span data-ttu-id="9e945-111">`-verbose` Параметр отображает сведения об общем количестве ошибок, выданных компилятором, сообщает о том, какие сборки загружаются модулем, и показывает, какие файлы в данный момент компилируются.</span><span class="sxs-lookup"><span data-stu-id="9e945-111">The `-verbose` option displays information about the total number of errors issued by the compiler, reports which assemblies are being loaded by a module, and displays which files are currently being compiled.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9e945-112">Этот `-verbose` параметр недоступен в среде разработки Visual Studio; он доступен только при компиляции из командной строки.</span><span class="sxs-lookup"><span data-stu-id="9e945-112">The `-verbose` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9e945-113">Пример</span><span class="sxs-lookup"><span data-stu-id="9e945-113">Example</span></span>  
 <span data-ttu-id="9e945-114">Следующий код компилирует `In.vb` и направляет компилятор для вывода подробных сведений о состоянии.</span><span class="sxs-lookup"><span data-stu-id="9e945-114">The following code compiles `In.vb` and directs the compiler to display verbose status information.</span></span>  
  
```console  
vbc -verbose in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="9e945-115">См. также</span><span class="sxs-lookup"><span data-stu-id="9e945-115">See also</span></span>

- [<span data-ttu-id="9e945-116">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="9e945-116">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="9e945-117">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="9e945-117">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
