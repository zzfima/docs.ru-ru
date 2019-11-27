---
title: -utf8output
ms.date: 07/20/2015
helpviewer_keywords:
- -utf8output compiler option [Visual Basic]
- utf8output compiler option [Visual Basic]
- /utf8output compiler option [Visual Basic]
ms.assetid: 8ab36b1e-027a-49ac-85b4-f48997d9e4d6
ms.openlocfilehash: 5cdc60888cd872940afc1b03febd879bb6d87c2e
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350841"
---
# <a name="-utf8output-visual-basic"></a><span data-ttu-id="2a50d-102">-utf8output (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2a50d-102">-utf8output (Visual Basic)</span></span>
<span data-ttu-id="2a50d-103">Отображает выходные данные компилятора в кодировке UTF-8.</span><span class="sxs-lookup"><span data-stu-id="2a50d-103">Displays compiler output using UTF-8 encoding.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a50d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2a50d-104">Syntax</span></span>  
  
```console  
-utf8output[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="2a50d-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="2a50d-105">Arguments</span></span>  
 <span data-ttu-id="2a50d-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="2a50d-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="2a50d-107">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="2a50d-107">Optional.</span></span> <span data-ttu-id="2a50d-108">Значение по умолчанию для этого параметра — `-utf8output-`, то есть выходные данные компилятора не используют кодировку UTF-8.</span><span class="sxs-lookup"><span data-stu-id="2a50d-108">The default for this option is `-utf8output-`, which means compiler output does not use UTF-8 encoding.</span></span> <span data-ttu-id="2a50d-109">Указание `-utf8output` дает тот же результат, что и указание `-utf8output+`.</span><span class="sxs-lookup"><span data-stu-id="2a50d-109">Specifying `-utf8output` is the same as specifying `-utf8output+`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2a50d-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="2a50d-110">Remarks</span></span>  
 <span data-ttu-id="2a50d-111">В некоторых международных конфигурациях вывод компилятора не может правильно отображаться в консоли.</span><span class="sxs-lookup"><span data-stu-id="2a50d-111">In some international configurations, compiler output cannot be displayed correctly in the console.</span></span> <span data-ttu-id="2a50d-112">В таких ситуациях используйте `-utf8output` и перенаправьте выходные данные компилятора в файл.</span><span class="sxs-lookup"><span data-stu-id="2a50d-112">In such situations, use `-utf8output` and redirect compiler output to a file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2a50d-113">Параметр `-utf8output` недоступен в среде разработки Visual Studio; Он доступен только при компиляции из командной строки.</span><span class="sxs-lookup"><span data-stu-id="2a50d-113">The `-utf8output` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2a50d-114">Пример</span><span class="sxs-lookup"><span data-stu-id="2a50d-114">Example</span></span>  
 <span data-ttu-id="2a50d-115">Следующий код компилирует `In.vb` и направляет компилятор для вывода выходных данных в кодировке UTF-8.</span><span class="sxs-lookup"><span data-stu-id="2a50d-115">The following code compiles `In.vb` and directs the compiler to display output using UTF-8 encoding.</span></span>  
  
```console  
vbc -utf8output in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="2a50d-116">См. также</span><span class="sxs-lookup"><span data-stu-id="2a50d-116">See also</span></span>

- [<span data-ttu-id="2a50d-117">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="2a50d-117">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="2a50d-118">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="2a50d-118">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
