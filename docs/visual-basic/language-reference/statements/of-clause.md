---
title: "Предложение Of (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- Of
- vb.Of
- vb.of
helpviewer_keywords:
- Of keyword [Visual Basic]
- arguments [Visual Basic], data types
- constraints, Visual Basic generic types
- generic parameters
- generics [Visual Basic], constraints
- parameters [Visual Basic], type
- types [Visual Basic], generic
- parameters [Visual Basic], generic
- type parameters
- data type arguments
ms.assetid: 0db8f65c-65af-4089-ab7f-6fcfecb60444
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 5ef3ac4ac88727b1dcae50fa14abde03f29a16fb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="of-clause-visual-basic"></a><span data-ttu-id="cc52f-102">Предложение Of (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cc52f-102">Of Clause (Visual Basic)</span></span>
<span data-ttu-id="cc52f-103">Представляет `Of` предложение, которое идентифицирует *параметр типа* на *универсального* класса, структуры, интерфейса, делегата или процедуры.</span><span class="sxs-lookup"><span data-stu-id="cc52f-103">Introduces an `Of` clause, which identifies a *type parameter* on a *generic* class, structure, interface, delegate, or procedure.</span></span> <span data-ttu-id="cc52f-104">Сведения об универсальных типах см. в разделе [универсальных типов в Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md).</span><span class="sxs-lookup"><span data-stu-id="cc52f-104">For information on generic types, see [Generic Types in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md).</span></span>  
  
## <a name="using-the-of-keyword"></a><span data-ttu-id="cc52f-105">С помощью ключевого слова</span><span class="sxs-lookup"><span data-stu-id="cc52f-105">Using the Of Keyword</span></span>  
 <span data-ttu-id="cc52f-106">Следующий пример кода использует `Of` ключевое слово, чтобы определить структуру класса, который принимает два параметра типа.</span><span class="sxs-lookup"><span data-stu-id="cc52f-106">The following code example uses the `Of` keyword to define the outline of a class that takes two type parameters.</span></span> <span data-ttu-id="cc52f-107">Он *ограничивает* `keyType` по <xref:System.IComparable> интерфейс, который означает код-потребитель необходимо указать аргумент типа, который реализует <xref:System.IComparable>.</span><span class="sxs-lookup"><span data-stu-id="cc52f-107">It *constrains* the `keyType` parameter by the <xref:System.IComparable> interface, which means the consuming code must supply a type argument that implements <xref:System.IComparable>.</span></span> <span data-ttu-id="cc52f-108">Это необходимо, чтобы `add` процедура может вызывать <xref:System.IComparable.CompareTo%2A?displayProperty=nameWithType> метод.</span><span class="sxs-lookup"><span data-stu-id="cc52f-108">This is necessary so that the `add` procedure can call the <xref:System.IComparable.CompareTo%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="cc52f-109">Дополнительные сведения об ограничениях см. в разделе [список типов](../../../visual-basic/language-reference/statements/type-list.md).</span><span class="sxs-lookup"><span data-stu-id="cc52f-109">For more information on constraints, see [Type List](../../../visual-basic/language-reference/statements/type-list.md).</span></span>  
  
```  
Public Class Dictionary(Of entryType, keyType As IComparable)  
    Public Sub add(ByVal e As entryType, ByVal k As keyType)  
        Dim dk As keyType  
        If k.CompareTo(dk) = 0 Then  
        End If  
    End Sub  
    Public Function find(ByVal k As keyType) As entryType  
    End Function  
End Class  
```  
  
 <span data-ttu-id="cc52f-110">Если выполнить предыдущий определение класса, можно создать различные `dictionary` классы из него.</span><span class="sxs-lookup"><span data-stu-id="cc52f-110">If you complete the preceding class definition, you can construct a variety of `dictionary` classes from it.</span></span> <span data-ttu-id="cc52f-111">Типы, которые вводятся `entryType` и `keyType` определить класс содержит тип и тип ключа, связываемого с каждой записи.</span><span class="sxs-lookup"><span data-stu-id="cc52f-111">The types you supply to `entryType` and `keyType` determine what type of entry the class holds and what type of key it associates with each entry.</span></span> <span data-ttu-id="cc52f-112">Из-за ограничений, необходимо указать `keyType` тип, реализующий <xref:System.IComparable>.</span><span class="sxs-lookup"><span data-stu-id="cc52f-112">Because of the constraint, you must supply to `keyType` a type that implements <xref:System.IComparable>.</span></span>  
  
 <span data-ttu-id="cc52f-113">В следующем примере кода создается объект, который содержит `String` записей и связывает `Integer` ключа с каждой из них.</span><span class="sxs-lookup"><span data-stu-id="cc52f-113">The following code example creates an object that holds `String` entries and associates an `Integer` key with each one.</span></span> <span data-ttu-id="cc52f-114">`Integer`реализует <xref:System.IComparable> и поэтому удовлетворяет ограничению на `keyType`.</span><span class="sxs-lookup"><span data-stu-id="cc52f-114">`Integer` implements <xref:System.IComparable> and therefore satisfies the constraint on `keyType`.</span></span>  
  
```  
Dim d As New dictionary(Of String, Integer)  
```  
  
 <span data-ttu-id="cc52f-115">Ключевое слово `Of` можно использовать в следующих контекстах:</span><span class="sxs-lookup"><span data-stu-id="cc52f-115">The `Of` keyword can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="cc52f-116">Оператор Class</span><span class="sxs-lookup"><span data-stu-id="cc52f-116">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [<span data-ttu-id="cc52f-117">Оператор Delegate</span><span class="sxs-lookup"><span data-stu-id="cc52f-117">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)  
  
 [<span data-ttu-id="cc52f-118">Оператор Function</span><span class="sxs-lookup"><span data-stu-id="cc52f-118">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="cc52f-119">Оператор Interface</span><span class="sxs-lookup"><span data-stu-id="cc52f-119">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 [<span data-ttu-id="cc52f-120">Оператор Structure</span><span class="sxs-lookup"><span data-stu-id="cc52f-120">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
 [<span data-ttu-id="cc52f-121">Оператор Sub</span><span class="sxs-lookup"><span data-stu-id="cc52f-121">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="cc52f-122">См. также</span><span class="sxs-lookup"><span data-stu-id="cc52f-122">See Also</span></span>  
 <xref:System.IComparable>  
 [<span data-ttu-id="cc52f-123">Список типов</span><span class="sxs-lookup"><span data-stu-id="cc52f-123">Type List</span></span>](../../../visual-basic/language-reference/statements/type-list.md)  
 [<span data-ttu-id="cc52f-124">Универсальные типы в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="cc52f-124">Generic Types in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)  
 [<span data-ttu-id="cc52f-125">In</span><span class="sxs-lookup"><span data-stu-id="cc52f-125">In</span></span>](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md)  
 [<span data-ttu-id="cc52f-126">Out</span><span class="sxs-lookup"><span data-stu-id="cc52f-126">Out</span></span>](../../../visual-basic/language-reference/modifiers/out-generic-modifier.md)
