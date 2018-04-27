---
title: Ограничения в Visual Basic
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- limits
- limitations [Visual Basic]
- limitations
- limits, Visual Basic code
- Visual Basic code, limitations
ms.assetid: cf1646b7-5d24-48c6-9616-bda8a4849d91
caps.latest.revision: 14
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d06b743996969dcd7fc022bbb8ab625f3a151137
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="visual-basic-limitations"></a><span data-ttu-id="c3ccd-102">Ограничения в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c3ccd-102">Visual Basic Limitations</span></span>
<span data-ttu-id="c3ccd-103">Более ранних версиях Visual Basic накладывались ограничения на код, например длина имени переменной, количество переменных в модуле и размер модуля.</span><span class="sxs-lookup"><span data-stu-id="c3ccd-103">Earlier versions of Visual Basic enforced boundaries in code, such as the length of variable names, the number of variables allowed in modules, and module size.</span></span> <span data-ttu-id="c3ccd-104">В Visual Basic .NET эти ограничения были ослаблены, предоставляя большую свободу в написании и упорядочении кода.</span><span class="sxs-lookup"><span data-stu-id="c3ccd-104">In Visual Basic .NET, these restrictions have been relaxed, giving you greater freedom in writing and arranging your code.</span></span>  
  
 <span data-ttu-id="c3ccd-105">Физические ограничения зависят больше от памяти времени выполнения, чем на вопросы во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="c3ccd-105">Physical limits are dependent more on run-time memory than on compile-time considerations.</span></span> <span data-ttu-id="c3ccd-106">Если следовать разумным правилам программирования и разделять большие приложения на несколько классов и модулей, имеется очень мало вероятность возникновения внутреннее ограничение Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="c3ccd-106">If you use prudent programming practices, and divide large applications into multiple classes and modules, then there is very little chance of encountering an internal Visual Basic limitation.</span></span>  
  
 <span data-ttu-id="c3ccd-107">Ниже приведены некоторые ограничения, которые могут возникнуть в крайних случаях.</span><span class="sxs-lookup"><span data-stu-id="c3ccd-107">The following are some limitations that you might encounter in extreme cases:</span></span>  
  
-   <span data-ttu-id="c3ccd-108">**Длина имени.**</span><span class="sxs-lookup"><span data-stu-id="c3ccd-108">**Name Length.**</span></span> <span data-ttu-id="c3ccd-109">Нет максимальное количество символов в имени каждого объявленного элемента программирования.</span><span class="sxs-lookup"><span data-stu-id="c3ccd-109">There is a maximum number of characters for the name of every declared programming element.</span></span> <span data-ttu-id="c3ccd-110">Этот максимум применяется к полной уточняющей строке, если полное имя элемента.</span><span class="sxs-lookup"><span data-stu-id="c3ccd-110">This maximum applies to an entire qualification string if the element name is qualified.</span></span> <span data-ttu-id="c3ccd-111">В разделе [имена объявленных элементов](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="c3ccd-111">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
-   <span data-ttu-id="c3ccd-112">**Длина строки.**</span><span class="sxs-lookup"><span data-stu-id="c3ccd-112">**Line Length.**</span></span> <span data-ttu-id="c3ccd-113">Имеется более 65 535 знаков в физической строке исходного кода.</span><span class="sxs-lookup"><span data-stu-id="c3ccd-113">There is a maximum of 65535 characters in a physical line of source code.</span></span> <span data-ttu-id="c3ccd-114">Логическая строка исходного кода может быть больше, если вы используете символы продолжения строки.</span><span class="sxs-lookup"><span data-stu-id="c3ccd-114">The logical source code line can be longer if you use line continuation characters.</span></span> <span data-ttu-id="c3ccd-115">В разделе [как: разбиение и объединение инструкций в коде](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md).</span><span class="sxs-lookup"><span data-stu-id="c3ccd-115">See [How to: Break and Combine Statements in Code](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md).</span></span>  
  
-   <span data-ttu-id="c3ccd-116">**Размерность массива.**</span><span class="sxs-lookup"><span data-stu-id="c3ccd-116">**Array Dimensions.**</span></span> <span data-ttu-id="c3ccd-117">Имеется максимальное число измерений, которые можно объявить для массива.</span><span class="sxs-lookup"><span data-stu-id="c3ccd-117">There is a maximum number of dimensions you can declare for an array.</span></span> <span data-ttu-id="c3ccd-118">Это ограничивает количество индексов, которые можно использовать для указания элемента массива.</span><span class="sxs-lookup"><span data-stu-id="c3ccd-118">This limits how many indexes you can use to specify an array element.</span></span> <span data-ttu-id="c3ccd-119">В разделе [массива измерений в Visual Basic](../../../visual-basic/programming-guide/language-features/arrays/array-dimensions.md).</span><span class="sxs-lookup"><span data-stu-id="c3ccd-119">See [Array Dimensions in Visual Basic](../../../visual-basic/programming-guide/language-features/arrays/array-dimensions.md).</span></span>  
  
-   <span data-ttu-id="c3ccd-120">**Длина строки.**</span><span class="sxs-lookup"><span data-stu-id="c3ccd-120">**String Length.**</span></span> <span data-ttu-id="c3ccd-121">Нет максимальное количество символов Юникода, которые можно хранить в одной строке.</span><span class="sxs-lookup"><span data-stu-id="c3ccd-121">There is a maximum number of Unicode characters you can store in a single string.</span></span> <span data-ttu-id="c3ccd-122">В разделе [строковый тип данных](../../../visual-basic/language-reference/data-types/string-data-type.md).</span><span class="sxs-lookup"><span data-stu-id="c3ccd-122">See [String Data Type](../../../visual-basic/language-reference/data-types/string-data-type.md).</span></span>  
  
-   <span data-ttu-id="c3ccd-123">**Длина строки в среде.**</span><span class="sxs-lookup"><span data-stu-id="c3ccd-123">**Environment String Length.**</span></span> <span data-ttu-id="c3ccd-124">Нет до 32768 символов для любой строки среды, используется в качестве аргумента командной строки.</span><span class="sxs-lookup"><span data-stu-id="c3ccd-124">There is a maximum of 32768 characters for any environment string used as a command-line argument.</span></span> <span data-ttu-id="c3ccd-125">Это ограничение для всех платформ.</span><span class="sxs-lookup"><span data-stu-id="c3ccd-125">This is a limitation on all platforms.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3ccd-126">См. также</span><span class="sxs-lookup"><span data-stu-id="c3ccd-126">See Also</span></span>  
 [<span data-ttu-id="c3ccd-127">Соглашения о структуре программы и коде</span><span class="sxs-lookup"><span data-stu-id="c3ccd-127">Program Structure and Code Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)  
 [<span data-ttu-id="c3ccd-128">Соглашения об именах Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c3ccd-128">Visual Basic Naming Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)
