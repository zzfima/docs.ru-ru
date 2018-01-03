---
title: "Соглашения об именах Visual Basic"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- names [Visual Basic], Visual Basic rules
- naming conventions
- naming conventions [Visual Basic], Visual Basic
- Visual Basic code, naming conventions
- conventions [Visual Basic], Visual Basic coding
- names [Visual Basic], naming conventions
- naming conventions [Visual Basic], classes
ms.assetid: 164949a4-2a7c-4736-9d82-9c3078e2e56c
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 97f02fd85d4796d6799a8a5b40a9137eeb79a93f
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="visual-basic-naming-conventions"></a><span data-ttu-id="5c26b-102">Соглашения об именах Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5c26b-102">Visual Basic Naming Conventions</span></span>
<span data-ttu-id="5c26b-103">При задании имени элемента в приложении Visual Basic, первый символ с тем же именем необходимо буквы алфавита или знака подчеркивания.</span><span class="sxs-lookup"><span data-stu-id="5c26b-103">When you name an element in your Visual Basic application, the first character of that name must be an alphabetic character or an underscore.</span></span> <span data-ttu-id="5c26b-104">Обратите внимание, что имена, начинающиеся с символа подчеркивания, не совместимы с [независимость от языка и независимые от языка компоненты](../../../standard/language-independence-and-language-independent-components.md) (CLS).</span><span class="sxs-lookup"><span data-stu-id="5c26b-104">Note, however, that names beginning with an underscore are not compliant with the [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS).</span></span>  
  
 <span data-ttu-id="5c26b-105">Следующие советы для именования.</span><span class="sxs-lookup"><span data-stu-id="5c26b-105">The following suggestions apply to naming.</span></span>  
  
-   <span data-ttu-id="5c26b-106">Начинать каждое отдельное слово в имени с прописной буквы, например `FindLastRecord` и `RedrawMyForm`.</span><span class="sxs-lookup"><span data-stu-id="5c26b-106">Begin each separate word in a name with a capital letter, as in `FindLastRecord` and `RedrawMyForm`.</span></span>  
  
-   <span data-ttu-id="5c26b-107">Начинать имена функций и методов с глагола, например `InitNameArray` или `CloseDialog`.</span><span class="sxs-lookup"><span data-stu-id="5c26b-107">Begin function and method names with a verb, as in `InitNameArray` or `CloseDialog`.</span></span>  
  
-   <span data-ttu-id="5c26b-108">Начинать класс, структура, модуль и имена свойств с существительного, например `EmployeeName` или `CarAccessory`.</span><span class="sxs-lookup"><span data-stu-id="5c26b-108">Begin class, structure, module, and property names with a noun, as in `EmployeeName` or `CarAccessory`.</span></span>  
  
-   <span data-ttu-id="5c26b-109">Первым в имени интерфейса с префиксом «I», следуют существительного или субстантивное словосочетание, таких как `IComponent`, или прилагательное, описывающее поведение интерфейса, например `IPersistable`.</span><span class="sxs-lookup"><span data-stu-id="5c26b-109">Begin interface names with the prefix "I", followed by a noun or a noun phrase, like `IComponent`, or with an adjective describing the interface's behavior, like `IPersistable`.</span></span> <span data-ttu-id="5c26b-110">Не используйте символ подчеркивания и аббревиатуры, поскольку аббревиатуры могут ввести в заблуждение.</span><span class="sxs-lookup"><span data-stu-id="5c26b-110">Do not use the underscore, and use abbreviations sparingly, because abbreviations can cause confusion.</span></span>  
  
-   <span data-ttu-id="5c26b-111">Имена обработчиков событий начинать с имени существительного, описывающего тип события, за которым следует "`EventHandler`«как в следующем примере, суффикс»`MouseEventHandler`».</span><span class="sxs-lookup"><span data-stu-id="5c26b-111">Begin event handler names with a noun describing the type of event followed by the "`EventHandler`" suffix, as in "`MouseEventHandler`".</span></span>  
  
-   <span data-ttu-id="5c26b-112">К именам аргументов классов событий следует добавлять «`EventArgs`» суффикс.</span><span class="sxs-lookup"><span data-stu-id="5c26b-112">In names of event argument classes, include the "`EventArgs`" suffix.</span></span>  
  
-   <span data-ttu-id="5c26b-113">Если событие имеет смысл «до» или «после», используйте суффикс в настоящее или прошедшее время, как в «`ControlAdd`«или»`ControlAdded`».</span><span class="sxs-lookup"><span data-stu-id="5c26b-113">If an event has a concept of "before" or "after," use a suffix in present or past tense, as in "`ControlAdd`" or "`ControlAdded`".</span></span>  
  
-   <span data-ttu-id="5c26b-114">Для длинных или часто используемых терминов используйте аббревиатуры разумной длины, например, «HTML» вместо «Язык HTML».</span><span class="sxs-lookup"><span data-stu-id="5c26b-114">For long or frequently used terms, use abbreviations to keep name lengths reasonable, for example, "HTML", instead of "Hypertext Markup Language".</span></span> <span data-ttu-id="5c26b-115">В общем случае имена переменных длиной более 32 символов трудно читать на мониторе с низким разрешением.</span><span class="sxs-lookup"><span data-stu-id="5c26b-115">In general, variable names greater than 32 characters are difficult to read on a monitor set to a low resolution.</span></span> <span data-ttu-id="5c26b-116">Кроме того убедитесь, что ваш сокращения согласованы во всем приложении.</span><span class="sxs-lookup"><span data-stu-id="5c26b-116">Also, make sure your abbreviations are consistent throughout the entire application.</span></span> <span data-ttu-id="5c26b-117">Переключение случайным образом в проекте между «HTML» и «Язык HTML» может привести к путанице.</span><span class="sxs-lookup"><span data-stu-id="5c26b-117">Randomly switching in a project between "HTML" and "Hypertext Markup Language" can lead to confusion.</span></span>  
  
-   <span data-ttu-id="5c26b-118">Избегайте использования во внутренней области имен, которые совпадают с именами во внешней области.</span><span class="sxs-lookup"><span data-stu-id="5c26b-118">Avoid using names in an inner scope that are the same as names in an outer scope.</span></span> <span data-ttu-id="5c26b-119">Ошибки могут привести случае доступа к неправильной переменной.</span><span class="sxs-lookup"><span data-stu-id="5c26b-119">Errors can result if the wrong variable is accessed.</span></span> <span data-ttu-id="5c26b-120">Если конфликт возникает между переменной и ключевого слова с тем же именем, необходимо указать ключевое слово перед ее именем соответствующей библиотеки типов.</span><span class="sxs-lookup"><span data-stu-id="5c26b-120">If a conflict occurs between a variable and the keyword of the same name, you must identify the keyword by preceding it with the appropriate type library.</span></span> <span data-ttu-id="5c26b-121">Например, если есть переменная `Date`, можно использовать встроенную функцию `Date` функции только путем вызова <xref:System.DateTime.Date%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="5c26b-121">For example, if you have a variable called `Date`, you can use the intrinsic `Date` function only by calling <xref:System.DateTime.Date%2A?displayProperty=nameWithType>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c26b-122">См. также</span><span class="sxs-lookup"><span data-stu-id="5c26b-122">See Also</span></span>  
 [<span data-ttu-id="5c26b-123">Ключевые слова как имена элементов в коде</span><span class="sxs-lookup"><span data-stu-id="5c26b-123">Keywords as Element Names in Code</span></span>](../../../visual-basic/programming-guide/program-structure/keywords-as-element-names-in-code.md)  
 [<span data-ttu-id="5c26b-124">Me, My, MyBase и MyClass</span><span class="sxs-lookup"><span data-stu-id="5c26b-124">Me, My, MyBase, and MyClass</span></span>](../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)  
 [<span data-ttu-id="5c26b-125">Имена объявленных элементов</span><span class="sxs-lookup"><span data-stu-id="5c26b-125">Declared Element Names</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)  
 [<span data-ttu-id="5c26b-126">Соглашения о структуре программы и коде</span><span class="sxs-lookup"><span data-stu-id="5c26b-126">Program Structure and Code Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)  
 [<span data-ttu-id="5c26b-127">Справочник по языку Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5c26b-127">Visual Basic Language Reference</span></span>](../../../visual-basic/language-reference/index.md)
