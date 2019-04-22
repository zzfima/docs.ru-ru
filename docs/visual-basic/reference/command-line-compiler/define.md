---
title: -Определение (Visual Basic)
ms.date: 03/10/2018
helpviewer_keywords:
- -d compiler option [Visual Basic]
- /d compiler option [Visual Basic]
- -define compiler option [Visual Basic]
- d compiler option [Visual Basic]
- /define compiler option [Visual Basic]
- define compiler option [Visual Basic]
ms.assetid: f735c57d-1cf9-4f2f-a26f-0de630fd4077
ms.openlocfilehash: d0a483e7a3c9e9863db39e89d655cf172c1e8c81
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "58834313"
---
# <a name="-define-visual-basic"></a><span data-ttu-id="57e7f-102">-Определение (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="57e7f-102">-define (Visual Basic)</span></span>
<span data-ttu-id="57e7f-103">Задает константы условной компиляции.</span><span class="sxs-lookup"><span data-stu-id="57e7f-103">Defines conditional compiler constants.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="57e7f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="57e7f-104">Syntax</span></span>  
  
```  
-define:["]symbol[=value][,symbol[=value]]["]  
' -or-  
-d:["]symbol[=value][,symbol[=value]]["]  
```  
  
## <a name="arguments"></a><span data-ttu-id="57e7f-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="57e7f-105">Arguments</span></span>  
  
|<span data-ttu-id="57e7f-106">Термин</span><span class="sxs-lookup"><span data-stu-id="57e7f-106">Term</span></span>|<span data-ttu-id="57e7f-107">Определение</span><span class="sxs-lookup"><span data-stu-id="57e7f-107">Definition</span></span>|  
|---|---|  
|`symbol`|<span data-ttu-id="57e7f-108">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="57e7f-108">Required.</span></span> <span data-ttu-id="57e7f-109">Определяемый символ.</span><span class="sxs-lookup"><span data-stu-id="57e7f-109">The symbol to define.</span></span>|  
|`value`|<span data-ttu-id="57e7f-110">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="57e7f-110">Optional.</span></span> <span data-ttu-id="57e7f-111">Значение, которому назначается `symbol`.</span><span class="sxs-lookup"><span data-stu-id="57e7f-111">The value to assign `symbol`.</span></span> <span data-ttu-id="57e7f-112">Если `value` представляет собой строку, оно должно быть заключено в обратная косая черта и кавычка (\\«) кавычки.</span><span class="sxs-lookup"><span data-stu-id="57e7f-112">If `value` is a string, it must be surrounded by backslash/quotation-mark sequences (\\") instead of quotation marks.</span></span> <span data-ttu-id="57e7f-113">Если значение не задано, считается, что используется значение True.</span><span class="sxs-lookup"><span data-stu-id="57e7f-113">If no value is specified, then it is taken to be True.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="57e7f-114">Примечания</span><span class="sxs-lookup"><span data-stu-id="57e7f-114">Remarks</span></span>  
 <span data-ttu-id="57e7f-115">`-define` Параметр действует аналогично использованию `#Const` директивы препроцессора в файле исходного кода, за исключением этой константы, определенные с помощью `-define` являются общими и применяются ко всем файлам в проекте.</span><span class="sxs-lookup"><span data-stu-id="57e7f-115">The `-define` option has an effect similar to using a `#Const` preprocessor directive in your source file, except that constants defined with `-define` are public and apply to all files in the project.</span></span>  
  
 <span data-ttu-id="57e7f-116">Вы можете использовать символы, созданные этим параметром с помощью директивы `#If`...`Then`...`#Else`, для условной компиляции исходных файлов.</span><span class="sxs-lookup"><span data-stu-id="57e7f-116">You can use symbols created by this option with the `#If`...`Then`...`#Else` directive to compile source files conditionally.</span></span>  
  
 <span data-ttu-id="57e7f-117">`-d` является краткой формой `-define`.</span><span class="sxs-lookup"><span data-stu-id="57e7f-117">`-d` is the short form of `-define`.</span></span>  
  
 <span data-ttu-id="57e7f-118">Вы можете определить несколько символов с помощью `-define`, разделяя их определения запятой.</span><span class="sxs-lookup"><span data-stu-id="57e7f-118">You can define multiple symbols with `-define` by using a comma to separate symbol definitions.</span></span>  
  
|<span data-ttu-id="57e7f-119">Задание параметра /define в интегрированной среде разработки Visual Studio</span><span class="sxs-lookup"><span data-stu-id="57e7f-119">To set /define in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="57e7f-120">1.  Выберите проект в **Обозревателе решений**.</span><span class="sxs-lookup"><span data-stu-id="57e7f-120">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="57e7f-121">В меню **Проект** выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="57e7f-121">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="57e7f-122">2.  Откройте вкладку **Компиляция**.</span><span class="sxs-lookup"><span data-stu-id="57e7f-122">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="57e7f-123">3.  Нажмите кнопку **Дополнительно**.</span><span class="sxs-lookup"><span data-stu-id="57e7f-123">3.  Click **Advanced**.</span></span><br /><span data-ttu-id="57e7f-124">4.  Измените значение в **настраиваемые константы** поле.</span><span class="sxs-lookup"><span data-stu-id="57e7f-124">4.  Modify the value in the **Custom Constants** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="57e7f-125">Пример</span><span class="sxs-lookup"><span data-stu-id="57e7f-125">Example</span></span>  
 <span data-ttu-id="57e7f-126">В следующем примере кода определяются и используются две константы условной компиляции.</span><span class="sxs-lookup"><span data-stu-id="57e7f-126">The following code defines and then uses two conditional compiler constants.</span></span>  
  
 [!code-vb[VbVbalrCompiler#45](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/Class1.vb#45)]  
  
## <a name="see-also"></a><span data-ttu-id="57e7f-127">См. также</span><span class="sxs-lookup"><span data-stu-id="57e7f-127">See also</span></span>

- [<span data-ttu-id="57e7f-128">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="57e7f-128">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="57e7f-129">Директивы #If...Then...#Else</span><span class="sxs-lookup"><span data-stu-id="57e7f-129">#If...Then...#Else Directives</span></span>](../../../visual-basic/language-reference/directives/if-then-else-directives.md)
- [<span data-ttu-id="57e7f-130">Директива #Const</span><span class="sxs-lookup"><span data-stu-id="57e7f-130">#Const Directive</span></span>](../../../visual-basic/language-reference/directives/const-directive.md)
- [<span data-ttu-id="57e7f-131">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="57e7f-131">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
