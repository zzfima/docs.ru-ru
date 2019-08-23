---
title: -utf8output (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- -utf8output compiler option [Visual Basic]
- utf8output compiler option [Visual Basic]
- /utf8output compiler option [Visual Basic]
ms.assetid: 8ab36b1e-027a-49ac-85b4-f48997d9e4d6
ms.openlocfilehash: 789df84bb4011d1ad128c50a9c689d1217be6694
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69937274"
---
# <a name="-utf8output-visual-basic"></a><span data-ttu-id="85ab9-102">-utf8output (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="85ab9-102">-utf8output (Visual Basic)</span></span>
<span data-ttu-id="85ab9-103">Отображает выходные данные компилятора в кодировке UTF-8.</span><span class="sxs-lookup"><span data-stu-id="85ab9-103">Displays compiler output using UTF-8 encoding.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="85ab9-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="85ab9-104">Syntax</span></span>  
  
```  
-utf8output[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="85ab9-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="85ab9-105">Arguments</span></span>  
 <span data-ttu-id="85ab9-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="85ab9-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="85ab9-107">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="85ab9-107">Optional.</span></span> <span data-ttu-id="85ab9-108">Значение по умолчанию для этого `-utf8output-`параметра —, то есть выходные данные компилятора не используют кодировку UTF-8.</span><span class="sxs-lookup"><span data-stu-id="85ab9-108">The default for this option is `-utf8output-`, which means compiler output does not use UTF-8 encoding.</span></span> <span data-ttu-id="85ab9-109">Указание `-utf8output` дает тот же результат, что и указание `-utf8output+`.</span><span class="sxs-lookup"><span data-stu-id="85ab9-109">Specifying `-utf8output` is the same as specifying `-utf8output+`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="85ab9-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="85ab9-110">Remarks</span></span>  
 <span data-ttu-id="85ab9-111">В некоторых международных конфигурациях вывод компилятора не может правильно отображаться в консоли.</span><span class="sxs-lookup"><span data-stu-id="85ab9-111">In some international configurations, compiler output cannot be displayed correctly in the console.</span></span> <span data-ttu-id="85ab9-112">В таких ситуациях следует использовать `-utf8output` и перенаправить выходные данные компилятора в файл.</span><span class="sxs-lookup"><span data-stu-id="85ab9-112">In such situations, use `-utf8output` and redirect compiler output to a file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="85ab9-113">Этот `-utf8output` параметр недоступен в среде разработки Visual Studio; он доступен только при компиляции из командной строки.</span><span class="sxs-lookup"><span data-stu-id="85ab9-113">The `-utf8output` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="85ab9-114">Пример</span><span class="sxs-lookup"><span data-stu-id="85ab9-114">Example</span></span>  
 <span data-ttu-id="85ab9-115">Следующий код компилирует `In.vb` и направляет компилятор для вывода выходных данных в кодировке UTF-8.</span><span class="sxs-lookup"><span data-stu-id="85ab9-115">The following code compiles `In.vb` and directs the compiler to display output using UTF-8 encoding.</span></span>  
  
```console  
vbc -utf8output in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="85ab9-116">См. также</span><span class="sxs-lookup"><span data-stu-id="85ab9-116">See also</span></span>

- [<span data-ttu-id="85ab9-117">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="85ab9-117">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="85ab9-118">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="85ab9-118">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
