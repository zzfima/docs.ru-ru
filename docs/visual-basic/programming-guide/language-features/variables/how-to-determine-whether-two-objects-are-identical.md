---
title: "Практическое руководство: определить, являются ли два объекта идентичными (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- testing, objects
- objects [Visual Basic], comparing
- object variables, determining identity
ms.assetid: 7829f817-0d1f-4749-a707-de0b95e0cf5c
caps.latest.revision: 19
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
ms.openlocfilehash: c9621412eb1429ed07d8861114a67a67b6c1d58c
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-determine-whether-two-objects-are-identical-visual-basic"></a><span data-ttu-id="b7be9-102">Практическое руководство. Определение идентичности двух объектов (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b7be9-102">How to: Determine Whether Two Objects Are Identical (Visual Basic)</span></span>
<span data-ttu-id="b7be9-103">В [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], две ссылки на переменные считаются идентичными, если их указатели совпадают, то есть если обе переменных указывают на один экземпляр класса в памяти.</span><span class="sxs-lookup"><span data-stu-id="b7be9-103">In [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], two variable references are considered identical if their pointers are the same, that is, if both variables point to the same class instance in memory.</span></span> <span data-ttu-id="b7be9-104">Например, в приложении Windows Forms может потребоваться сделать сравнение, чтобы определить ли текущий экземпляр (`Me`) является таким же, как конкретный экземпляр, такой как `Form2`.</span><span class="sxs-lookup"><span data-stu-id="b7be9-104">For example, in a Windows Forms application, you might want to make a comparison to determine whether the current instance (`Me`) is the same as a particular instance, such as `Form2`.</span></span>  
  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="b7be9-105">предоставляет два оператора для сравнения указателей.</span><span class="sxs-lookup"><span data-stu-id="b7be9-105"> provides two operators to compare pointers.</span></span> <span data-ttu-id="b7be9-106">[Оператор Is](../../../../visual-basic/language-reference/operators/is-operator.md) возвращает `True` Если объекты совпадают и [оператор IsNot](../../../../visual-basic/language-reference/operators/isnot-operator.md) возвращает `True` , если это не так.</span><span class="sxs-lookup"><span data-stu-id="b7be9-106">The [Is Operator](../../../../visual-basic/language-reference/operators/is-operator.md) returns `True` if the objects are identical, and the [IsNot Operator](../../../../visual-basic/language-reference/operators/isnot-operator.md) returns `True` if they are not.</span></span>  
  
## <a name="determining-if-two-objects-are-identical"></a><span data-ttu-id="b7be9-107">Определение, являются ли два объекта идентичными</span><span class="sxs-lookup"><span data-stu-id="b7be9-107">Determining if Two Objects Are Identical</span></span>  
  
#### <a name="to-determine-if-two-objects-are-identical"></a><span data-ttu-id="b7be9-108">Для определения идентичности двух объектов</span><span class="sxs-lookup"><span data-stu-id="b7be9-108">To determine if two objects are identical</span></span>  
  
1.  <span data-ttu-id="b7be9-109">Настройка `Boolean` выражение для проверки двух объектов.</span><span class="sxs-lookup"><span data-stu-id="b7be9-109">Set up a `Boolean` expression to test the two objects.</span></span>  
  
2.  <span data-ttu-id="b7be9-110">В проверяемом выражении используйте `Is` оператора с двумя объектами в качестве операндов.</span><span class="sxs-lookup"><span data-stu-id="b7be9-110">In your testing expression, use the `Is` operator with the two objects as operands.</span></span>  
  
     <span data-ttu-id="b7be9-111">`Is`Возвращает `True` , если объекты указывают на один и тот же экземпляр класса.</span><span class="sxs-lookup"><span data-stu-id="b7be9-111">`Is` returns `True` if the objects point to the same class instance.</span></span>  
  
## <a name="determining-if-two-objects-are-not-identical"></a><span data-ttu-id="b7be9-112">Определение, если два объекта не совпадают</span><span class="sxs-lookup"><span data-stu-id="b7be9-112">Determining if Two Objects Are Not Identical</span></span>  
 <span data-ttu-id="b7be9-113">Иногда требуется выполнить действие, если два объекта не идентичны, и может быть неудобно объединять `Not` и `Is`, например `If Not obj1 Is obj2`.</span><span class="sxs-lookup"><span data-stu-id="b7be9-113">Sometimes you want to perform an action if the two objects are not identical, and it can be awkward to combine `Not` and `Is`, for example `If Not obj1 Is obj2`.</span></span> <span data-ttu-id="b7be9-114">В этом случае можно использовать `IsNot` оператор.</span><span class="sxs-lookup"><span data-stu-id="b7be9-114">In such a case you can use the `IsNot` operator.</span></span>  
  
#### <a name="to-determine-if-two-objects-are-not-identical"></a><span data-ttu-id="b7be9-115">Чтобы определить, если два объекта не совпадают</span><span class="sxs-lookup"><span data-stu-id="b7be9-115">To determine if two objects are not identical</span></span>  
  
1.  <span data-ttu-id="b7be9-116">Настройка `Boolean` выражение для проверки двух объектов.</span><span class="sxs-lookup"><span data-stu-id="b7be9-116">Set up a `Boolean` expression to test the two objects.</span></span>  
  
2.  <span data-ttu-id="b7be9-117">В проверяемом выражении используйте `IsNot` оператора с двумя объектами в качестве операндов.</span><span class="sxs-lookup"><span data-stu-id="b7be9-117">In your testing expression, use the `IsNot` operator with the two objects as operands.</span></span>  
  
     <span data-ttu-id="b7be9-118">`IsNot`Возвращает `True` , если объекты не указывают на один и тот же экземпляр класса.</span><span class="sxs-lookup"><span data-stu-id="b7be9-118">`IsNot` returns `True` if the objects do not point to the same class instance.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b7be9-119">Пример</span><span class="sxs-lookup"><span data-stu-id="b7be9-119">Example</span></span>  
 <span data-ttu-id="b7be9-120">Следующий пример проверяет пары `Object` переменные, чтобы увидеть, указывают ли они на один экземпляр класса.</span><span class="sxs-lookup"><span data-stu-id="b7be9-120">The following example tests pairs of `Object` variables to see if they point to the same class instance.</span></span>  
  
 <span data-ttu-id="b7be9-121">[!code-vb[VbVbalrKeywords&#14;](../../../../visual-basic/language-reference/codesnippet/VisualBasic/how-to-determine-whether-two-objects-are-identical_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="b7be9-121">[!code-vb[VbVbalrKeywords#14](../../../../visual-basic/language-reference/codesnippet/VisualBasic/how-to-determine-whether-two-objects-are-identical_1.vb)]</span></span>  
  
 <span data-ttu-id="b7be9-122">В предыдущем примере отображаются следующие выходные данные.</span><span class="sxs-lookup"><span data-stu-id="b7be9-122">The preceding example displays the following output.</span></span>  
  
 `objA different from objB? True`  
  
 `objA identical to objC? True`  
  
## <a name="see-also"></a><span data-ttu-id="b7be9-123">См. также</span><span class="sxs-lookup"><span data-stu-id="b7be9-123">See Also</span></span>  
 <span data-ttu-id="b7be9-124">[Тип данных Object](../../../../visual-basic/language-reference/data-types/object-data-type.md) </span><span class="sxs-lookup"><span data-stu-id="b7be9-124">[Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md) </span></span>  
<span data-ttu-id="b7be9-125"> [Объектные переменные](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md) </span><span class="sxs-lookup"><span data-stu-id="b7be9-125"> [Object Variables](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md) </span></span>  
<span data-ttu-id="b7be9-126"> [Значения объектных переменных](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md) </span><span class="sxs-lookup"><span data-stu-id="b7be9-126"> [Object Variable Values](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md) </span></span>  
<span data-ttu-id="b7be9-127"> [Оператор Is](../../../../visual-basic/language-reference/operators/is-operator.md) </span><span class="sxs-lookup"><span data-stu-id="b7be9-127"> [Is Operator](../../../../visual-basic/language-reference/operators/is-operator.md) </span></span>  
<span data-ttu-id="b7be9-128"> [Оператор IsNot](../../../../visual-basic/language-reference/operators/isnot-operator.md) </span><span class="sxs-lookup"><span data-stu-id="b7be9-128"> [IsNot Operator](../../../../visual-basic/language-reference/operators/isnot-operator.md) </span></span>  
<span data-ttu-id="b7be9-129"> [Практическое руководство: определение связи между двумя объектами](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-related.md) </span><span class="sxs-lookup"><span data-stu-id="b7be9-129"> [How to: Determine Whether Two Objects Are Related](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-related.md) </span></span>  
<span data-ttu-id="b7be9-130"> [Me, My, MyBase и MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)</span><span class="sxs-lookup"><span data-stu-id="b7be9-130"> [Me, My, MyBase, and MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)</span></span>
