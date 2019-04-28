---
title: Когда следует использовать перечисление (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [Visual Basic]
ms.assetid: e6e47b5b-3ed9-452d-a481-9c3fed88519a
ms.openlocfilehash: ff2d8c324aee8bbccef050c020e5392368b05b1c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61907313"
---
# <a name="when-to-use-an-enumeration-visual-basic"></a><span data-ttu-id="ecebe-102">Когда следует использовать перечисление (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ecebe-102">When to Use an Enumeration (Visual Basic)</span></span>
<span data-ttu-id="ecebe-103">Перечисления предоставляют простой способ работы с наборами связанных констант.</span><span class="sxs-lookup"><span data-stu-id="ecebe-103">Enumerations offer an easy way to work with sets of related constants.</span></span> <span data-ttu-id="ecebe-104">Перечисление или `Enum`, является символическое имя для набора значений.</span><span class="sxs-lookup"><span data-stu-id="ecebe-104">An enumeration, or `Enum`, is a symbolic name for a set of values.</span></span> <span data-ttu-id="ecebe-105">Перечисления обрабатываются как типы данных и их можно использовать для создания наборов констант для использования с переменными и свойства.</span><span class="sxs-lookup"><span data-stu-id="ecebe-105">Enumerations are treated as data types, and you can use them to create sets of constants for use with variables and properties.</span></span>  
  
## <a name="when-to-use-an-enumeration"></a><span data-ttu-id="ecebe-106">Когда следует использовать перечисление</span><span class="sxs-lookup"><span data-stu-id="ecebe-106">When to Use an Enumeration</span></span>  
 <span data-ttu-id="ecebe-107">Когда процедура принимает ограниченный набор переменных, следует использовать перечисление.</span><span class="sxs-lookup"><span data-stu-id="ecebe-107">Whenever a procedure accepts a limited set of variables, consider using an enumeration.</span></span> <span data-ttu-id="ecebe-108">Перечисление делает код более удобочитаемым, особенно в том случае, если используются значимые имена.</span><span class="sxs-lookup"><span data-stu-id="ecebe-108">Enumerations make for clearer and more readable code, particularly when meaningful names are used.</span></span>  
  
 <span data-ttu-id="ecebe-109">Преимущества использования перечисления:</span><span class="sxs-lookup"><span data-stu-id="ecebe-109">The benefits of using enumerations include:</span></span>  
  
- <span data-ttu-id="ecebe-110">Сокращает число ошибок, вызванных перемещением или неправильным вводом значений.</span><span class="sxs-lookup"><span data-stu-id="ecebe-110">Reduces errors caused by transposing or mistyping numbers.</span></span>  
  
- <span data-ttu-id="ecebe-111">Позволяет легко изменять значения в будущем.</span><span class="sxs-lookup"><span data-stu-id="ecebe-111">Makes it easy to change values in the future.</span></span>  
  
- <span data-ttu-id="ecebe-112">Делает код более удобным для чтения, это означает, что это снижает вероятность возникновения ошибок в нем.</span><span class="sxs-lookup"><span data-stu-id="ecebe-112">Makes code easier to read, which means it is less likely that errors will creep into it.</span></span>  
  
- <span data-ttu-id="ecebe-113">Обеспечение прямой совместимости.</span><span class="sxs-lookup"><span data-stu-id="ecebe-113">Ensures forward compatibility.</span></span> <span data-ttu-id="ecebe-114">С помощью перечисления код является менее вероятны ошибки, если в будущем кто-то изменяет значения, соответствующие именам элементов.</span><span class="sxs-lookup"><span data-stu-id="ecebe-114">With enumerations, your code is less likely to fail if in the future someone changes the values corresponding to the member names.</span></span>  
  
## <a name="naming-enumerations"></a><span data-ttu-id="ecebe-115">Именование перечислений</span><span class="sxs-lookup"><span data-stu-id="ecebe-115">Naming Enumerations</span></span>  
 <span data-ttu-id="ecebe-116">Используйте соглашения об именовании для членов перечисления.</span><span class="sxs-lookup"><span data-stu-id="ecebe-116">Use a naming convention for enumeration members.</span></span> <span data-ttu-id="ecebe-117">Когда Visual Basic встречает имя члена перечисления, может быть исключение если тем же именем содержится в других библиотеках типов.</span><span class="sxs-lookup"><span data-stu-id="ecebe-117">When Visual Basic encounters an enumeration member name, an exception may be thrown if other referenced type libraries contain the same name.</span></span> <span data-ttu-id="ecebe-118">Используйте уникальный префикс, который определяет значения из своего приложения или компонента.</span><span class="sxs-lookup"><span data-stu-id="ecebe-118">Use a unique prefix that identifies the values from your application or component.</span></span>  
  
 <span data-ttu-id="ecebe-119">При ссылке на член перечисления, вам необходимо уточнить имя члена перечисления или воспользуйтесь `Imports` инструкции.</span><span class="sxs-lookup"><span data-stu-id="ecebe-119">When referring to a member of an enumeration, you must qualify the member name with the enumeration name or else use the `Imports` statement.</span></span> <span data-ttu-id="ecebe-120">Дополнительные сведения см. в разделе [перечисления и уточнение имен](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md).</span><span class="sxs-lookup"><span data-stu-id="ecebe-120">For more information, see [Enumerations and Name Qualification](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md).</span></span>  
  
## <a name="predefined-enumerations"></a><span data-ttu-id="ecebe-121">Предопределенные перечисления</span><span class="sxs-lookup"><span data-stu-id="ecebe-121">Predefined Enumerations</span></span>  
 <span data-ttu-id="ecebe-122">Visual Basic предоставляет ряд стандартных перечислений, таких как `FirstDayOfWeek` и `MsgBoxResult`, для упрощения кода.</span><span class="sxs-lookup"><span data-stu-id="ecebe-122">Visual Basic provides a number of predefined enumerations, such as `FirstDayOfWeek` and `MsgBoxResult`, to facilitate your code.</span></span> <span data-ttu-id="ecebe-123">Список кодов см. в разделе [константы и перечисления](../../../../visual-basic/language-reference/constants-and-enumerations.md).</span><span class="sxs-lookup"><span data-stu-id="ecebe-123">For a list of these see [Constants and Enumerations](../../../../visual-basic/language-reference/constants-and-enumerations.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ecebe-124">См. также</span><span class="sxs-lookup"><span data-stu-id="ecebe-124">See also</span></span>

- [<span data-ttu-id="ecebe-125">Практическое руководство. Объявления перечисления</span><span class="sxs-lookup"><span data-stu-id="ecebe-125">How to: Declare an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)
- [<span data-ttu-id="ecebe-126">Практическое руководство. Ссылка на член перечисления</span><span class="sxs-lookup"><span data-stu-id="ecebe-126">How to: Refer to an Enumeration Member</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)
- [<span data-ttu-id="ecebe-127">Перечисления и уточнение имен</span><span class="sxs-lookup"><span data-stu-id="ecebe-127">Enumerations and Name Qualification</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)
- [<span data-ttu-id="ecebe-128">Практическое руководство. Перебор элементов перечисления в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ecebe-128">How to: Iterate Through An Enumeration in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md)
- [<span data-ttu-id="ecebe-129">Практическое руководство. Определение строки, связанной со значением из перечисления</span><span class="sxs-lookup"><span data-stu-id="ecebe-129">How to: Determine the String Associated with an Enumeration Value</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md)
- [<span data-ttu-id="ecebe-130">Оператор Enum</span><span class="sxs-lookup"><span data-stu-id="ecebe-130">Enum Statement</span></span>](../../../../visual-basic/language-reference/statements/enum-statement.md)
- [<span data-ttu-id="ecebe-131">Константы и перечисления</span><span class="sxs-lookup"><span data-stu-id="ecebe-131">Constants and Enumerations</span></span>](../../../../visual-basic/language-reference/constants-and-enumerations.md)
