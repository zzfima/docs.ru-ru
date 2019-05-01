---
title: MustInherit (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- MustInherit
- vb.MustInherit
helpviewer_keywords:
- classes [Visual Basic], abstract
- MustInherit classes [Visual Basic], MustInherit keyword
- abstract classes [Visual Basic], MustInherit class
- MustInherit keyword [Visual Basic]
ms.assetid: b8f05185-90e3-4dd7-adc2-90d852fab5b4
ms.openlocfilehash: 0bda03d3c01356317fbcc56d44199ff4f9484b5b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62053942"
---
# <a name="mustinherit-visual-basic"></a><span data-ttu-id="e53be-102">MustInherit (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e53be-102">MustInherit (Visual Basic)</span></span>
<span data-ttu-id="e53be-103">Указывает, что класс может использоваться только в качестве базового класса, и что не удается создать объект непосредственно из него.</span><span class="sxs-lookup"><span data-stu-id="e53be-103">Specifies that a class can be used only as a base class and that you cannot create an object directly from it.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e53be-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="e53be-104">Remarks</span></span>  
 <span data-ttu-id="e53be-105">Цель *базового класса* (также известный как *абстрактного класса*) заключается в определении функции, общие для всех классов, производных от него.</span><span class="sxs-lookup"><span data-stu-id="e53be-105">The purpose of a *base class* (also known as an *abstract class*) is to define functionality that is common to all the classes derived from it.</span></span> <span data-ttu-id="e53be-106">Это экономит производные классы от необходимости переопределять Общие элементы.</span><span class="sxs-lookup"><span data-stu-id="e53be-106">This saves the derived classes from having to redefine the common elements.</span></span> <span data-ttu-id="e53be-107">В некоторых случаях эти общие функциональные возможности не недостаточно полна, чтобы сделать подходящий объект, и каждый производный класс определяет отсутствующие функциональные возможности.</span><span class="sxs-lookup"><span data-stu-id="e53be-107">In some cases, this common functionality is not complete enough to make a usable object, and each derived class defines the missing functionality.</span></span> <span data-ttu-id="e53be-108">В этом случае требуется много кода для создания объектов только из производных классов.</span><span class="sxs-lookup"><span data-stu-id="e53be-108">In such a case, you want the consuming code to create objects only from the derived classes.</span></span> <span data-ttu-id="e53be-109">Использовании `MustInherit` в базовом классе, это обеспечить.</span><span class="sxs-lookup"><span data-stu-id="e53be-109">You use `MustInherit` on the base class to enforce this.</span></span>  
  
 <span data-ttu-id="e53be-110">Другим использованием `MustInherit` класс является ограничение переменной для набора связанных классов.</span><span class="sxs-lookup"><span data-stu-id="e53be-110">Another use of a `MustInherit` class is to restrict a variable to a set of related classes.</span></span> <span data-ttu-id="e53be-111">Можно определить базовый класс и производные от него все эти связанные классы.</span><span class="sxs-lookup"><span data-stu-id="e53be-111">You can define a base class and derive all these related classes from it.</span></span> <span data-ttu-id="e53be-112">Базовый класс не требуется ли предоставлять любые функции, общие для всех производных классов, но его можно использовать в качестве фильтра для присвоения значений переменным.</span><span class="sxs-lookup"><span data-stu-id="e53be-112">The base class does not need to provide any functionality common to all the derived classes, but it can serve as a filter for assigning values to variables.</span></span> <span data-ttu-id="e53be-113">Если код объявляет переменную как базовый класс, Visual Basic позволяет присвоить переменной только объект из одного из производных классов.</span><span class="sxs-lookup"><span data-stu-id="e53be-113">If your consuming code declares a variable as the base class, Visual Basic allows you to assign only an object from one of the derived classes to that variable.</span></span>  
  
 <span data-ttu-id="e53be-114">.NET Framework определяет несколько `MustInherit` классов, между ними <xref:System.Array>, <xref:System.Enum>, и <xref:System.ValueType>.</span><span class="sxs-lookup"><span data-stu-id="e53be-114">The .NET Framework defines several `MustInherit` classes, among them <xref:System.Array>, <xref:System.Enum>, and <xref:System.ValueType>.</span></span> <span data-ttu-id="e53be-115"><xref:System.ValueType> приведен пример базового класса, который ограничивает переменную.</span><span class="sxs-lookup"><span data-stu-id="e53be-115"><xref:System.ValueType> is an example of a base class that restricts a variable.</span></span> <span data-ttu-id="e53be-116">Все типы значений являются производными от <xref:System.ValueType>.</span><span class="sxs-lookup"><span data-stu-id="e53be-116">All value types derive from <xref:System.ValueType>.</span></span> <span data-ttu-id="e53be-117">Если объявить переменную как <xref:System.ValueType>, этой переменной можно назначить только типы значений.</span><span class="sxs-lookup"><span data-stu-id="e53be-117">If you declare a variable as <xref:System.ValueType>, you can assign only value types to that variable.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="e53be-118">Правила</span><span class="sxs-lookup"><span data-stu-id="e53be-118">Rules</span></span>  
  
- <span data-ttu-id="e53be-119">**Контекст объявления.**</span><span class="sxs-lookup"><span data-stu-id="e53be-119">**Declaration Context.**</span></span> <span data-ttu-id="e53be-120">Можно использовать `MustInherit` только в `Class` инструкции.</span><span class="sxs-lookup"><span data-stu-id="e53be-120">You can use `MustInherit` only in a `Class` statement.</span></span>  
  
- <span data-ttu-id="e53be-121">**Комбинированные модификаторы.**</span><span class="sxs-lookup"><span data-stu-id="e53be-121">**Combined Modifiers.**</span></span> <span data-ttu-id="e53be-122">Нельзя указать `MustInherit` вместе с `NotInheritable` в одном объявлении.</span><span class="sxs-lookup"><span data-stu-id="e53be-122">You cannot specify `MustInherit` together with `NotInheritable` in the same declaration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e53be-123">Пример</span><span class="sxs-lookup"><span data-stu-id="e53be-123">Example</span></span>  
 <span data-ttu-id="e53be-124">В следующем примере показано принудительное наследование и переопределение.</span><span class="sxs-lookup"><span data-stu-id="e53be-124">The following example illustrates both forced inheritance and forced overriding.</span></span> <span data-ttu-id="e53be-125">Базовый класс `shape` определяет переменную `acrossLine`.</span><span class="sxs-lookup"><span data-stu-id="e53be-125">The base class `shape` defines a variable `acrossLine`.</span></span> <span data-ttu-id="e53be-126">Классы `circle` и `square` являются производными от `shape`.</span><span class="sxs-lookup"><span data-stu-id="e53be-126">The classes `circle` and `square` derive from `shape`.</span></span> <span data-ttu-id="e53be-127">Они наследуют определение `acrossLine`, но должны определять функцию `area` так, как это вычисление отличается для каждого вида фигуры.</span><span class="sxs-lookup"><span data-stu-id="e53be-127">They inherit the definition of `acrossLine`, but they must define the function `area` because that calculation is different for each kind of shape.</span></span>  
  
 [!code-vb[VbVbalrKeywords#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class1.vb#2)]  
  
 <span data-ttu-id="e53be-128">Можно объявить `shape1` и `shape2` типа `shape`.</span><span class="sxs-lookup"><span data-stu-id="e53be-128">You can declare `shape1` and `shape2` to be of type `shape`.</span></span> <span data-ttu-id="e53be-129">Тем не менее, не удается создать объект из `shape` так, как у него нет функцию `area` и помечается `MustInherit`.</span><span class="sxs-lookup"><span data-stu-id="e53be-129">However, you cannot create an object from `shape` because it lacks the functionality of the function `area` and is marked `MustInherit`.</span></span>  
  
 <span data-ttu-id="e53be-130">Так как они будут объявлены как `shape`, переменные `shape1` и `shape2` доступны только для объектов из производных классов `circle` и `square`.</span><span class="sxs-lookup"><span data-stu-id="e53be-130">Because they are declared as `shape`, the variables `shape1` and `shape2` are restricted to objects from the derived classes `circle` and `square`.</span></span> <span data-ttu-id="e53be-131">Visual Basic не поддерживает назначение любого другого объекта эти переменные, которая предоставляет высокий уровень безопасности типов.</span><span class="sxs-lookup"><span data-stu-id="e53be-131">Visual Basic does not allow you to assign any other object to these variables, which gives you a high level of type safety.</span></span>  
  
## <a name="usage"></a><span data-ttu-id="e53be-132">Использование</span><span class="sxs-lookup"><span data-stu-id="e53be-132">Usage</span></span>  
 <span data-ttu-id="e53be-133">`MustInherit` Модификатор может использоваться в этом контексте:</span><span class="sxs-lookup"><span data-stu-id="e53be-133">The `MustInherit` modifier can be used in this context:</span></span>  
  
 [<span data-ttu-id="e53be-134">Оператор Class</span><span class="sxs-lookup"><span data-stu-id="e53be-134">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="e53be-135">См. также</span><span class="sxs-lookup"><span data-stu-id="e53be-135">See also</span></span>

- [<span data-ttu-id="e53be-136">Оператор Inherits</span><span class="sxs-lookup"><span data-stu-id="e53be-136">Inherits Statement</span></span>](../../../visual-basic/language-reference/statements/inherits-statement.md)
- [<span data-ttu-id="e53be-137">NotInheritable</span><span class="sxs-lookup"><span data-stu-id="e53be-137">NotInheritable</span></span>](../../../visual-basic/language-reference/modifiers/notinheritable.md)
- [<span data-ttu-id="e53be-138">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="e53be-138">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
- [<span data-ttu-id="e53be-139">Основы наследования</span><span class="sxs-lookup"><span data-stu-id="e53be-139">Inheritance Basics</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
