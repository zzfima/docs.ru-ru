---
title: MustInherit (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- MustInherit
- vb.MustInherit
helpviewer_keywords:
- classes [Visual Basic], abstract
- MustInherit classes [Visual Basic], MustInherit keyword
- abstract classes [Visual Basic], MustInherit class
- MustInherit keyword [Visual Basic]
ms.assetid: b8f05185-90e3-4dd7-adc2-90d852fab5b4
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 9d384986e42ee69a0f425c1590599aa2c82bc856
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="mustinherit-visual-basic"></a><span data-ttu-id="36020-102">MustInherit (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="36020-102">MustInherit (Visual Basic)</span></span>
<span data-ttu-id="36020-103">Указывает, что класс может использоваться только как базовый класс и что невозможно создать объект непосредственно из него.</span><span class="sxs-lookup"><span data-stu-id="36020-103">Specifies that a class can be used only as a base class and that you cannot create an object directly from it.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="36020-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="36020-104">Remarks</span></span>  
 <span data-ttu-id="36020-105">Назначение *базового класса* (также известный как *абстрактного класса*) заключается в определении функции, общие для всех классов, производных от него.</span><span class="sxs-lookup"><span data-stu-id="36020-105">The purpose of a *base class* (also known as an *abstract class*) is to define functionality that is common to all the classes derived from it.</span></span> <span data-ttu-id="36020-106">Это экономит производные классы от необходимости переопределять Общие элементы.</span><span class="sxs-lookup"><span data-stu-id="36020-106">This saves the derived classes from having to redefine the common elements.</span></span> <span data-ttu-id="36020-107">В некоторых случаях эти общие функциональные возможности не завершено, чтобы сделать подходящий объект, и каждый производный класс определяет отсутствующие функциональные возможности.</span><span class="sxs-lookup"><span data-stu-id="36020-107">In some cases, this common functionality is not complete enough to make a usable object, and each derived class defines the missing functionality.</span></span> <span data-ttu-id="36020-108">В этом случае требуется много кода для создания объектов только из производных классов.</span><span class="sxs-lookup"><span data-stu-id="36020-108">In such a case, you want the consuming code to create objects only from the derived classes.</span></span> <span data-ttu-id="36020-109">Вы используете `MustInherit` базового класса, чтобы этого добиться.</span><span class="sxs-lookup"><span data-stu-id="36020-109">You use `MustInherit` on the base class to enforce this.</span></span>  
  
 <span data-ttu-id="36020-110">Другое использование оператора `MustInherit` класса является ограничение переменной до набора связанных классов.</span><span class="sxs-lookup"><span data-stu-id="36020-110">Another use of a `MustInherit` class is to restrict a variable to a set of related classes.</span></span> <span data-ttu-id="36020-111">Можно определить базовый класс и производные от него все эти связанные классы.</span><span class="sxs-lookup"><span data-stu-id="36020-111">You can define a base class and derive all these related classes from it.</span></span> <span data-ttu-id="36020-112">Базовый класс не требуется для предоставления функциональных возможностей, общих для всех производных классов, но его можно использовать в качестве фильтра для присвоения значений переменным.</span><span class="sxs-lookup"><span data-stu-id="36020-112">The base class does not need to provide any functionality common to all the derived classes, but it can serve as a filter for assigning values to variables.</span></span> <span data-ttu-id="36020-113">Если код объявляет переменную как базовый класс, Visual Basic можно присвоить переменной только объект из одного из производных классов.</span><span class="sxs-lookup"><span data-stu-id="36020-113">If your consuming code declares a variable as the base class, Visual Basic allows you to assign only an object from one of the derived classes to that variable.</span></span>  
  
 <span data-ttu-id="36020-114">Платформа .NET Framework определяет несколько `MustInherit` классы, среди них <xref:System.Array>, <xref:System.Enum>, и <xref:System.ValueType>.</span><span class="sxs-lookup"><span data-stu-id="36020-114">The .NET Framework defines several `MustInherit` classes, among them <xref:System.Array>, <xref:System.Enum>, and <xref:System.ValueType>.</span></span> <span data-ttu-id="36020-115"><xref:System.ValueType>Примером может служить базового класса, который ограничивает переменную.</span><span class="sxs-lookup"><span data-stu-id="36020-115"><xref:System.ValueType> is an example of a base class that restricts a variable.</span></span> <span data-ttu-id="36020-116">Все типы значений являются производными от <xref:System.ValueType>.</span><span class="sxs-lookup"><span data-stu-id="36020-116">All value types derive from <xref:System.ValueType>.</span></span> <span data-ttu-id="36020-117">Если объявить переменную как <xref:System.ValueType>, этой переменной можно назначить только типы значений.</span><span class="sxs-lookup"><span data-stu-id="36020-117">If you declare a variable as <xref:System.ValueType>, you can assign only value types to that variable.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="36020-118">Правила</span><span class="sxs-lookup"><span data-stu-id="36020-118">Rules</span></span>  
  
-   <span data-ttu-id="36020-119">**Контекст объявления.**</span><span class="sxs-lookup"><span data-stu-id="36020-119">**Declaration Context.**</span></span> <span data-ttu-id="36020-120">Можно использовать `MustInherit` только в `Class` инструкции.</span><span class="sxs-lookup"><span data-stu-id="36020-120">You can use `MustInherit` only in a `Class` statement.</span></span>  
  
-   <span data-ttu-id="36020-121">**Комбинированные модификаторы.**</span><span class="sxs-lookup"><span data-stu-id="36020-121">**Combined Modifiers.**</span></span> <span data-ttu-id="36020-122">Нельзя указать `MustInherit` вместе с `NotInheritable` в одном объявлении.</span><span class="sxs-lookup"><span data-stu-id="36020-122">You cannot specify `MustInherit` together with `NotInheritable` in the same declaration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="36020-123">Пример</span><span class="sxs-lookup"><span data-stu-id="36020-123">Example</span></span>  
 <span data-ttu-id="36020-124">В следующем примере показано, как принудительное наследование и переопределение.</span><span class="sxs-lookup"><span data-stu-id="36020-124">The following example illustrates both forced inheritance and forced overriding.</span></span> <span data-ttu-id="36020-125">Базовый класс `shape` определяет переменную `acrossLine`.</span><span class="sxs-lookup"><span data-stu-id="36020-125">The base class `shape` defines a variable `acrossLine`.</span></span> <span data-ttu-id="36020-126">Классы `circle` и `square` являются производными от `shape`.</span><span class="sxs-lookup"><span data-stu-id="36020-126">The classes `circle` and `square` derive from `shape`.</span></span> <span data-ttu-id="36020-127">Они наследуют определение `acrossLine`, но должны определять функции `area` так, как это вычисление, отличается для каждого вида фигуры.</span><span class="sxs-lookup"><span data-stu-id="36020-127">They inherit the definition of `acrossLine`, but they must define the function `area` because that calculation is different for each kind of shape.</span></span>  
  
 [!code-vb[VbVbalrKeywords#2](../../../visual-basic/language-reference/codesnippet/VisualBasic/mustinherit_1.vb)]  
  
 <span data-ttu-id="36020-128">Можно объявить `shape1` и `shape2` типа `shape`.</span><span class="sxs-lookup"><span data-stu-id="36020-128">You can declare `shape1` and `shape2` to be of type `shape`.</span></span> <span data-ttu-id="36020-129">Тем не менее, не удается создать объект из `shape` , так как он не имеет функцию `area` и помечается `MustInherit`.</span><span class="sxs-lookup"><span data-stu-id="36020-129">However, you cannot create an object from `shape` because it lacks the functionality of the function `area` and is marked `MustInherit`.</span></span>  
  
 <span data-ttu-id="36020-130">Так как они были объявлены как `shape`, переменные `shape1` и `shape2` доступны только для объектов из производных классов `circle` и `square`.</span><span class="sxs-lookup"><span data-stu-id="36020-130">Because they are declared as `shape`, the variables `shape1` and `shape2` are restricted to objects from the derived classes `circle` and `square`.</span></span> <span data-ttu-id="36020-131">Visual Basic не можно назначать любой другой объект на эти переменные, что обеспечивает высокий уровень безопасности типов.</span><span class="sxs-lookup"><span data-stu-id="36020-131">Visual Basic does not allow you to assign any other object to these variables, which gives you a high level of type safety.</span></span>  
  
## <a name="usage"></a><span data-ttu-id="36020-132">Использование</span><span class="sxs-lookup"><span data-stu-id="36020-132">Usage</span></span>  
 <span data-ttu-id="36020-133">`MustInherit` Модификатор может использоваться в этом контексте:</span><span class="sxs-lookup"><span data-stu-id="36020-133">The `MustInherit` modifier can be used in this context:</span></span>  
  
 [<span data-ttu-id="36020-134">Оператор Class</span><span class="sxs-lookup"><span data-stu-id="36020-134">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="36020-135">См. также</span><span class="sxs-lookup"><span data-stu-id="36020-135">See Also</span></span>  
 [<span data-ttu-id="36020-136">Оператор Inherits</span><span class="sxs-lookup"><span data-stu-id="36020-136">Inherits Statement</span></span>](../../../visual-basic/language-reference/statements/inherits-statement.md)  
 [<span data-ttu-id="36020-137">NotInheritable</span><span class="sxs-lookup"><span data-stu-id="36020-137">NotInheritable</span></span>](../../../visual-basic/language-reference/modifiers/notinheritable.md)  
 [<span data-ttu-id="36020-138">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="36020-138">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)  
 [<span data-ttu-id="36020-139">Основы наследования</span><span class="sxs-lookup"><span data-stu-id="36020-139">Inheritance Basics</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
