---
title: Когда следует использовать перечисление (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [Visual Basic]
ms.assetid: e6e47b5b-3ed9-452d-a481-9c3fed88519a
ms.openlocfilehash: e50057e114abae9fbf05c94ef0b60cf94b033a2b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33647314"
---
# <a name="when-to-use-an-enumeration-visual-basic"></a><span data-ttu-id="739e9-102">Когда следует использовать перечисление (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="739e9-102">When to Use an Enumeration (Visual Basic)</span></span>
<span data-ttu-id="739e9-103">Перечисления предоставляют простой способ работы с наборами связанных констант.</span><span class="sxs-lookup"><span data-stu-id="739e9-103">Enumerations offer an easy way to work with sets of related constants.</span></span> <span data-ttu-id="739e9-104">Перечисление или `Enum`, является символическое имя для набора значений.</span><span class="sxs-lookup"><span data-stu-id="739e9-104">An enumeration, or `Enum`, is a symbolic name for a set of values.</span></span> <span data-ttu-id="739e9-105">Перечисления обрабатываются как типы данных и их можно использовать для создания наборов констант для использования с переменными и свойства.</span><span class="sxs-lookup"><span data-stu-id="739e9-105">Enumerations are treated as data types, and you can use them to create sets of constants for use with variables and properties.</span></span>  
  
## <a name="when-to-use-an-enumeration"></a><span data-ttu-id="739e9-106">Когда следует использовать перечисление</span><span class="sxs-lookup"><span data-stu-id="739e9-106">When to Use an Enumeration</span></span>  
 <span data-ttu-id="739e9-107">Когда процедура принимает ограниченный набор переменных, следует использовать перечисление.</span><span class="sxs-lookup"><span data-stu-id="739e9-107">Whenever a procedure accepts a limited set of variables, consider using an enumeration.</span></span> <span data-ttu-id="739e9-108">Перечисление делает код более удобочитаемым, особенно в том случае, если используются значимые имена.</span><span class="sxs-lookup"><span data-stu-id="739e9-108">Enumerations make for clearer and more readable code, particularly when meaningful names are used.</span></span>  
  
 <span data-ttu-id="739e9-109">Преимущества использования перечисления:</span><span class="sxs-lookup"><span data-stu-id="739e9-109">The benefits of using enumerations include:</span></span>  
  
-   <span data-ttu-id="739e9-110">Уменьшает количество ошибок, вызванных перемещением или неправильным вводом значений.</span><span class="sxs-lookup"><span data-stu-id="739e9-110">Reduces errors caused by transposing or mistyping numbers.</span></span>  
  
-   <span data-ttu-id="739e9-111">Позволяет легко изменять значения в будущем.</span><span class="sxs-lookup"><span data-stu-id="739e9-111">Makes it easy to change values in the future.</span></span>  
  
-   <span data-ttu-id="739e9-112">Делает код более удобным для чтения, это означает, что это снижает вероятность возникновения ошибок в нем.</span><span class="sxs-lookup"><span data-stu-id="739e9-112">Makes code easier to read, which means it is less likely that errors will creep into it.</span></span>  
  
-   <span data-ttu-id="739e9-113">Обеспечение прямой совместимости.</span><span class="sxs-lookup"><span data-stu-id="739e9-113">Ensures forward compatibility.</span></span> <span data-ttu-id="739e9-114">Для перечислений код является менее вероятны, если в будущем уведомлений об изменении значения, соответствующие именам элементов.</span><span class="sxs-lookup"><span data-stu-id="739e9-114">With enumerations, your code is less likely to fail if in the future someone changes the values corresponding to the member names.</span></span>  
  
## <a name="naming-enumerations"></a><span data-ttu-id="739e9-115">Именование перечислений</span><span class="sxs-lookup"><span data-stu-id="739e9-115">Naming Enumerations</span></span>  
 <span data-ttu-id="739e9-116">Используйте соглашение об именовании для элементов перечисления.</span><span class="sxs-lookup"><span data-stu-id="739e9-116">Use a naming convention for enumeration members.</span></span> <span data-ttu-id="739e9-117">Когда Visual Basic встречает имя члена перечисления, исключение может возникать, если то же имя содержится в других библиотеках типов.</span><span class="sxs-lookup"><span data-stu-id="739e9-117">When Visual Basic encounters an enumeration member name, an exception may be thrown if other referenced type libraries contain the same name.</span></span> <span data-ttu-id="739e9-118">Используйте уникальный префикс для идентификации значения из приложения или компонента.</span><span class="sxs-lookup"><span data-stu-id="739e9-118">Use a unique prefix that identifies the values from your application or component.</span></span>  
  
 <span data-ttu-id="739e9-119">При ссылке на член перечисления, вам необходимо уточнить имя члена с именем перечисления или воспользуйтесь `Imports` инструкции.</span><span class="sxs-lookup"><span data-stu-id="739e9-119">When referring to a member of an enumeration, you must qualify the member name with the enumeration name or else use the `Imports` statement.</span></span> <span data-ttu-id="739e9-120">Дополнительные сведения см. в разделе [перечисления и уточнение имен](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md).</span><span class="sxs-lookup"><span data-stu-id="739e9-120">For more information, see [Enumerations and Name Qualification](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md).</span></span>  
  
## <a name="predefined-enumerations"></a><span data-ttu-id="739e9-121">Предопределенные перечисления</span><span class="sxs-lookup"><span data-stu-id="739e9-121">Predefined Enumerations</span></span>  
 <span data-ttu-id="739e9-122">Visual Basic предоставляет ряд стандартных перечислений, таких как `FirstDayOfWeek` и `MsgBoxResult`, для упрощения кода.</span><span class="sxs-lookup"><span data-stu-id="739e9-122">Visual Basic provides a number of predefined enumerations, such as `FirstDayOfWeek` and `MsgBoxResult`, to facilitate your code.</span></span> <span data-ttu-id="739e9-123">Список этих разделе [константы и перечисления](../../../../visual-basic/language-reference/constants-and-enumerations.md).</span><span class="sxs-lookup"><span data-stu-id="739e9-123">For a list of these see [Constants and Enumerations](../../../../visual-basic/language-reference/constants-and-enumerations.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="739e9-124">См. также</span><span class="sxs-lookup"><span data-stu-id="739e9-124">See Also</span></span>  
 [<span data-ttu-id="739e9-125">Как: объявление перечисления</span><span class="sxs-lookup"><span data-stu-id="739e9-125">How to: Declare an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)  
 [<span data-ttu-id="739e9-126">Практическое руководство. Ссылка на элемент перечисления</span><span class="sxs-lookup"><span data-stu-id="739e9-126">How to: Refer to an Enumeration Member</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)  
 [<span data-ttu-id="739e9-127">Перечисления и уточнение имен</span><span class="sxs-lookup"><span data-stu-id="739e9-127">Enumerations and Name Qualification</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)  
 [<span data-ttu-id="739e9-128">Как: перебор элементов перечисления в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="739e9-128">How to: Iterate Through An Enumeration in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md)  
 [<span data-ttu-id="739e9-129">Практическое руководство. Определение строки, связанной со значением из перечисления</span><span class="sxs-lookup"><span data-stu-id="739e9-129">How to: Determine the String Associated with an Enumeration Value</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md)  
 [<span data-ttu-id="739e9-130">Оператор Enum</span><span class="sxs-lookup"><span data-stu-id="739e9-130">Enum Statement</span></span>](../../../../visual-basic/language-reference/statements/enum-statement.md)  
 [<span data-ttu-id="739e9-131">Константы и перечисления</span><span class="sxs-lookup"><span data-stu-id="739e9-131">Constants and Enumerations</span></span>](../../../../visual-basic/language-reference/constants-and-enumerations.md)
