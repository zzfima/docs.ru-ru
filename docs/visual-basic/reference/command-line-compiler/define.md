---
title: "/ define (Visual Basic) | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- -d compiler option [Visual Basic]
- /d compiler option [Visual Basic]
- -define compiler option [Visual Basic]
- d compiler option [Visual Basic]
- /define compiler option [Visual Basic]
- define compiler option [Visual Basic]
ms.assetid: f735c57d-1cf9-4f2f-a26f-0de630fd4077
caps.latest.revision: 15
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: e4eac32b4ab7259b9d3fd2ec37e21406c4cec326
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="define-visual-basic"></a><span data-ttu-id="1e7af-102">/define (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1e7af-102">/define (Visual Basic)</span></span>
<span data-ttu-id="1e7af-103">Задает константы условной компиляции.</span><span class="sxs-lookup"><span data-stu-id="1e7af-103">Defines conditional compiler constants.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1e7af-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1e7af-104">Syntax</span></span>  
  
```  
/define:["]symbol[=value][,symbol[=value]]["]  
' -or-  
/d:["]symbol[=value][,symbol[=value]]["]  
```  
  
## <a name="arguments"></a><span data-ttu-id="1e7af-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="1e7af-105">Arguments</span></span>  
  
|<span data-ttu-id="1e7af-106">Термин</span><span class="sxs-lookup"><span data-stu-id="1e7af-106">Term</span></span>|<span data-ttu-id="1e7af-107">Определение</span><span class="sxs-lookup"><span data-stu-id="1e7af-107">Definition</span></span>|  
|---|---|  
|`symbol`|<span data-ttu-id="1e7af-108">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="1e7af-108">Required.</span></span> <span data-ttu-id="1e7af-109">Определяемый символ.</span><span class="sxs-lookup"><span data-stu-id="1e7af-109">The symbol to define.</span></span>|  
|`value`|<span data-ttu-id="1e7af-110">Необязательно.</span><span class="sxs-lookup"><span data-stu-id="1e7af-110">Optional.</span></span> <span data-ttu-id="1e7af-111">Значение, которому назначается `symbol`.</span><span class="sxs-lookup"><span data-stu-id="1e7af-111">The value to assign `symbol`.</span></span> <span data-ttu-id="1e7af-112">Если `value` является строкой, оно должно быть заключено в обратная косая черта и кавычка (\\») вместо кавычек.</span><span class="sxs-lookup"><span data-stu-id="1e7af-112">If `value` is a string, it must be surrounded by backslash/quotation-mark sequences (\\") instead of quotation marks.</span></span> <span data-ttu-id="1e7af-113">Если значение не задано, считается, что используется значение True.</span><span class="sxs-lookup"><span data-stu-id="1e7af-113">If no value is specified, then it is taken to be True.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1e7af-114">Примечания</span><span class="sxs-lookup"><span data-stu-id="1e7af-114">Remarks</span></span>  
 <span data-ttu-id="1e7af-115">Влияние параметра `/define` похоже на использование директивы препроцессора `#Const` в исходном файле, за исключением того, что определенные с помощью `/define` константы являются общими и применяются ко всем файлам в проекте.</span><span class="sxs-lookup"><span data-stu-id="1e7af-115">The `/define` option has an effect  similar to using a `#Const` preprocessor directive in your source file, except that constants defined with `/define` are public and apply to all files in the project.</span></span>  
  
 <span data-ttu-id="1e7af-116">Вы можете использовать символы, созданные этим параметром с помощью директивы `#If`...`Then`...`#Else`, для условной компиляции исходных файлов.</span><span class="sxs-lookup"><span data-stu-id="1e7af-116">You can use symbols created by this option with the `#If`...`Then`...`#Else` directive to compile source files conditionally.</span></span>  
  
 <span data-ttu-id="1e7af-117">`/d` является краткой формой `/define`.</span><span class="sxs-lookup"><span data-stu-id="1e7af-117">`/d` is the short form of `/define`.</span></span>  
  
 <span data-ttu-id="1e7af-118">Вы можете определить несколько символов с помощью `/define`, разделяя их определения запятой.</span><span class="sxs-lookup"><span data-stu-id="1e7af-118">You can define multiple symbols with `/define` by using a comma to separate symbol definitions.</span></span>  
  
|<span data-ttu-id="1e7af-119">Задание параметра /define в интегрированной среде разработки Visual Studio</span><span class="sxs-lookup"><span data-stu-id="1e7af-119">To set /define in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="1e7af-120">1.  Выберите проект в **Обозревателе решений**.</span><span class="sxs-lookup"><span data-stu-id="1e7af-120">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="1e7af-121">На **проекта** меню, щелкните **свойства**.</span><span class="sxs-lookup"><span data-stu-id="1e7af-121">On the **Project** menu, click **Properties**.</span></span> <span data-ttu-id="1e7af-122">Дополнительные сведения см. в разделе [Знакомство с конструктором проектов](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span><span class="sxs-lookup"><span data-stu-id="1e7af-122">For more information, see [Introduction to the Project Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span></span><br /><span data-ttu-id="1e7af-123">2.  Откройте вкладку **Компиляция**.</span><span class="sxs-lookup"><span data-stu-id="1e7af-123">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="1e7af-124">3.  Нажмите кнопку **Дополнительно**.</span><span class="sxs-lookup"><span data-stu-id="1e7af-124">3.  Click **Advanced**.</span></span><br /><span data-ttu-id="1e7af-125">4.  Измените значение в **настраиваемые константы** поле.</span><span class="sxs-lookup"><span data-stu-id="1e7af-125">4.  Modify the value in the **Custom Constants** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="1e7af-126">Пример</span><span class="sxs-lookup"><span data-stu-id="1e7af-126">Example</span></span>  
 <span data-ttu-id="1e7af-127">В следующем примере кода определяются и используются две константы условной компиляции.</span><span class="sxs-lookup"><span data-stu-id="1e7af-127">The following code defines and then uses two conditional compiler constants.</span></span>  
  
 <span data-ttu-id="1e7af-128">[!code-vb[VbVbalrCompiler&#45;](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/define_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="1e7af-128">[!code-vb[VbVbalrCompiler#45](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/define_1.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e7af-129">См. также</span><span class="sxs-lookup"><span data-stu-id="1e7af-129">See Also</span></span>  
 <span data-ttu-id="1e7af-130">[Компилятор командной строки Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="1e7af-130">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="1e7af-131"> [#If... Then... #Else директивы](../../../visual-basic/language-reference/directives/if-then-else-directives.md) </span><span class="sxs-lookup"><span data-stu-id="1e7af-131"> [#If...Then...#Else Directives](../../../visual-basic/language-reference/directives/if-then-else-directives.md) </span></span>  
<span data-ttu-id="1e7af-132"> [# Директива const](../../../visual-basic/language-reference/directives/const-directive.md) </span><span class="sxs-lookup"><span data-stu-id="1e7af-132"> [#Const Directive](../../../visual-basic/language-reference/directives/const-directive.md) </span></span>  
<span data-ttu-id="1e7af-133"> [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span><span class="sxs-lookup"><span data-stu-id="1e7af-133"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span></span>
