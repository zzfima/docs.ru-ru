---
title: — Определение (Visual Basic)
ms.date: 03/10/2018
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- -d compiler option [Visual Basic]
- /d compiler option [Visual Basic]
- -define compiler option [Visual Basic]
- d compiler option [Visual Basic]
- /define compiler option [Visual Basic]
- define compiler option [Visual Basic]
ms.assetid: f735c57d-1cf9-4f2f-a26f-0de630fd4077
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 136339c84ce80bff790c6683eef76065fb6d71ef
ms.sourcegitcommit: 498799639937c89de777361aab74261efe7b79ea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/22/2018
---
# <a name="-define-visual-basic"></a><span data-ttu-id="0aeaa-102">— Определение (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0aeaa-102">-define (Visual Basic)</span></span>
<span data-ttu-id="0aeaa-103">Задает константы условной компиляции.</span><span class="sxs-lookup"><span data-stu-id="0aeaa-103">Defines conditional compiler constants.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0aeaa-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0aeaa-104">Syntax</span></span>  
  
```  
-define:["]symbol[=value][,symbol[=value]]["]  
' -or-  
-d:["]symbol[=value][,symbol[=value]]["]  
```  
  
## <a name="arguments"></a><span data-ttu-id="0aeaa-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="0aeaa-105">Arguments</span></span>  
  
|<span data-ttu-id="0aeaa-106">Термин</span><span class="sxs-lookup"><span data-stu-id="0aeaa-106">Term</span></span>|<span data-ttu-id="0aeaa-107">Определение</span><span class="sxs-lookup"><span data-stu-id="0aeaa-107">Definition</span></span>|  
|---|---|  
|`symbol`|<span data-ttu-id="0aeaa-108">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="0aeaa-108">Required.</span></span> <span data-ttu-id="0aeaa-109">Определяемый символ.</span><span class="sxs-lookup"><span data-stu-id="0aeaa-109">The symbol to define.</span></span>|  
|`value`|<span data-ttu-id="0aeaa-110">Необязательно.</span><span class="sxs-lookup"><span data-stu-id="0aeaa-110">Optional.</span></span> <span data-ttu-id="0aeaa-111">Значение, которому назначается `symbol`.</span><span class="sxs-lookup"><span data-stu-id="0aeaa-111">The value to assign `symbol`.</span></span> <span data-ttu-id="0aeaa-112">Если `value` представляет собой строку, оно должно быть заключено в обратная косая черта и кавычка (\\«) кавычки.</span><span class="sxs-lookup"><span data-stu-id="0aeaa-112">If `value` is a string, it must be surrounded by backslash/quotation-mark sequences (\\") instead of quotation marks.</span></span> <span data-ttu-id="0aeaa-113">Если значение не задано, считается, что используется значение True.</span><span class="sxs-lookup"><span data-stu-id="0aeaa-113">If no value is specified, then it is taken to be True.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0aeaa-114">Примечания</span><span class="sxs-lookup"><span data-stu-id="0aeaa-114">Remarks</span></span>  
 <span data-ttu-id="0aeaa-115">`-define` Параметр действует аналогично использованию `#Const` директива препроцессора в исходном файле, за исключением того, что константы, определенные с `-define` являются открытыми и применяются ко всем файлам в проекте.</span><span class="sxs-lookup"><span data-stu-id="0aeaa-115">The `-define` option has an effect similar to using a `#Const` preprocessor directive in your source file, except that constants defined with `-define` are public and apply to all files in the project.</span></span>  
  
 <span data-ttu-id="0aeaa-116">Вы можете использовать символы, созданные этим параметром с помощью директивы `#If`...`Then`...`#Else`, для условной компиляции исходных файлов.</span><span class="sxs-lookup"><span data-stu-id="0aeaa-116">You can use symbols created by this option with the `#If`...`Then`...`#Else` directive to compile source files conditionally.</span></span>  
  
 <span data-ttu-id="0aeaa-117">`-d` является краткой формой `-define`.</span><span class="sxs-lookup"><span data-stu-id="0aeaa-117">`-d` is the short form of `-define`.</span></span>  
  
 <span data-ttu-id="0aeaa-118">Вы можете определить несколько символов с помощью `-define`, разделяя их определения запятой.</span><span class="sxs-lookup"><span data-stu-id="0aeaa-118">You can define multiple symbols with `-define` by using a comma to separate symbol definitions.</span></span>  
  
|<span data-ttu-id="0aeaa-119">Задание параметра /define в интегрированной среде разработки Visual Studio</span><span class="sxs-lookup"><span data-stu-id="0aeaa-119">To set /define in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="0aeaa-120">1.  Выберите проект в **Обозревателе решений**.</span><span class="sxs-lookup"><span data-stu-id="0aeaa-120">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="0aeaa-121">В меню **Проект** выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="0aeaa-121">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="0aeaa-122">2.  Откройте вкладку **Компиляция**.</span><span class="sxs-lookup"><span data-stu-id="0aeaa-122">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="0aeaa-123">3.  Нажмите кнопку **Дополнительно**.</span><span class="sxs-lookup"><span data-stu-id="0aeaa-123">3.  Click **Advanced**.</span></span><br /><span data-ttu-id="0aeaa-124">4.  Измените значение в **пользовательские константы** поле.</span><span class="sxs-lookup"><span data-stu-id="0aeaa-124">4.  Modify the value in the **Custom Constants** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="0aeaa-125">Пример</span><span class="sxs-lookup"><span data-stu-id="0aeaa-125">Example</span></span>  
 <span data-ttu-id="0aeaa-126">В следующем примере кода определяются и используются две константы условной компиляции.</span><span class="sxs-lookup"><span data-stu-id="0aeaa-126">The following code defines and then uses two conditional compiler constants.</span></span>  
  
 [!code-vb[VbVbalrCompiler#45](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/define_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="0aeaa-127">См. также</span><span class="sxs-lookup"><span data-stu-id="0aeaa-127">See Also</span></span>  
 [<span data-ttu-id="0aeaa-128">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="0aeaa-128">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="0aeaa-129">Директивы #If...Then...#Else</span><span class="sxs-lookup"><span data-stu-id="0aeaa-129">#If...Then...#Else Directives</span></span>](../../../visual-basic/language-reference/directives/if-then-else-directives.md)  
 [<span data-ttu-id="0aeaa-130">Директива #Const</span><span class="sxs-lookup"><span data-stu-id="0aeaa-130">#Const Directive</span></span>](../../../visual-basic/language-reference/directives/const-directive.md)  
 [<span data-ttu-id="0aeaa-131">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="0aeaa-131">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
