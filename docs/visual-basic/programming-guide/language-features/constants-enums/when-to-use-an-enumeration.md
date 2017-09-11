---
title: "Когда следует использовать перечисление (Visual Basic) | Документы Microsoft"
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
- enumerations [Visual Basic]
ms.assetid: e6e47b5b-3ed9-452d-a481-9c3fed88519a
caps.latest.revision: 12
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
ms.openlocfilehash: 3853950382fd4336c569f9d772aea3c1312f2ebc
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="when-to-use-an-enumeration-visual-basic"></a><span data-ttu-id="ffdea-102">Когда следует использовать перечисление (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ffdea-102">When to Use an Enumeration (Visual Basic)</span></span>
<span data-ttu-id="ffdea-103">Перечисления предоставляют простой способ работы с наборами связанных констант.</span><span class="sxs-lookup"><span data-stu-id="ffdea-103">Enumerations offer an easy way to work with sets of related constants.</span></span> <span data-ttu-id="ffdea-104">Перечисление или `Enum`, является символическим именем для набора значений.</span><span class="sxs-lookup"><span data-stu-id="ffdea-104">An enumeration, or `Enum`, is a symbolic name for a set of values.</span></span> <span data-ttu-id="ffdea-105">Перечисления обрабатываются как типы данных и их можно использовать для создания наборов констант для использования с переменными и свойствами.</span><span class="sxs-lookup"><span data-stu-id="ffdea-105">Enumerations are treated as data types, and you can use them to create sets of constants for use with variables and properties.</span></span>  
  
## <a name="when-to-use-an-enumeration"></a><span data-ttu-id="ffdea-106">Когда следует использовать перечисление</span><span class="sxs-lookup"><span data-stu-id="ffdea-106">When to Use an Enumeration</span></span>  
 <span data-ttu-id="ffdea-107">Когда процедура принимает ограниченный набор переменных, следует использовать перечисление.</span><span class="sxs-lookup"><span data-stu-id="ffdea-107">Whenever a procedure accepts a limited set of variables, consider using an enumeration.</span></span> <span data-ttu-id="ffdea-108">Перечисление делает код более удобочитаемым, особенно при использовании осмысленных имен.</span><span class="sxs-lookup"><span data-stu-id="ffdea-108">Enumerations make for clearer and more readable code, particularly when meaningful names are used.</span></span>  
  
 <span data-ttu-id="ffdea-109">Преимущества использования перечисления:</span><span class="sxs-lookup"><span data-stu-id="ffdea-109">The benefits of using enumerations include:</span></span>  
  
-   <span data-ttu-id="ffdea-110">Уменьшает количество ошибок, вызванных перемещением или неправильным вводом значений.</span><span class="sxs-lookup"><span data-stu-id="ffdea-110">Reduces errors caused by transposing or mistyping numbers.</span></span>  
  
-   <span data-ttu-id="ffdea-111">Позволяет легко изменять значения в будущем.</span><span class="sxs-lookup"><span data-stu-id="ffdea-111">Makes it easy to change values in the future.</span></span>  
  
-   <span data-ttu-id="ffdea-112">Делает код более удобными для чтения, это означает, что это снижает вероятность возникновения ошибок в нем.</span><span class="sxs-lookup"><span data-stu-id="ffdea-112">Makes code easier to read, which means it is less likely that errors will creep into it.</span></span>  
  
-   <span data-ttu-id="ffdea-113">Обеспечение прямой совместимости.</span><span class="sxs-lookup"><span data-stu-id="ffdea-113">Ensures forward compatibility.</span></span> <span data-ttu-id="ffdea-114">Для перечислений код вероятность возникновения ошибок, если в будущем кто-то изменяет значения, соответствующие именам элементов.</span><span class="sxs-lookup"><span data-stu-id="ffdea-114">With enumerations, your code is less likely to fail if in the future someone changes the values corresponding to the member names.</span></span>  
  
## <a name="naming-enumerations"></a><span data-ttu-id="ffdea-115">Именование перечислений</span><span class="sxs-lookup"><span data-stu-id="ffdea-115">Naming Enumerations</span></span>  
 <span data-ttu-id="ffdea-116">Используйте соглашения об именах для членов перечисления.</span><span class="sxs-lookup"><span data-stu-id="ffdea-116">Use a naming convention for enumeration members.</span></span> <span data-ttu-id="ffdea-117">Когда [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] встречается имя члена перечисления, может быть исключение, если то же имя содержится в других библиотеках типов.</span><span class="sxs-lookup"><span data-stu-id="ffdea-117">When [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] encounters an enumeration member name, an exception may be thrown if other referenced type libraries contain the same name.</span></span> <span data-ttu-id="ffdea-118">Используйте уникальный префикс для идентификации значения из приложения или компонента.</span><span class="sxs-lookup"><span data-stu-id="ffdea-118">Use a unique prefix that identifies the values from your application or component.</span></span>  
  
 <span data-ttu-id="ffdea-119">При ссылке на член перечисления, вам необходимо уточнить имя члена с помощью имени перечисления или воспользуйтесь `Imports` инструкции.</span><span class="sxs-lookup"><span data-stu-id="ffdea-119">When referring to a member of an enumeration, you must qualify the member name with the enumeration name or else use the `Imports` statement.</span></span> <span data-ttu-id="ffdea-120">Дополнительные сведения см. в разделе [перечисления и уточнение имен](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md).</span><span class="sxs-lookup"><span data-stu-id="ffdea-120">For more information, see [Enumerations and Name Qualification](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md).</span></span>  
  
## <a name="predefined-enumerations"></a><span data-ttu-id="ffdea-121">Предопределенные перечисления</span><span class="sxs-lookup"><span data-stu-id="ffdea-121">Predefined Enumerations</span></span>  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="ffdea-122">предоставляет ряд стандартных перечислений, таких как `FirstDayOfWeek` и `MsgBoxResul`t для упрощения кода.</span><span class="sxs-lookup"><span data-stu-id="ffdea-122"> provides a number of predefined enumerations, such as `FirstDayOfWeek` and `MsgBoxResul`t, to facilitate your code.</span></span> <span data-ttu-id="ffdea-123">Список кодов см. [константы и перечисления](../../../../visual-basic/language-reference/constants-and-enumerations.md).</span><span class="sxs-lookup"><span data-stu-id="ffdea-123">For a list of these see [Constants and Enumerations](../../../../visual-basic/language-reference/constants-and-enumerations.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ffdea-124">См. также</span><span class="sxs-lookup"><span data-stu-id="ffdea-124">See Also</span></span>  
 <span data-ttu-id="ffdea-125">[Практическое руководство: объявление перечисления](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md) </span><span class="sxs-lookup"><span data-stu-id="ffdea-125">[How to: Declare an Enumeration](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md) </span></span>  
<span data-ttu-id="ffdea-126"> [Практическое руководство: ссылка на член перечисления](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md) </span><span class="sxs-lookup"><span data-stu-id="ffdea-126"> [How to: Refer to an Enumeration Member](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md) </span></span>  
<span data-ttu-id="ffdea-127"> [Перечисления и уточнение имен](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md) </span><span class="sxs-lookup"><span data-stu-id="ffdea-127"> [Enumerations and Name Qualification](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md) </span></span>  
<span data-ttu-id="ffdea-128"> [Практическое руководство: перебор элементов перечисления в Visual Basic](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md) </span><span class="sxs-lookup"><span data-stu-id="ffdea-128"> [How to: Iterate Through An Enumeration in Visual Basic](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md) </span></span>  
<span data-ttu-id="ffdea-129"> [Практическое руководство: определение строки, связанной со значением перечисления](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md) </span><span class="sxs-lookup"><span data-stu-id="ffdea-129"> [How to: Determine the String Associated with an Enumeration Value](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md) </span></span>  
<span data-ttu-id="ffdea-130"> [Оператор Enum](../../../../visual-basic/language-reference/statements/enum-statement.md) </span><span class="sxs-lookup"><span data-stu-id="ffdea-130"> [Enum Statement](../../../../visual-basic/language-reference/statements/enum-statement.md) </span></span>  
<span data-ttu-id="ffdea-131"> [Константы и перечисления](../../../../visual-basic/language-reference/constants-and-enumerations.md)</span><span class="sxs-lookup"><span data-stu-id="ffdea-131"> [Constants and Enumerations](../../../../visual-basic/language-reference/constants-and-enumerations.md)</span></span>
