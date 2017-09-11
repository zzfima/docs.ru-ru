---
title: "Практическое руководство: объявление константы (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.constant
dev_langs:
- VB
helpviewer_keywords:
- Integer data type, declaring constants
- Single data type, declaring constants
- Const statement [Visual Basic], declaring constants
- procedures, declaration
- data types [Visual Basic], constants
- Long data type, declaring constants
- Visual Basic code, declaring variables and constants
- Double data type, declaring constants
- Boolean data type, declaring constants
- modules, declaring constants
- Byte data type, declaring constants
- constants, declaring
- Date data type, declaring constants
- String data type, declaring constants
- declaring constants, const keyword
- Currency data type, declaring constants and variants
- module-level constants and variables
- Object data type, declaring constants
ms.assetid: f901b4fa-481f-4621-822e-427060577ad1
caps.latest.revision: 20
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
ms.sourcegitcommit: 31905a37f09db5f5192123f0118252fbe8b02eff
ms.openlocfilehash: b7fc499336c2b5db3b4d2fe9c0cd11799ea0ad77
ms.contentlocale: ru-ru
ms.lasthandoff: 05/26/2017

---
# <a name="how-to-declare-a-constant-visual-basic"></a><span data-ttu-id="74086-102">Практическое руководство. Объявление константы (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="74086-102">How to: Declare A Constant (Visual Basic)</span></span>
<span data-ttu-id="74086-103">Использовать `Const` инструкцию, чтобы объявить константу и задать его значение.</span><span class="sxs-lookup"><span data-stu-id="74086-103">You use the `Const` statement to declare a constant and set its value.</span></span> <span data-ttu-id="74086-104">Определяя константу, присваивайте ей понятное имя, значение.</span><span class="sxs-lookup"><span data-stu-id="74086-104">By declaring a constant, you assign a meaningful name to a value.</span></span> <span data-ttu-id="74086-105">После объявления константы ее нельзя изменить или присвоить новое значение.</span><span class="sxs-lookup"><span data-stu-id="74086-105">Once a constant is declared, it cannot be modified or assigned a new value.</span></span>  
  
 <span data-ttu-id="74086-106">Объявление константы в процедуре либо в разделе объявлений модуля, класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="74086-106">You declare a constant within a procedure or in the declarations section of a module, class, or structure.</span></span> <span data-ttu-id="74086-107">Класс или структура уровня константы являются `Private` по умолчанию, но также может быть объявлен как `Public`, `Friend`, `Protected`, или `Protected Friend` для соответствующего уровня доступа к коду.</span><span class="sxs-lookup"><span data-stu-id="74086-107">Class or structure-level constants are `Private` by default, but may also be declared as `Public`, `Friend`, `Protected`, or `Protected Friend` for the appropriate level of code access.</span></span>  
  
 <span data-ttu-id="74086-108">Константа должна иметь допустимое символьное имя (правила совпадают имени для переменной) и выражение, состоящее из числовое или строковое констант и операторов (но не вызовов функций).</span><span class="sxs-lookup"><span data-stu-id="74086-108">The constant must have a valid symbolic name (the rules are the same as those for creating variable names) and an expression composed of numeric or string constants and operators (but no function calls).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-declare-a-constant"></a><span data-ttu-id="74086-109">Объявление константы</span><span class="sxs-lookup"><span data-stu-id="74086-109">To declare a constant</span></span>  
  
-   <span data-ttu-id="74086-110">Написать объявление, которое включает спецификатор доступа `Const` ключевое слово и выражение, как показано в следующих примерах:</span><span class="sxs-lookup"><span data-stu-id="74086-110">Write a declaration that includes an access specifier, the `Const` keyword, and an expression, as in the following examples:</span></span>  
  
     <span data-ttu-id="74086-111">[!code-vb[VbEnumsTask №&8;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-a-constant_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="74086-111">[!code-vb[VbEnumsTask#8](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-a-constant_1.vb)]</span></span>  
  
     <span data-ttu-id="74086-112">Когда [Option Infer](../../../../visual-basic/language-reference/statements/option-infer-statement.md) — `Off` и [Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md) — `On`, вы явным образом объявить константу, указав тип данных (`Boolean`, `Byte`, `Char`, `DateTime`, `Decimal`, `Double`, `Integer`, `Long`, `Short`, `Single`, или `String`).</span><span class="sxs-lookup"><span data-stu-id="74086-112">When [Option Infer](../../../../visual-basic/language-reference/statements/option-infer-statement.md) is `Off` and [Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md) is `On`, you must declare a constant explicitly by specifying a data type (`Boolean`, `Byte`, `Char`, `DateTime`, `Decimal`, `Double`, `Integer`, `Long`, `Short`, `Single`, or `String`).</span></span>  
  
     <span data-ttu-id="74086-113">Когда `Option Infer` — `On` или `Option Strict` — `Off`, можно объявить константу без указания типа данных с `As` предложения.</span><span class="sxs-lookup"><span data-stu-id="74086-113">When `Option Infer` is `On` or `Option Strict` is `Off`, you can declare a constant without specifying a data type with an `As` clause.</span></span> <span data-ttu-id="74086-114">Компилятор определяет тип константы из типа выражения.</span><span class="sxs-lookup"><span data-stu-id="74086-114">The compiler determines the type of the constant from the type of the expression.</span></span> <span data-ttu-id="74086-115">Дополнительные сведения см. в разделе [константы и типы данных литералов](constant-and-literal-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="74086-115">For more information, see [Constant and Literal Data Types](constant-and-literal-data-types.md).</span></span>  
  
### <a name="to-declare-a-constant-that-has-an-explicitly-stated-data-type"></a><span data-ttu-id="74086-116">Объявление константы с явно заданным типом данных</span><span class="sxs-lookup"><span data-stu-id="74086-116">To declare a constant that has an explicitly stated data type</span></span>  
  
-   <span data-ttu-id="74086-117">Написать объявление, которое включает в себя `As` ключевое слово и явного типа данных, как показано в следующих примерах:</span><span class="sxs-lookup"><span data-stu-id="74086-117">Write a declaration that includes the `As` keyword and an explicit data type, as in the following examples:</span></span>  
  
     <span data-ttu-id="74086-118">[!code-vb[VbEnumsTask №&9;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-a-constant_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="74086-118">[!code-vb[VbEnumsTask#9](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-a-constant_2.vb)]</span></span>  
  
     <span data-ttu-id="74086-119">В одной строке можно объявить несколько констант, хотя код более удобочитаемым, если объявлена только одна константа в строке.</span><span class="sxs-lookup"><span data-stu-id="74086-119">You can declare multiple constants on a single line, although your code is more readable if you declare only a single constant per line.</span></span> <span data-ttu-id="74086-120">Если в одной строке объявляется несколько констант, все они должны иметь тот же уровень доступа (`Public`, `Private`, `Friend`, `Protected`, или `Protected Friend`).</span><span class="sxs-lookup"><span data-stu-id="74086-120">If you declare multiple constants on a single line, they must all have the same access level (`Public`, `Private`, `Friend`, `Protected`, or `Protected Friend`).</span></span>  
  
### <a name="to-declare-multiple-constants-on-a-single-line"></a><span data-ttu-id="74086-121">Объявление нескольких констант в одной строке</span><span class="sxs-lookup"><span data-stu-id="74086-121">To declare multiple constants on a single line</span></span>  
  
-   <span data-ttu-id="74086-122">Разделите объявления запятой и пробелом, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="74086-122">Separate the declarations with a comma and a space, as in the following example:</span></span>  
  
    ```  
    Public Const Four As Integer = 4, Five As Integer = 5, Six As Integer = 44  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="74086-123">См. также</span><span class="sxs-lookup"><span data-stu-id="74086-123">See Also</span></span>  
 <span data-ttu-id="74086-124">[Оператор Const](../../../../visual-basic/language-reference/statements/const-statement.md) </span><span class="sxs-lookup"><span data-stu-id="74086-124">[Const Statement](../../../../visual-basic/language-reference/statements/const-statement.md) </span></span>  
<span data-ttu-id="74086-125"> [Типы данных констант и литералов](constant-and-literal-data-types.md) </span><span class="sxs-lookup"><span data-stu-id="74086-125"> [Constant and Literal Data Types](constant-and-literal-data-types.md) </span></span>  
<span data-ttu-id="74086-126"> [Общие сведения о константах](constants-overview.md)
 [как: объявление константы](how-to-declare-a-constant.md)
 [константы, определенные пользователем](user-defined-constants.md)
 [типы данных констант и литералов](constant-and-literal-data-types.md)
 [как: группы значений связанных констант](how-to-group-related-constant-values-together.md)
 [Общие сведения о перечислениях](enumerations-overview.md)
 [как: объявление перечисления](how-to-declare-enumerations.md)
 [как: ссылка на член перечисления](how-to-refer-to-an-enumeration-member.md)
 [перечисления и уточнение имен](enumerations-and-name-qualification.md)
 [как: перебор элементов перечисления](how-to-iterate-through-an-enumeration.md)
 [Практическое руководство: определение строки Связанные со значением перечисления](how-to-determine-the-string-associated-with-an-enumeration-value.md)
 [когда следует использовать перечисление](when-to-use-an-enumeration.md)</span><span class="sxs-lookup"><span data-stu-id="74086-126"> [Constants Overview](constants-overview.md)
 [How to: Declare A Constant](how-to-declare-a-constant.md)
 [User-Defined Constants](user-defined-constants.md)
 [Constant and Literal Data Types](constant-and-literal-data-types.md)
 [How to: Group Related Constant Values Together](how-to-group-related-constant-values-together.md)
 [Enumerations Overview](enumerations-overview.md)
 [How to: Declare Enumerations](how-to-declare-enumerations.md)
 [How to: Refer to an Enumeration Member](how-to-refer-to-an-enumeration-member.md)
 [Enumerations and Name Qualification](enumerations-and-name-qualification.md)
 [How to: Iterate Through An Enumeration](how-to-iterate-through-an-enumeration.md)
 [How to: Determine the String Associated with an Enumeration Value](how-to-determine-the-string-associated-with-an-enumeration-value.md)
 [When to Use an Enumeration](when-to-use-an-enumeration.md)</span></span>

 <span data-ttu-id="74086-127">[Общие сведения о перечислениях](enumerations-overview.md) </span><span class="sxs-lookup"><span data-stu-id="74086-127">[Enumerations Overview](enumerations-overview.md) </span></span>  
<span data-ttu-id="74086-128"> [Общие сведения о константах](constants-overview.md) </span><span class="sxs-lookup"><span data-stu-id="74086-128"> [Constants Overview](constants-overview.md) </span></span>  
<span data-ttu-id="74086-129"> [Практическое руководство: объявление перечисления](how-to-declare-enumerations.md) </span><span class="sxs-lookup"><span data-stu-id="74086-129"> [How to: Declare an Enumeration](how-to-declare-enumerations.md) </span></span>  
<span data-ttu-id="74086-130"> [Перечисления и уточнение имен](enumerations-and-name-qualification.md) </span><span class="sxs-lookup"><span data-stu-id="74086-130"> [Enumerations and Name Qualification](enumerations-and-name-qualification.md) </span></span>  
<span data-ttu-id="74086-131"> [Оператор Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md) </span><span class="sxs-lookup"><span data-stu-id="74086-131"> [Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md) </span></span>  
<span data-ttu-id="74086-132"> [Константы и перечисления](../../../../visual-basic/language-reference/constants-and-enumerations.md)</span><span class="sxs-lookup"><span data-stu-id="74086-132"> [Constants and Enumerations](../../../../visual-basic/language-reference/constants-and-enumerations.md)</span></span>

