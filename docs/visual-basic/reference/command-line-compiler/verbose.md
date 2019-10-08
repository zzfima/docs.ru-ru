---
title: -verbose
ms.date: 03/13/2018
helpviewer_keywords:
- verbose compiler option [Visual Basic]
- -verbose compiler option [Visual Basic]
- /verbose compiler option [Visual Basic]
ms.assetid: d1aec0c1-0261-421d-9adc-5b13756100be
ms.openlocfilehash: 8c5bc1d2ce331b8fe9461f91d64fbeab5a070b59
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004972"
---
# <a name="-verbose"></a><span data-ttu-id="3e014-102">-verbose</span><span class="sxs-lookup"><span data-stu-id="3e014-102">-verbose</span></span>
<span data-ttu-id="3e014-103">Заставляет компилятор создавать подробные сведения о состоянии и сообщения об ошибках.</span><span class="sxs-lookup"><span data-stu-id="3e014-103">Causes the compiler to produce verbose status and error messages.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3e014-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3e014-104">Syntax</span></span>  
  
```console  
-verbose[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="3e014-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="3e014-105">Arguments</span></span>  
 <span data-ttu-id="3e014-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="3e014-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="3e014-107">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="3e014-107">Optional.</span></span> <span data-ttu-id="3e014-108">Указание `-verbose` аналогично указанию `-verbose+`, что приводит к тому, что компилятор выдает подробные сообщения.</span><span class="sxs-lookup"><span data-stu-id="3e014-108">Specifying `-verbose` is the same as specifying `-verbose+`, which causes the compiler to emit verbose messages.</span></span> <span data-ttu-id="3e014-109">Значение по умолчанию для этого параметра — `-verbose-`.</span><span class="sxs-lookup"><span data-stu-id="3e014-109">The default for this option is `-verbose-`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3e014-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="3e014-110">Remarks</span></span>  
 <span data-ttu-id="3e014-111">Параметр `-verbose` отображает сведения об общем количестве ошибок, выданных компилятором, сообщает о том, какие сборки загружаются модулем, и показывает, какие файлы в данный момент компилируются.</span><span class="sxs-lookup"><span data-stu-id="3e014-111">The `-verbose` option displays information about the total number of errors issued by the compiler, reports which assemblies are being loaded by a module, and displays which files are currently being compiled.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3e014-112">Параметр `-verbose` недоступен в среде разработки Visual Studio; Он доступен только при компиляции из командной строки.</span><span class="sxs-lookup"><span data-stu-id="3e014-112">The `-verbose` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3e014-113">Пример</span><span class="sxs-lookup"><span data-stu-id="3e014-113">Example</span></span>  
 <span data-ttu-id="3e014-114">Следующий код компилирует `In.vb` и направляет компилятор для вывода подробных сведений о состоянии.</span><span class="sxs-lookup"><span data-stu-id="3e014-114">The following code compiles `In.vb` and directs the compiler to display verbose status information.</span></span>  
  
```console  
vbc -verbose in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="3e014-115">См. также</span><span class="sxs-lookup"><span data-stu-id="3e014-115">See also</span></span>

- [<span data-ttu-id="3e014-116">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="3e014-116">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="3e014-117">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="3e014-117">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
