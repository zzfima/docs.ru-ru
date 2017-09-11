---
title: "Практическое руководство: объявление перечисления (Visual Basic) | Документы Microsoft"
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
- declarations, enumerations
- enumerations [Visual Basic], declaring
- declaring enumerations
ms.assetid: db4ca1c3-f429-4c81-ae81-29e0157b29fd
caps.latest.revision: 24
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
ms.openlocfilehash: 7adaca7e7252ce7165a5fd27b5bc9c049388206c
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-declare-enumerations-visual-basic"></a><span data-ttu-id="40b07-102">Практическое руководство. Объявление перечисления (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="40b07-102">How to: Declare Enumerations (Visual Basic)</span></span>
<span data-ttu-id="40b07-103">Создание перечисления с `Enum` инструкции в разделе объявлений класса или модуля.</span><span class="sxs-lookup"><span data-stu-id="40b07-103">You create an enumeration with the `Enum` statement in the declarations section of a class or module.</span></span> <span data-ttu-id="40b07-104">Нельзя объявить перечисление в методе.</span><span class="sxs-lookup"><span data-stu-id="40b07-104">You cannot declare an enumeration within a method.</span></span> <span data-ttu-id="40b07-105">Чтобы указать соответствующий уровень доступа, используйте `Private`, `Protected`, `Friend`, или `Public`.</span><span class="sxs-lookup"><span data-stu-id="40b07-105">To specify the appropriate level of access, use `Private`, `Protected`, `Friend`, or `Public`.</span></span>  
  
 <span data-ttu-id="40b07-106">`Enum` Тип имеет имя, базовый тип и набор полей, каждое из которых представляет собой константу.</span><span class="sxs-lookup"><span data-stu-id="40b07-106">An `Enum` type has a name, an underlying type, and a set of fields, each representing a constant.</span></span> <span data-ttu-id="40b07-107">Имя должно быть допустимым [!INCLUDE[vbprvblong](../../../../visual-basic/developing-apps/customizing-extending-my/includes/vbprvblong_md.md)] квалификатор.</span><span class="sxs-lookup"><span data-stu-id="40b07-107">The name must be a valid [!INCLUDE[vbprvblong](../../../../visual-basic/developing-apps/customizing-extending-my/includes/vbprvblong_md.md)] qualifier.</span></span> <span data-ttu-id="40b07-108">Базовый тип должен быть одним из целочисленных типов —`Byte`, `Short`, `Long` или `Integer`.</span><span class="sxs-lookup"><span data-stu-id="40b07-108">The underlying type must be one of the integer types—`Byte`, `Short`, `Long` or `Integer`.</span></span> <span data-ttu-id="40b07-109">Значение по умолчанию — `Integer`.</span><span class="sxs-lookup"><span data-stu-id="40b07-109">`Integer` is the default.</span></span> <span data-ttu-id="40b07-110">Перечисления всегда имеют строгие типы и не взаимозаменяемы с целочисленными типами.</span><span class="sxs-lookup"><span data-stu-id="40b07-110">Enumerations are always strongly typed and are not interchangeable with integer number types.</span></span>  
  
 <span data-ttu-id="40b07-111">Перечисления не могут иметь значений с плавающей запятой.</span><span class="sxs-lookup"><span data-stu-id="40b07-111">Enumerations cannot have floating-point values.</span></span> <span data-ttu-id="40b07-112">Если перечислению присваивается значение с плавающей запятой с `Option Strict On`, приведет к ошибке компилятора.</span><span class="sxs-lookup"><span data-stu-id="40b07-112">If an enumeration is assigned a floating-point value with `Option Strict On`, a compiler error results.</span></span> <span data-ttu-id="40b07-113">Если `Option Strict` — `Off`, значение автоматически преобразуется в `Enum` типа.</span><span class="sxs-lookup"><span data-stu-id="40b07-113">If `Option Strict` is `Off`, the value is automatically converted to the `Enum` type.</span></span>  
  
 <span data-ttu-id="40b07-114">Сведения об именах и использование `Imports` разделе инструкции, чтобы сделать уточнение имен нет необходимости, [перечисления и уточнение имен](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md).</span><span class="sxs-lookup"><span data-stu-id="40b07-114">For information on names, and how to use the `Imports` statement to make name qualification unnecessary, see [Enumerations and Name Qualification](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md).</span></span>  
  
### <a name="to-declare-an-enumeration"></a><span data-ttu-id="40b07-115">Объявление перечисления</span><span class="sxs-lookup"><span data-stu-id="40b07-115">To declare an enumeration</span></span>  
  
1.  <span data-ttu-id="40b07-116">Написать объявление, которое включает уровень доступа к коду, `Enum` ключевое слово и допустимое имя, как показано в следующих примерах, каждый из которых объявляет различные `Enum`.</span><span class="sxs-lookup"><span data-stu-id="40b07-116">Write a declaration that includes a code access level, the `Enum` keyword, and a valid name, as in the following examples, each of which declares a different `Enum`.</span></span>  
  
     <span data-ttu-id="40b07-117">[!code-vb[VbEnumsTask&#3;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-enumerations_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="40b07-117">[!code-vb[VbEnumsTask#3](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-enumerations_1.vb)]</span></span>  
  
2.  <span data-ttu-id="40b07-118">Определите константы в перечислении.</span><span class="sxs-lookup"><span data-stu-id="40b07-118">Define the constants in the enumeration.</span></span> <span data-ttu-id="40b07-119">По умолчанию первая константа перечисления инициализируется `0`, и каждая последующая константа инициализируется значение на единицу больше, чем значение предыдущей константы.</span><span class="sxs-lookup"><span data-stu-id="40b07-119">By default, the first constant in an enumeration is initialized to `0`, and subsequent constants are initialized to a value of one more than the previous constant.</span></span> <span data-ttu-id="40b07-120">Например, следующее перечисление `Days`, содержит константу с именем `Sunday` со значением `0`, константу с именем `Monday` со значением `1`, константу с именем `Tuesday` со значением `2`, и т. д.</span><span class="sxs-lookup"><span data-stu-id="40b07-120">For example, the following enumeration, `Days`, contains a constant named `Sunday` with the value `0`, a constant named `Monday` with the value `1`, a constant named `Tuesday` with the value of `2`, and so on.</span></span>  
  
     <span data-ttu-id="40b07-121">[!code-vb[VbEnumsTask&#4;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-enumerations_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="40b07-121">[!code-vb[VbEnumsTask#4](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-enumerations_2.vb)]</span></span>  
  
3.  <span data-ttu-id="40b07-122">Можно явным образом присвоить значения константам перечисления с помощью оператора присваивания.</span><span class="sxs-lookup"><span data-stu-id="40b07-122">You can explicitly assign values to constants in an enumeration by using an assignment statement.</span></span> <span data-ttu-id="40b07-123">Можно назначить любое целочисленное значение, включая отрицательные числа.</span><span class="sxs-lookup"><span data-stu-id="40b07-123">You can assign any integer value, including negative numbers.</span></span> <span data-ttu-id="40b07-124">Например можно привести константы с отрицательными значениями в ту или иную ошибку.</span><span class="sxs-lookup"><span data-stu-id="40b07-124">For example, you may want constants with values less than zero to represent error conditions.</span></span> <span data-ttu-id="40b07-125">В следующем примере константа `Invalid` явным образом присваивается значение `–1`, а константа `Sunday` присваивается значение `0`.</span><span class="sxs-lookup"><span data-stu-id="40b07-125">In the following enumeration, the constant `Invalid` is explicitly assigned the value `–1`, and the constant `Sunday` is assigned the value `0`.</span></span> <span data-ttu-id="40b07-126">Поскольку это первая константа перечисления, `Saturday` также инициализируется значение `0`.</span><span class="sxs-lookup"><span data-stu-id="40b07-126">Because it is the first constant in the enumeration, `Saturday` is also initialized to the value `0`.</span></span> <span data-ttu-id="40b07-127">Значение `Monday` — `1` (на единицу больше, чем значение `Sunday`); значение `Tuesday` — `2`, и т. д.</span><span class="sxs-lookup"><span data-stu-id="40b07-127">The value of `Monday` is `1` (one more than the value of `Sunday`); the value of `Tuesday` is `2`, and so on.</span></span>  
  
     <span data-ttu-id="40b07-128">[!code-vb[VbEnumsTask&#5;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-enumerations_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="40b07-128">[!code-vb[VbEnumsTask#5](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-enumerations_3.vb)]</span></span>  
  
### <a name="to-declare-an-enumeration-as-an-explicit-type"></a><span data-ttu-id="40b07-129">Для объявления перечисления в виде явного типа</span><span class="sxs-lookup"><span data-stu-id="40b07-129">To declare an enumeration as an explicit type</span></span>  
  
-   <span data-ttu-id="40b07-130">Укажите тип перечисления с помощью `As` , как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="40b07-130">Specify the type of the enum by using the `As` clause, as shown in the following example.</span></span>  
  
     <span data-ttu-id="40b07-131">[!code-vb[VbEnumsTask №&6;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-enumerations_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="40b07-131">[!code-vb[VbEnumsTask#6](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-enumerations_4.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40b07-132">См. также</span><span class="sxs-lookup"><span data-stu-id="40b07-132">See Also</span></span>  
 <span data-ttu-id="40b07-133">[Перечисления и уточнение имен](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md) </span><span class="sxs-lookup"><span data-stu-id="40b07-133">[Enumerations and Name Qualification](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md) </span></span>  
<span data-ttu-id="40b07-134"> [Практическое руководство: ссылка на член перечисления](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md) </span><span class="sxs-lookup"><span data-stu-id="40b07-134"> [How to: Refer to an Enumeration Member](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md) </span></span>  
<span data-ttu-id="40b07-135"> [Практическое руководство: перебор элементов перечисления в Visual Basic](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md) </span><span class="sxs-lookup"><span data-stu-id="40b07-135"> [How to: Iterate Through An Enumeration in Visual Basic](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md) </span></span>  
<span data-ttu-id="40b07-136"> [Практическое руководство: определение строки, связанной со значением перечисления](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md) </span><span class="sxs-lookup"><span data-stu-id="40b07-136"> [How to: Determine the String Associated with an Enumeration Value](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md) </span></span>  
<span data-ttu-id="40b07-137"> [Когда следует использовать перечисление](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md) </span><span class="sxs-lookup"><span data-stu-id="40b07-137"> [When to Use an Enumeration](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md) </span></span>  
<span data-ttu-id="40b07-138"> [Общие сведения о константах](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md) </span><span class="sxs-lookup"><span data-stu-id="40b07-138"> [Constants Overview](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md) </span></span>  
<span data-ttu-id="40b07-139"> [Типы данных констант и литералов](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md) </span><span class="sxs-lookup"><span data-stu-id="40b07-139"> [Constant and Literal Data Types](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md) </span></span>  
<span data-ttu-id="40b07-140"> [Константы и перечисления](../../../../visual-basic/language-reference/constants-and-enumerations.md)</span><span class="sxs-lookup"><span data-stu-id="40b07-140"> [Constants and Enumerations](../../../../visual-basic/language-reference/constants-and-enumerations.md)</span></span>
