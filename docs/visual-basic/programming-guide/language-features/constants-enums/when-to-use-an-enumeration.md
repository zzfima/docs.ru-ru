---
title: Когда следует использовать перечисление
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [Visual Basic]
ms.assetid: e6e47b5b-3ed9-452d-a481-9c3fed88519a
ms.openlocfilehash: 5daae8d487ddfe079a54e305e59e32e8ded8f65e
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74353963"
---
# <a name="when-to-use-an-enumeration-visual-basic"></a><span data-ttu-id="d84ec-102">Когда следует использовать перечисление (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d84ec-102">When to Use an Enumeration (Visual Basic)</span></span>
<span data-ttu-id="d84ec-103">Перечисления предлагают простой способ работы с наборами связанных констант.</span><span class="sxs-lookup"><span data-stu-id="d84ec-103">Enumerations offer an easy way to work with sets of related constants.</span></span> <span data-ttu-id="d84ec-104">Перечисление, или `Enum`, является символическим именем для набора значений.</span><span class="sxs-lookup"><span data-stu-id="d84ec-104">An enumeration, or `Enum`, is a symbolic name for a set of values.</span></span> <span data-ttu-id="d84ec-105">Перечисления обрабатываются как типы данных, и их можно использовать для создания наборов констант для использования с переменными и свойствами.</span><span class="sxs-lookup"><span data-stu-id="d84ec-105">Enumerations are treated as data types, and you can use them to create sets of constants for use with variables and properties.</span></span>  
  
## <a name="when-to-use-an-enumeration"></a><span data-ttu-id="d84ec-106">Когда следует использовать перечисление</span><span class="sxs-lookup"><span data-stu-id="d84ec-106">When to Use an Enumeration</span></span>  
 <span data-ttu-id="d84ec-107">Если процедура принимает ограниченный набор переменных, рекомендуется использовать перечисление.</span><span class="sxs-lookup"><span data-stu-id="d84ec-107">Whenever a procedure accepts a limited set of variables, consider using an enumeration.</span></span> <span data-ttu-id="d84ec-108">Перечисления делают более понятным и удобочитаемым кодом, особенно при использовании осмысленных имен.</span><span class="sxs-lookup"><span data-stu-id="d84ec-108">Enumerations make for clearer and more readable code, particularly when meaningful names are used.</span></span>  
  
 <span data-ttu-id="d84ec-109">Ниже перечислены преимущества использования перечислений.</span><span class="sxs-lookup"><span data-stu-id="d84ec-109">The benefits of using enumerations include:</span></span>  
  
- <span data-ttu-id="d84ec-110">Сокращает количество ошибок, вызванных перечислением или неотрицательным вводом чисел.</span><span class="sxs-lookup"><span data-stu-id="d84ec-110">Reduces errors caused by transposing or mistyping numbers.</span></span>  
  
- <span data-ttu-id="d84ec-111">Упрощает изменение значений в будущем.</span><span class="sxs-lookup"><span data-stu-id="d84ec-111">Makes it easy to change values in the future.</span></span>  
  
- <span data-ttu-id="d84ec-112">Упрощает чтение кода. Это означает, что менее вероятно, что ошибки будут отменяться.</span><span class="sxs-lookup"><span data-stu-id="d84ec-112">Makes code easier to read, which means it is less likely that errors will creep into it.</span></span>  
  
- <span data-ttu-id="d84ec-113">Обеспечивает прямую совместимость.</span><span class="sxs-lookup"><span data-stu-id="d84ec-113">Ensures forward compatibility.</span></span> <span data-ttu-id="d84ec-114">При использовании перечислений код менее вероятен, если в будущем кто-то изменит значения, соответствующие именам элементов.</span><span class="sxs-lookup"><span data-stu-id="d84ec-114">With enumerations, your code is less likely to fail if in the future someone changes the values corresponding to the member names.</span></span>  
  
## <a name="naming-enumerations"></a><span data-ttu-id="d84ec-115">Перечисления именования</span><span class="sxs-lookup"><span data-stu-id="d84ec-115">Naming Enumerations</span></span>  
 <span data-ttu-id="d84ec-116">Используйте соглашение об именовании для членов перечисления.</span><span class="sxs-lookup"><span data-stu-id="d84ec-116">Use a naming convention for enumeration members.</span></span> <span data-ttu-id="d84ec-117">Когда Visual Basic встречает имя члена перечисления, может возникнуть исключение, если другие библиотеки типов содержат одно и то же имя.</span><span class="sxs-lookup"><span data-stu-id="d84ec-117">When Visual Basic encounters an enumeration member name, an exception may be thrown if other referenced type libraries contain the same name.</span></span> <span data-ttu-id="d84ec-118">Используйте уникальный префикс, определяющий значения из приложения или компонента.</span><span class="sxs-lookup"><span data-stu-id="d84ec-118">Use a unique prefix that identifies the values from your application or component.</span></span>  
  
 <span data-ttu-id="d84ec-119">При ссылке на член перечисления необходимо уточнить имя члена с помощью имени перечисления или использовать оператор `Imports`.</span><span class="sxs-lookup"><span data-stu-id="d84ec-119">When referring to a member of an enumeration, you must qualify the member name with the enumeration name or else use the `Imports` statement.</span></span> <span data-ttu-id="d84ec-120">Дополнительные сведения см. в разделе [перечисления и квалификация имени](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md).</span><span class="sxs-lookup"><span data-stu-id="d84ec-120">For more information, see [Enumerations and Name Qualification](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md).</span></span>  
  
## <a name="predefined-enumerations"></a><span data-ttu-id="d84ec-121">Предопределенные перечисления</span><span class="sxs-lookup"><span data-stu-id="d84ec-121">Predefined Enumerations</span></span>  
 <span data-ttu-id="d84ec-122">Visual Basic предоставляет ряд предопределенных перечислений, таких как `FirstDayOfWeek` и `MsgBoxResult`, для упрощения кода.</span><span class="sxs-lookup"><span data-stu-id="d84ec-122">Visual Basic provides a number of predefined enumerations, such as `FirstDayOfWeek` and `MsgBoxResult`, to facilitate your code.</span></span> <span data-ttu-id="d84ec-123">Список этих элементов см. в разделе [константы и перечисления](../../../../visual-basic/language-reference/constants-and-enumerations.md).</span><span class="sxs-lookup"><span data-stu-id="d84ec-123">For a list of these see [Constants and Enumerations](../../../../visual-basic/language-reference/constants-and-enumerations.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d84ec-124">См. также</span><span class="sxs-lookup"><span data-stu-id="d84ec-124">See also</span></span>

- [<span data-ttu-id="d84ec-125">Инструкции. Объявление перечисления</span><span class="sxs-lookup"><span data-stu-id="d84ec-125">How to: Declare an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)
- [<span data-ttu-id="d84ec-126">Практическое руководство. Ссылка на элемент перечисления</span><span class="sxs-lookup"><span data-stu-id="d84ec-126">How to: Refer to an Enumeration Member</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)
- [<span data-ttu-id="d84ec-127">Перечисления и уточнение имен</span><span class="sxs-lookup"><span data-stu-id="d84ec-127">Enumerations and Name Qualification</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)
- [<span data-ttu-id="d84ec-128">Пошаговое руководство. перебор перечислений в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d84ec-128">How to: Iterate Through An Enumeration in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md)
- [<span data-ttu-id="d84ec-129">Практическое руководство. Определение строки, связанной со значением из перечисления</span><span class="sxs-lookup"><span data-stu-id="d84ec-129">How to: Determine the String Associated with an Enumeration Value</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md)
- [<span data-ttu-id="d84ec-130">Оператор Enum</span><span class="sxs-lookup"><span data-stu-id="d84ec-130">Enum Statement</span></span>](../../../../visual-basic/language-reference/statements/enum-statement.md)
- [<span data-ttu-id="d84ec-131">Константы и перечисления</span><span class="sxs-lookup"><span data-stu-id="d84ec-131">Constants and Enumerations</span></span>](../../../../visual-basic/language-reference/constants-and-enumerations.md)
