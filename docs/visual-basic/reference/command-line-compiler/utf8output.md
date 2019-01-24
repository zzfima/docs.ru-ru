---
title: -utf8output (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- -utf8output compiler option [Visual Basic]
- utf8output compiler option [Visual Basic]
- /utf8output compiler option [Visual Basic]
ms.assetid: 8ab36b1e-027a-49ac-85b4-f48997d9e4d6
ms.openlocfilehash: e6bb04364c2f92129993e19c746fd7cb9c18dc8a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54648538"
---
# <a name="-utf8output-visual-basic"></a><span data-ttu-id="1098a-102">-utf8output (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1098a-102">-utf8output (Visual Basic)</span></span>
<span data-ttu-id="1098a-103">Отображает выходные данные компилятора в кодировке UTF-8.</span><span class="sxs-lookup"><span data-stu-id="1098a-103">Displays compiler output using UTF-8 encoding.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1098a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1098a-104">Syntax</span></span>  
  
```  
-utf8output[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="1098a-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="1098a-105">Arguments</span></span>  
 <span data-ttu-id="1098a-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="1098a-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="1098a-107">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="1098a-107">Optional.</span></span> <span data-ttu-id="1098a-108">Значение по умолчанию для этого параметра — `-utf8output-`, что означает, что выходные данные компилятора не использует кодировку UTF-8.</span><span class="sxs-lookup"><span data-stu-id="1098a-108">The default for this option is `-utf8output-`, which means compiler output does not use UTF-8 encoding.</span></span> <span data-ttu-id="1098a-109">Указание `-utf8output` дает тот же результат, что и указание `-utf8output+`.</span><span class="sxs-lookup"><span data-stu-id="1098a-109">Specifying `-utf8output` is the same as specifying `-utf8output+`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1098a-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="1098a-110">Remarks</span></span>  
 <span data-ttu-id="1098a-111">В некоторых конфигурациях для различных языков выходные данные компилятора, могут отображаться правильно в консоли.</span><span class="sxs-lookup"><span data-stu-id="1098a-111">In some international configurations, compiler output cannot be displayed correctly in the console.</span></span> <span data-ttu-id="1098a-112">В таких ситуациях используйте `-utf8output` и перенаправления выходных данных компилятора в файл.</span><span class="sxs-lookup"><span data-stu-id="1098a-112">In such situations, use `-utf8output` and redirect compiler output to a file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1098a-113">`-utf8output` Не доступна из среды разработки Visual Studio; она доступна только при компиляции из командной строки.</span><span class="sxs-lookup"><span data-stu-id="1098a-113">The `-utf8output` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1098a-114">Пример</span><span class="sxs-lookup"><span data-stu-id="1098a-114">Example</span></span>  
 <span data-ttu-id="1098a-115">Следующий код компилирует `In.vb` и компилятор для отображения выходных данных с использованием кодировки UTF-8.</span><span class="sxs-lookup"><span data-stu-id="1098a-115">The following code compiles `In.vb` and directs the compiler to display output using UTF-8 encoding.</span></span>  
  
```console  
vbc -utf8output in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="1098a-116">См. также</span><span class="sxs-lookup"><span data-stu-id="1098a-116">See also</span></span>
- [<span data-ttu-id="1098a-117">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="1098a-117">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="1098a-118">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="1098a-118">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
