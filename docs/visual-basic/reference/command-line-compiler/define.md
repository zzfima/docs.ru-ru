---
title: /define (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- -d compiler option [Visual Basic]
- /d compiler option [Visual Basic]
- -define compiler option [Visual Basic]
- d compiler option [Visual Basic]
- /define compiler option [Visual Basic]
- define compiler option [Visual Basic]
ms.assetid: f735c57d-1cf9-4f2f-a26f-0de630fd4077
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 62669ec40803170cb623382b09472b82121d26bb
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="define-visual-basic"></a><span data-ttu-id="8b4dc-102">/define (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8b4dc-102">/define (Visual Basic)</span></span>
<span data-ttu-id="8b4dc-103">Задает константы условной компиляции.</span><span class="sxs-lookup"><span data-stu-id="8b4dc-103">Defines conditional compiler constants.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8b4dc-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8b4dc-104">Syntax</span></span>  
  
```  
/define:["]symbol[=value][,symbol[=value]]["]  
' -or-  
/d:["]symbol[=value][,symbol[=value]]["]  
```  
  
## <a name="arguments"></a><span data-ttu-id="8b4dc-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="8b4dc-105">Arguments</span></span>  
  
|<span data-ttu-id="8b4dc-106">Термин</span><span class="sxs-lookup"><span data-stu-id="8b4dc-106">Term</span></span>|<span data-ttu-id="8b4dc-107">Определение</span><span class="sxs-lookup"><span data-stu-id="8b4dc-107">Definition</span></span>|  
|---|---|  
|`symbol`|<span data-ttu-id="8b4dc-108">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="8b4dc-108">Required.</span></span> <span data-ttu-id="8b4dc-109">Определяемый символ.</span><span class="sxs-lookup"><span data-stu-id="8b4dc-109">The symbol to define.</span></span>|  
|`value`|<span data-ttu-id="8b4dc-110">Необязательно.</span><span class="sxs-lookup"><span data-stu-id="8b4dc-110">Optional.</span></span> <span data-ttu-id="8b4dc-111">Значение, которому назначается `symbol`.</span><span class="sxs-lookup"><span data-stu-id="8b4dc-111">The value to assign `symbol`.</span></span> <span data-ttu-id="8b4dc-112">Если `value` представляет собой строку, оно должно быть заключено в обратная косая черта и кавычка (\\«) кавычки.</span><span class="sxs-lookup"><span data-stu-id="8b4dc-112">If `value` is a string, it must be surrounded by backslash/quotation-mark sequences (\\") instead of quotation marks.</span></span> <span data-ttu-id="8b4dc-113">Если значение не задано, считается, что используется значение True.</span><span class="sxs-lookup"><span data-stu-id="8b4dc-113">If no value is specified, then it is taken to be True.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8b4dc-114">Примечания</span><span class="sxs-lookup"><span data-stu-id="8b4dc-114">Remarks</span></span>  
 <span data-ttu-id="8b4dc-115">Влияние параметра `/define` похоже на использование директивы препроцессора `#Const` в исходном файле, за исключением того, что определенные с помощью `/define` константы являются общими и применяются ко всем файлам в проекте.</span><span class="sxs-lookup"><span data-stu-id="8b4dc-115">The `/define` option has an effect  similar to using a `#Const` preprocessor directive in your source file, except that constants defined with `/define` are public and apply to all files in the project.</span></span>  
  
 <span data-ttu-id="8b4dc-116">Вы можете использовать символы, созданные этим параметром с помощью директивы `#If`...`Then`...`#Else`, для условной компиляции исходных файлов.</span><span class="sxs-lookup"><span data-stu-id="8b4dc-116">You can use symbols created by this option with the `#If`...`Then`...`#Else` directive to compile source files conditionally.</span></span>  
  
 <span data-ttu-id="8b4dc-117">`/d` является краткой формой `/define`.</span><span class="sxs-lookup"><span data-stu-id="8b4dc-117">`/d` is the short form of `/define`.</span></span>  
  
 <span data-ttu-id="8b4dc-118">Вы можете определить несколько символов с помощью `/define`, разделяя их определения запятой.</span><span class="sxs-lookup"><span data-stu-id="8b4dc-118">You can define multiple symbols with `/define` by using a comma to separate symbol definitions.</span></span>  
  
|<span data-ttu-id="8b4dc-119">Задание параметра /define в интегрированной среде разработки Visual Studio</span><span class="sxs-lookup"><span data-stu-id="8b4dc-119">To set /define in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="8b4dc-120">1.  Выберите проект в **Обозревателе решений**.</span><span class="sxs-lookup"><span data-stu-id="8b4dc-120">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="8b4dc-121">В меню **Проект** выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="8b4dc-121">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="8b4dc-122">2.  Откройте вкладку **Компиляция**.</span><span class="sxs-lookup"><span data-stu-id="8b4dc-122">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="8b4dc-123">3.  Нажмите кнопку **Дополнительно**.</span><span class="sxs-lookup"><span data-stu-id="8b4dc-123">3.  Click **Advanced**.</span></span><br /><span data-ttu-id="8b4dc-124">4.  Измените значение в **пользовательские константы** поле.</span><span class="sxs-lookup"><span data-stu-id="8b4dc-124">4.  Modify the value in the **Custom Constants** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="8b4dc-125">Пример</span><span class="sxs-lookup"><span data-stu-id="8b4dc-125">Example</span></span>  
 <span data-ttu-id="8b4dc-126">В следующем примере кода определяются и используются две константы условной компиляции.</span><span class="sxs-lookup"><span data-stu-id="8b4dc-126">The following code defines and then uses two conditional compiler constants.</span></span>  
  
 [!code-vb[VbVbalrCompiler#45](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/define_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="8b4dc-127">См. также</span><span class="sxs-lookup"><span data-stu-id="8b4dc-127">See Also</span></span>  
 [<span data-ttu-id="8b4dc-128">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="8b4dc-128">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="8b4dc-129">Директивы #If...Then...#Else</span><span class="sxs-lookup"><span data-stu-id="8b4dc-129">#If...Then...#Else Directives</span></span>](../../../visual-basic/language-reference/directives/if-then-else-directives.md)  
 [<span data-ttu-id="8b4dc-130">Директива #Const</span><span class="sxs-lookup"><span data-stu-id="8b4dc-130">#Const Directive</span></span>](../../../visual-basic/language-reference/directives/const-directive.md)  
 [<span data-ttu-id="8b4dc-131">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="8b4dc-131">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
