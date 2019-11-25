---
title: -define
ms.date: 03/10/2018
helpviewer_keywords:
- -d compiler option [Visual Basic]
- /d compiler option [Visual Basic]
- -define compiler option [Visual Basic]
- d compiler option [Visual Basic]
- /define compiler option [Visual Basic]
- define compiler option [Visual Basic]
ms.assetid: f735c57d-1cf9-4f2f-a26f-0de630fd4077
ms.openlocfilehash: fd0875f09bf3ba7211ede500aa0da45f8b7cd2c7
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344762"
---
# <a name="-define-visual-basic"></a><span data-ttu-id="f9238-102">-define (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f9238-102">-define (Visual Basic)</span></span>
<span data-ttu-id="f9238-103">Задает константы условной компиляции.</span><span class="sxs-lookup"><span data-stu-id="f9238-103">Defines conditional compiler constants.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f9238-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f9238-104">Syntax</span></span>  
  
```console  
-define:["]symbol[=value][,symbol[=value]]["]  
```

<span data-ttu-id="f9238-105">or</span><span class="sxs-lookup"><span data-stu-id="f9238-105">or</span></span>

```console  
-d:["]symbol[=value][,symbol[=value]]["]  
```  
  
## <a name="arguments"></a><span data-ttu-id="f9238-106">Аргументы</span><span class="sxs-lookup"><span data-stu-id="f9238-106">Arguments</span></span>  
  
|<span data-ttu-id="f9238-107">Термин</span><span class="sxs-lookup"><span data-stu-id="f9238-107">Term</span></span>|<span data-ttu-id="f9238-108">Определение</span><span class="sxs-lookup"><span data-stu-id="f9238-108">Definition</span></span>|  
|---|---|  
|`symbol`|<span data-ttu-id="f9238-109">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="f9238-109">Required.</span></span> <span data-ttu-id="f9238-110">Определяемый символ.</span><span class="sxs-lookup"><span data-stu-id="f9238-110">The symbol to define.</span></span>|  
|`value`|<span data-ttu-id="f9238-111">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="f9238-111">Optional.</span></span> <span data-ttu-id="f9238-112">Значение, которому назначается `symbol`.</span><span class="sxs-lookup"><span data-stu-id="f9238-112">The value to assign `symbol`.</span></span> <span data-ttu-id="f9238-113">If `value` is a string, it must be surrounded by backslash/quotation-mark sequences (\\") instead of quotation marks.</span><span class="sxs-lookup"><span data-stu-id="f9238-113">If `value` is a string, it must be surrounded by backslash/quotation-mark sequences (\\") instead of quotation marks.</span></span> <span data-ttu-id="f9238-114">Если значение не задано, считается, что используется значение True.</span><span class="sxs-lookup"><span data-stu-id="f9238-114">If no value is specified, then it is taken to be True.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f9238-115">Заметки</span><span class="sxs-lookup"><span data-stu-id="f9238-115">Remarks</span></span>  
 <span data-ttu-id="f9238-116">The `-define` option has an effect similar to using a `#Const` preprocessor directive in your source file, except that constants defined with `-define` are public and apply to all files in the project.</span><span class="sxs-lookup"><span data-stu-id="f9238-116">The `-define` option has an effect similar to using a `#Const` preprocessor directive in your source file, except that constants defined with `-define` are public and apply to all files in the project.</span></span>  
  
 <span data-ttu-id="f9238-117">Вы можете использовать символы, созданные этим параметром с помощью директивы `#If`...`Then`...`#Else`, для условной компиляции исходных файлов.</span><span class="sxs-lookup"><span data-stu-id="f9238-117">You can use symbols created by this option with the `#If`...`Then`...`#Else` directive to compile source files conditionally.</span></span>  
  
 <span data-ttu-id="f9238-118">`-d` является краткой формой `-define`.</span><span class="sxs-lookup"><span data-stu-id="f9238-118">`-d` is the short form of `-define`.</span></span>  
  
 <span data-ttu-id="f9238-119">Вы можете определить несколько символов с помощью `-define`, разделяя их определения запятой.</span><span class="sxs-lookup"><span data-stu-id="f9238-119">You can define multiple symbols with `-define` by using a comma to separate symbol definitions.</span></span>  
  
|<span data-ttu-id="f9238-120">Задание параметра /define в интегрированной среде разработки Visual Studio</span><span class="sxs-lookup"><span data-stu-id="f9238-120">To set /define in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="f9238-121">1.  Have a project selected in **Solution Explorer**.</span><span class="sxs-lookup"><span data-stu-id="f9238-121">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="f9238-122">В меню **Проект** выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="f9238-122">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="f9238-123">2.  Click the **Compile** tab.</span><span class="sxs-lookup"><span data-stu-id="f9238-123">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="f9238-124">3.  Click **Advanced**.</span><span class="sxs-lookup"><span data-stu-id="f9238-124">3.  Click **Advanced**.</span></span><br /><span data-ttu-id="f9238-125">4.  Modify the value in the **Custom Constants** box.</span><span class="sxs-lookup"><span data-stu-id="f9238-125">4.  Modify the value in the **Custom Constants** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="f9238-126">Пример</span><span class="sxs-lookup"><span data-stu-id="f9238-126">Example</span></span>  
 <span data-ttu-id="f9238-127">В следующем примере кода определяются и используются две константы условной компиляции.</span><span class="sxs-lookup"><span data-stu-id="f9238-127">The following code defines and then uses two conditional compiler constants.</span></span>  
  
 [!code-vb[VbVbalrCompiler#45](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/Class1.vb#45)]  
  
## <a name="see-also"></a><span data-ttu-id="f9238-128">См. также</span><span class="sxs-lookup"><span data-stu-id="f9238-128">See also</span></span>

- [<span data-ttu-id="f9238-129">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="f9238-129">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="f9238-130">Директивы #If...Then...#Else</span><span class="sxs-lookup"><span data-stu-id="f9238-130">#If...Then...#Else Directives</span></span>](../../../visual-basic/language-reference/directives/if-then-else-directives.md)
- [<span data-ttu-id="f9238-131">Директива #Const</span><span class="sxs-lookup"><span data-stu-id="f9238-131">#Const Directive</span></span>](../../../visual-basic/language-reference/directives/const-directive.md)
- [<span data-ttu-id="f9238-132">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="f9238-132">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
