---
title: MustInherit
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
ms.openlocfilehash: 30befaaf194d78d26a57f29c59bf0a603e9f07a3
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351501"
---
# <a name="mustinherit-visual-basic"></a><span data-ttu-id="ec15c-102">MustInherit (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ec15c-102">MustInherit (Visual Basic)</span></span>
<span data-ttu-id="ec15c-103">Указывает, что класс может использоваться только в качестве базового класса и не может создавать объект непосредственно из него.</span><span class="sxs-lookup"><span data-stu-id="ec15c-103">Specifies that a class can be used only as a base class and that you cannot create an object directly from it.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ec15c-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="ec15c-104">Remarks</span></span>  
 <span data-ttu-id="ec15c-105">Целью *базового класса* (также известного как *абстрактный класс*) является определение функций, общих для всех классов, производных от него.</span><span class="sxs-lookup"><span data-stu-id="ec15c-105">The purpose of a *base class* (also known as an *abstract class*) is to define functionality that is common to all the classes derived from it.</span></span> <span data-ttu-id="ec15c-106">Это позволяет сохранить производные классы от необходимости переопределять общие элементы.</span><span class="sxs-lookup"><span data-stu-id="ec15c-106">This saves the derived classes from having to redefine the common elements.</span></span> <span data-ttu-id="ec15c-107">В некоторых случаях эта общая функциональность не является достаточно полной для создания пригодного для использования объекта, и каждый производный класс определяет недостающие функциональные возможности.</span><span class="sxs-lookup"><span data-stu-id="ec15c-107">In some cases, this common functionality is not complete enough to make a usable object, and each derived class defines the missing functionality.</span></span> <span data-ttu-id="ec15c-108">В этом случае необходимо, чтобы код, создающий объекты, был создан только из производных классов.</span><span class="sxs-lookup"><span data-stu-id="ec15c-108">In such a case, you want the consuming code to create objects only from the derived classes.</span></span> <span data-ttu-id="ec15c-109">Для этого используйте `MustInherit` в базовом классе.</span><span class="sxs-lookup"><span data-stu-id="ec15c-109">You use `MustInherit` on the base class to enforce this.</span></span>  
  
 <span data-ttu-id="ec15c-110">Другое использование класса `MustInherit` заключается в ограничении переменной набором связанных классов.</span><span class="sxs-lookup"><span data-stu-id="ec15c-110">Another use of a `MustInherit` class is to restrict a variable to a set of related classes.</span></span> <span data-ttu-id="ec15c-111">Можно определить базовый класс и получить от него все связанные с ним классы.</span><span class="sxs-lookup"><span data-stu-id="ec15c-111">You can define a base class and derive all these related classes from it.</span></span> <span data-ttu-id="ec15c-112">Базовый класс не обязан предоставлять функциональные возможности, общие для всех производных классов, но он может служить фильтром для присвоения значений переменным.</span><span class="sxs-lookup"><span data-stu-id="ec15c-112">The base class does not need to provide any functionality common to all the derived classes, but it can serve as a filter for assigning values to variables.</span></span> <span data-ttu-id="ec15c-113">Если в используемом коде объявляется переменная в качестве базового класса, Visual Basic позволяет назначить этой переменной только один из производных классов.</span><span class="sxs-lookup"><span data-stu-id="ec15c-113">If your consuming code declares a variable as the base class, Visual Basic allows you to assign only an object from one of the derived classes to that variable.</span></span>  
  
 <span data-ttu-id="ec15c-114">.NET Framework определяет несколько классов `MustInherit`, между ними <xref:System.Array>, <xref:System.Enum>и <xref:System.ValueType>.</span><span class="sxs-lookup"><span data-stu-id="ec15c-114">The .NET Framework defines several `MustInherit` classes, among them <xref:System.Array>, <xref:System.Enum>, and <xref:System.ValueType>.</span></span> <span data-ttu-id="ec15c-115"><xref:System.ValueType> является примером базового класса, который ограничивают переменную.</span><span class="sxs-lookup"><span data-stu-id="ec15c-115"><xref:System.ValueType> is an example of a base class that restricts a variable.</span></span> <span data-ttu-id="ec15c-116">Все типы значений являются производными от <xref:System.ValueType>.</span><span class="sxs-lookup"><span data-stu-id="ec15c-116">All value types derive from <xref:System.ValueType>.</span></span> <span data-ttu-id="ec15c-117">Если переменная объявляется как <xref:System.ValueType>, то этой переменной можно назначить только типы значений.</span><span class="sxs-lookup"><span data-stu-id="ec15c-117">If you declare a variable as <xref:System.ValueType>, you can assign only value types to that variable.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="ec15c-118">Правила</span><span class="sxs-lookup"><span data-stu-id="ec15c-118">Rules</span></span>  
  
- <span data-ttu-id="ec15c-119">**Контекст объявления.**</span><span class="sxs-lookup"><span data-stu-id="ec15c-119">**Declaration Context.**</span></span> <span data-ttu-id="ec15c-120">`MustInherit` можно использовать только в инструкции `Class`.</span><span class="sxs-lookup"><span data-stu-id="ec15c-120">You can use `MustInherit` only in a `Class` statement.</span></span>  
  
- <span data-ttu-id="ec15c-121">**Комбинированные модификаторы.**</span><span class="sxs-lookup"><span data-stu-id="ec15c-121">**Combined Modifiers.**</span></span> <span data-ttu-id="ec15c-122">Нельзя указать `MustInherit` вместе с `NotInheritable` в одном объявлении.</span><span class="sxs-lookup"><span data-stu-id="ec15c-122">You cannot specify `MustInherit` together with `NotInheritable` in the same declaration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ec15c-123">Пример</span><span class="sxs-lookup"><span data-stu-id="ec15c-123">Example</span></span>  
 <span data-ttu-id="ec15c-124">В следующем примере показано принудительное наследование и принудительное переопределение.</span><span class="sxs-lookup"><span data-stu-id="ec15c-124">The following example illustrates both forced inheritance and forced overriding.</span></span> <span data-ttu-id="ec15c-125">Базовый класс `shape` определяет переменную `acrossLine`.</span><span class="sxs-lookup"><span data-stu-id="ec15c-125">The base class `shape` defines a variable `acrossLine`.</span></span> <span data-ttu-id="ec15c-126">Классы `circle` и `square` являются производными от `shape`.</span><span class="sxs-lookup"><span data-stu-id="ec15c-126">The classes `circle` and `square` derive from `shape`.</span></span> <span data-ttu-id="ec15c-127">Они наследуют определение `acrossLine`, но они должны определять функцию `area` поскольку вычисление для каждого вида формы различается.</span><span class="sxs-lookup"><span data-stu-id="ec15c-127">They inherit the definition of `acrossLine`, but they must define the function `area` because that calculation is different for each kind of shape.</span></span>  
  
 [!code-vb[VbVbalrKeywords#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class1.vb#2)]  
  
 <span data-ttu-id="ec15c-128">Можно объявить `shape1` и `shape2` типа `shape`.</span><span class="sxs-lookup"><span data-stu-id="ec15c-128">You can declare `shape1` and `shape2` to be of type `shape`.</span></span> <span data-ttu-id="ec15c-129">Однако нельзя создать объект из `shape`, так как в нем отсутствуют функциональные возможности функции `area` и он помечен как `MustInherit`.</span><span class="sxs-lookup"><span data-stu-id="ec15c-129">However, you cannot create an object from `shape` because it lacks the functionality of the function `area` and is marked `MustInherit`.</span></span>  
  
 <span data-ttu-id="ec15c-130">Поскольку они объявляются как `shape`, переменные `shape1` и `shape2` ограничиваются объектами из производных классов `circle` и `square`.</span><span class="sxs-lookup"><span data-stu-id="ec15c-130">Because they are declared as `shape`, the variables `shape1` and `shape2` are restricted to objects from the derived classes `circle` and `square`.</span></span> <span data-ttu-id="ec15c-131">Visual Basic не позволяет назначать другим объектам эти переменные, что обеспечивает высокий уровень безопасности типов.</span><span class="sxs-lookup"><span data-stu-id="ec15c-131">Visual Basic does not allow you to assign any other object to these variables, which gives you a high level of type safety.</span></span>  
  
## <a name="usage"></a><span data-ttu-id="ec15c-132">Использование</span><span class="sxs-lookup"><span data-stu-id="ec15c-132">Usage</span></span>  
 <span data-ttu-id="ec15c-133">Модификатор `MustInherit` можно использовать в этом контексте:</span><span class="sxs-lookup"><span data-stu-id="ec15c-133">The `MustInherit` modifier can be used in this context:</span></span>  
  
 [<span data-ttu-id="ec15c-134">Оператор Class</span><span class="sxs-lookup"><span data-stu-id="ec15c-134">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="ec15c-135">См. также</span><span class="sxs-lookup"><span data-stu-id="ec15c-135">See also</span></span>

- [<span data-ttu-id="ec15c-136">Оператор Inherits</span><span class="sxs-lookup"><span data-stu-id="ec15c-136">Inherits Statement</span></span>](../../../visual-basic/language-reference/statements/inherits-statement.md)
- [<span data-ttu-id="ec15c-137">NotInheritable</span><span class="sxs-lookup"><span data-stu-id="ec15c-137">NotInheritable</span></span>](../../../visual-basic/language-reference/modifiers/notinheritable.md)
- [<span data-ttu-id="ec15c-138">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="ec15c-138">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
- [<span data-ttu-id="ec15c-139">Основы наследования</span><span class="sxs-lookup"><span data-stu-id="ec15c-139">Inheritance Basics</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
