---
title: Практическое руководство. Объявление константы (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.constant
helpviewer_keywords:
- Integer data type [Visual Basic], declaring constants
- Single data type [Visual Basic], declaring constants
- Const statement [Visual Basic], declaring constants
- procedures [Visual Basic], declaration
- data types [Visual Basic], constants
- Long data type [Visual Basic], declaring constants
- Visual Basic code, declaring variables and constants
- Double data type [Visual Basic], declaring constants
- Boolean data type [Visual Basic], declaring constants
- modules, declaring constants
- Byte data type [Visual Basic], declaring constants
- constants [Visual Basic], declaring
- Date data type [Visual Basic], declaring constants
- String data type [Visual Basic], declaring constants
- declaring constants [Visual Basic], const keyword
- Currency data type [Visual Basic], declaring constants and variants
- module-level constants and variables
- Object data type [Visual Basic], declaring constants
ms.assetid: f901b4fa-481f-4621-822e-427060577ad1
ms.openlocfilehash: ce45e4df7f74cd68bde0fb2adba10197a11edb1b
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/01/2018
ms.locfileid: "43394318"
---
# <a name="how-to-declare-a-constant-visual-basic"></a><span data-ttu-id="b3a6e-102">Практическое руководство. Объявление константы (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b3a6e-102">How to: Declare A Constant (Visual Basic)</span></span>
<span data-ttu-id="b3a6e-103">Использовании `Const` инструкцию, чтобы объявление константы и присвойте ему значение.</span><span class="sxs-lookup"><span data-stu-id="b3a6e-103">You use the `Const` statement to declare a constant and set its value.</span></span> <span data-ttu-id="b3a6e-104">Объявляя константу, понятное имя назначается значение.</span><span class="sxs-lookup"><span data-stu-id="b3a6e-104">By declaring a constant, you assign a meaningful name to a value.</span></span> <span data-ttu-id="b3a6e-105">После объявления константа не может изменить или присвоить новое значение.</span><span class="sxs-lookup"><span data-stu-id="b3a6e-105">Once a constant is declared, it cannot be modified or assigned a new value.</span></span>  
  
 <span data-ttu-id="b3a6e-106">Вы объявите константу в процедуре или в раздел объявлений модуля, класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="b3a6e-106">You declare a constant within a procedure or in the declarations section of a module, class, or structure.</span></span> <span data-ttu-id="b3a6e-107">Класс или структура на уровне константы являются `Private` по умолчанию, но также может быть объявлено как `Public`, `Friend`, `Protected`, или `Protected Friend` для соответствующего уровня доступа к коду.</span><span class="sxs-lookup"><span data-stu-id="b3a6e-107">Class or structure-level constants are `Private` by default, but may also be declared as `Public`, `Friend`, `Protected`, or `Protected Friend` for the appropriate level of code access.</span></span>  
  
 <span data-ttu-id="b3a6e-108">Константа должна иметь допустимое символическое имя (правила являются те же имени для переменной) и выражение, состоящее из числовой или строковый констант и операторов (но не вызовы функций).</span><span class="sxs-lookup"><span data-stu-id="b3a6e-108">The constant must have a valid symbolic name (the rules are the same as those for creating variable names) and an expression composed of numeric or string constants and operators (but no function calls).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-declare-a-constant"></a><span data-ttu-id="b3a6e-109">Объявление константы</span><span class="sxs-lookup"><span data-stu-id="b3a6e-109">To declare a constant</span></span>  
  
-   <span data-ttu-id="b3a6e-110">Написать объявление, которое включает спецификатор доступа `Const` ключевое слово и выражение, как показано в следующих примерах:</span><span class="sxs-lookup"><span data-stu-id="b3a6e-110">Write a declaration that includes an access specifier, the `Const` keyword, and an expression, as in the following examples:</span></span>  
  
     [!code-vb[VbEnumsTask#8](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-a-constant_1.vb)]  
  
     <span data-ttu-id="b3a6e-111">Когда [Option Infer](../../../../visual-basic/language-reference/statements/option-infer-statement.md) — `Off` и [Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md) — `On`, константа необходимо объявить явно путем указания типа данных (`Boolean`, `Byte`, `Char`, `DateTime`, `Decimal`, `Double`, `Integer`, `Long`, `Short`, `Single`, или `String`).</span><span class="sxs-lookup"><span data-stu-id="b3a6e-111">When [Option Infer](../../../../visual-basic/language-reference/statements/option-infer-statement.md) is `Off` and [Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md) is `On`, you must declare a constant explicitly by specifying a data type (`Boolean`, `Byte`, `Char`, `DateTime`, `Decimal`, `Double`, `Integer`, `Long`, `Short`, `Single`, or `String`).</span></span>  
  
     <span data-ttu-id="b3a6e-112">При `Option Infer` — `On` или `Option Strict` — `Off`, можно объявить без указания типа данных с константой `As` предложение.</span><span class="sxs-lookup"><span data-stu-id="b3a6e-112">When `Option Infer` is `On` or `Option Strict` is `Off`, you can declare a constant without specifying a data type with an `As` clause.</span></span> <span data-ttu-id="b3a6e-113">Компилятор определяет тип константы из типа выражения.</span><span class="sxs-lookup"><span data-stu-id="b3a6e-113">The compiler determines the type of the constant from the type of the expression.</span></span> <span data-ttu-id="b3a6e-114">Дополнительные сведения см. в разделе [константой, а также типы данных литералов](constant-and-literal-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="b3a6e-114">For more information, see [Constant and Literal Data Types](constant-and-literal-data-types.md).</span></span>  
  
### <a name="to-declare-a-constant-that-has-an-explicitly-stated-data-type"></a><span data-ttu-id="b3a6e-115">Объявление константы с явно заданным типом данных</span><span class="sxs-lookup"><span data-stu-id="b3a6e-115">To declare a constant that has an explicitly stated data type</span></span>  
  
-   <span data-ttu-id="b3a6e-116">Написать объявление, которое включает в себя `As` ключевое слово и явных типов данных, как показано в следующих примерах:</span><span class="sxs-lookup"><span data-stu-id="b3a6e-116">Write a declaration that includes the `As` keyword and an explicit data type, as in the following examples:</span></span>  
  
     [!code-vb[VbEnumsTask#9](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-a-constant_2.vb)]  
  
     <span data-ttu-id="b3a6e-117">Можно объявить несколько констант в одной строке, несмотря на то, что ваш код более удобочитаемым, если объявляется только одной константы в строке.</span><span class="sxs-lookup"><span data-stu-id="b3a6e-117">You can declare multiple constants on a single line, although your code is more readable if you declare only a single constant per line.</span></span> <span data-ttu-id="b3a6e-118">Если в одной строке объявляется несколько констант, все они должны иметь тот же уровень доступа (`Public`, `Private`, `Friend`, `Protected`, или `Protected Friend`).</span><span class="sxs-lookup"><span data-stu-id="b3a6e-118">If you declare multiple constants on a single line, they must all have the same access level (`Public`, `Private`, `Friend`, `Protected`, or `Protected Friend`).</span></span>  
  
### <a name="to-declare-multiple-constants-on-a-single-line"></a><span data-ttu-id="b3a6e-119">Объявление нескольких констант в одной строке</span><span class="sxs-lookup"><span data-stu-id="b3a6e-119">To declare multiple constants on a single line</span></span>  
  
-   <span data-ttu-id="b3a6e-120">Разделите объявления запятой и пробелом, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="b3a6e-120">Separate the declarations with a comma and a space, as in the following example:</span></span>  
  
    ```  
    Public Const Four As Integer = 4, Five As Integer = 5, Six As Integer = 44  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="b3a6e-121">См. также</span><span class="sxs-lookup"><span data-stu-id="b3a6e-121">See Also</span></span>  
 [<span data-ttu-id="b3a6e-122">Оператор Const</span><span class="sxs-lookup"><span data-stu-id="b3a6e-122">Const Statement</span></span>](../../../../visual-basic/language-reference/statements/const-statement.md)  
 [<span data-ttu-id="b3a6e-123">Типы данных констант и литералов</span><span class="sxs-lookup"><span data-stu-id="b3a6e-123">Constant and Literal Data Types</span></span>](constant-and-literal-data-types.md)  
 <span data-ttu-id="b3a6e-124">[Общие сведения о константах](constants-overview.md) [как: объявление константы](how-to-declare-a-constant.md) [константы, определенные пользователем](user-defined-constants.md) [типы данных констант и литералов](constant-and-literal-data-types.md) [как: группы Значений связанных констант](how-to-group-related-constant-values-together.md) [Общие сведения о перечислениях](enumerations-overview.md) [как: объявление перечислений](how-to-declare-enumerations.md) [как: ссылка на член перечисления](how-to-refer-to-an-enumeration-member.md) [Перечисления и уточнение имен](enumerations-and-name-qualification.md) [как: перебор элементов перечисления](how-to-iterate-through-an-enumeration.md) [как: определение строки, связанной со значением из перечисления](how-to-determine-the-string-associated-with-an-enumeration-value.md) [Когда следует использовать перечисление](when-to-use-an-enumeration.md)</span><span class="sxs-lookup"><span data-stu-id="b3a6e-124">[Constants Overview](constants-overview.md) [How to: Declare A Constant](how-to-declare-a-constant.md) [User-Defined Constants](user-defined-constants.md) [Constant and Literal Data Types](constant-and-literal-data-types.md) [How to: Group Related Constant Values Together](how-to-group-related-constant-values-together.md) [Enumerations Overview](enumerations-overview.md) [How to: Declare Enumerations](how-to-declare-enumerations.md) [How to: Refer to an Enumeration Member](how-to-refer-to-an-enumeration-member.md) [Enumerations and Name Qualification](enumerations-and-name-qualification.md) [How to: Iterate Through An Enumeration](how-to-iterate-through-an-enumeration.md) [How to: Determine the String Associated with an Enumeration Value](how-to-determine-the-string-associated-with-an-enumeration-value.md) [When to Use an Enumeration](when-to-use-an-enumeration.md)</span></span>

 [<span data-ttu-id="b3a6e-125">Общие сведения о перечислениях</span><span class="sxs-lookup"><span data-stu-id="b3a6e-125">Enumerations Overview</span></span>](enumerations-overview.md)  
 [<span data-ttu-id="b3a6e-126">Общие сведения о константах</span><span class="sxs-lookup"><span data-stu-id="b3a6e-126">Constants Overview</span></span>](constants-overview.md)  
 [<span data-ttu-id="b3a6e-127">Практическое: объявление перечисления</span><span class="sxs-lookup"><span data-stu-id="b3a6e-127">How to: Declare an Enumeration</span></span>](how-to-declare-enumerations.md)  
 [<span data-ttu-id="b3a6e-128">Перечисления и уточнение имен</span><span class="sxs-lookup"><span data-stu-id="b3a6e-128">Enumerations and Name Qualification</span></span>](enumerations-and-name-qualification.md)  
 [<span data-ttu-id="b3a6e-129">Оператор Option Strict</span><span class="sxs-lookup"><span data-stu-id="b3a6e-129">Option Strict Statement</span></span>](../../../../visual-basic/language-reference/statements/option-strict-statement.md)  
 [<span data-ttu-id="b3a6e-130">Константы и перечисления</span><span class="sxs-lookup"><span data-stu-id="b3a6e-130">Constants and Enumerations</span></span>](../../../../visual-basic/language-reference/constants-and-enumerations.md)
