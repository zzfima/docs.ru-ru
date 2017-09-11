---
title: "Ограничения в Visual Basic | Документы Microsoft"
ms.custom: 
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
- limits
- limitations, Visual Basic
- limitations
- limits, Visual Basic code
- Visual Basic code, limitations
ms.assetid: cf1646b7-5d24-48c6-9616-bda8a4849d91
caps.latest.revision: 14
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
ms.openlocfilehash: a3bd551ade2f0c55cd943cfbd353b09dfede4063
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="visual-basic-limitations"></a><span data-ttu-id="b265d-102">Ограничения в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b265d-102">Visual Basic Limitations</span></span>
<span data-ttu-id="b265d-103">Более ранние версии [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] накладывались ограничения на код, такие как длина имени переменной, разрешенное количество переменных в модуле и размер модуля.</span><span class="sxs-lookup"><span data-stu-id="b265d-103">Earlier versions of [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] enforced boundaries in code, such as the length of variable names, the number of variables allowed in modules, and module size.</span></span> <span data-ttu-id="b265d-104">В [!INCLUDE[vbprvblong](../../../visual-basic/developing-apps/customizing-extending-my/includes/vbprvblong_md.md)], эти ограничения были ослаблены, предоставляя большую свободу в написании и упорядочении кода.</span><span class="sxs-lookup"><span data-stu-id="b265d-104">In [!INCLUDE[vbprvblong](../../../visual-basic/developing-apps/customizing-extending-my/includes/vbprvblong_md.md)], these restrictions have been relaxed, giving you greater freedom in writing and arranging your code.</span></span>  
  
 <span data-ttu-id="b265d-105">Физические ограничения зависят больше от памяти времени выполнения, чем на времени компиляции.</span><span class="sxs-lookup"><span data-stu-id="b265d-105">Physical limits are dependent more on run-time memory than on compile-time considerations.</span></span> <span data-ttu-id="b265d-106">Если следовать разумным правилам программирования и разделять большие приложения на несколько классов и модулей, то есть очень низкую вероятность возникновения внутреннего [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] ограничение.</span><span class="sxs-lookup"><span data-stu-id="b265d-106">If you use prudent programming practices, and divide large applications into multiple classes and modules, then there is very little chance of encountering an internal [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] limitation.</span></span>  
  
 <span data-ttu-id="b265d-107">Ниже приведены некоторые ограничения, которые могут возникнуть в крайних случаях.</span><span class="sxs-lookup"><span data-stu-id="b265d-107">The following are some limitations that you might encounter in extreme cases:</span></span>  
  
-   <span data-ttu-id="b265d-108">**Длина имени.**</span><span class="sxs-lookup"><span data-stu-id="b265d-108">**Name Length.**</span></span> <span data-ttu-id="b265d-109">Существует максимальное число знаков для имени каждого объявленного элемента программирования.</span><span class="sxs-lookup"><span data-stu-id="b265d-109">There is a maximum number of characters for the name of every declared programming element.</span></span> <span data-ttu-id="b265d-110">Этот максимум применяется к полной уточняющей строке, если полное имя элемента.</span><span class="sxs-lookup"><span data-stu-id="b265d-110">This maximum applies to an entire qualification string if the element name is qualified.</span></span> <span data-ttu-id="b265d-111">В разделе [имена объявленных элементов](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="b265d-111">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
-   <span data-ttu-id="b265d-112">**Длина строки.**</span><span class="sxs-lookup"><span data-stu-id="b265d-112">**Line Length.**</span></span> <span data-ttu-id="b265d-113">Существует более 65535 символов в физической строке исходного кода.</span><span class="sxs-lookup"><span data-stu-id="b265d-113">There is a maximum of 65535 characters in a physical line of source code.</span></span> <span data-ttu-id="b265d-114">Логическая строка исходного кода может быть больше, если вы используете символы продолжения строки.</span><span class="sxs-lookup"><span data-stu-id="b265d-114">The logical source code line can be longer if you use line continuation characters.</span></span> <span data-ttu-id="b265d-115">В разделе [как: разбиение и объединение инструкций в коде](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md).</span><span class="sxs-lookup"><span data-stu-id="b265d-115">See [How to: Break and Combine Statements in Code](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md).</span></span>  
  
-   <span data-ttu-id="b265d-116">**Размерность массива.**</span><span class="sxs-lookup"><span data-stu-id="b265d-116">**Array Dimensions.**</span></span> <span data-ttu-id="b265d-117">Существует максимальное число измерений, которые можно объявить для массива.</span><span class="sxs-lookup"><span data-stu-id="b265d-117">There is a maximum number of dimensions you can declare for an array.</span></span> <span data-ttu-id="b265d-118">Это ограничивает количество индексов, которые можно использовать для указания элемента массива.</span><span class="sxs-lookup"><span data-stu-id="b265d-118">This limits how many indexes you can use to specify an array element.</span></span> <span data-ttu-id="b265d-119">В разделе [массива измерений в Visual Basic](../../../visual-basic/programming-guide/language-features/arrays/array-dimensions.md).</span><span class="sxs-lookup"><span data-stu-id="b265d-119">See [Array Dimensions in Visual Basic](../../../visual-basic/programming-guide/language-features/arrays/array-dimensions.md).</span></span>  
  
-   <span data-ttu-id="b265d-120">**Длина строки.**</span><span class="sxs-lookup"><span data-stu-id="b265d-120">**String Length.**</span></span> <span data-ttu-id="b265d-121">Существует максимальное число знаков Юникода, которые можно хранить в одной строке.</span><span class="sxs-lookup"><span data-stu-id="b265d-121">There is a maximum number of Unicode characters you can store in a single string.</span></span> <span data-ttu-id="b265d-122">В разделе [строковый тип данных](../../../visual-basic/language-reference/data-types/string-data-type.md).</span><span class="sxs-lookup"><span data-stu-id="b265d-122">See [String Data Type](../../../visual-basic/language-reference/data-types/string-data-type.md).</span></span>  
  
-   <span data-ttu-id="b265d-123">**Длина строки в среде.**</span><span class="sxs-lookup"><span data-stu-id="b265d-123">**Environment String Length.**</span></span> <span data-ttu-id="b265d-124">Существует максимум 32768 знаков для любой строки среды, используется в качестве аргумента командной строки.</span><span class="sxs-lookup"><span data-stu-id="b265d-124">There is a maximum of 32768 characters for any environment string used as a command-line argument.</span></span> <span data-ttu-id="b265d-125">Это ограничение для всех платформ.</span><span class="sxs-lookup"><span data-stu-id="b265d-125">This is a limitation on all platforms.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b265d-126">См. также</span><span class="sxs-lookup"><span data-stu-id="b265d-126">See Also</span></span>  
 <span data-ttu-id="b265d-127">[Структура программы и соглашения о коде](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md) </span><span class="sxs-lookup"><span data-stu-id="b265d-127">[Program Structure and Code Conventions](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md) </span></span>  
<span data-ttu-id="b265d-128"> [Соглашения об именах Visual Basic](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)</span><span class="sxs-lookup"><span data-stu-id="b265d-128"> [Visual Basic Naming Conventions](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)</span></span>
