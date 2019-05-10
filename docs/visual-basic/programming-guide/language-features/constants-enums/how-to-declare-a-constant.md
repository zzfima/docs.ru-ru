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
ms.openlocfilehash: b84afe4e354d4029bc61ba67bc93bd36a3430de4
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64610601"
---
# <a name="how-to-declare-a-constant-visual-basic"></a><span data-ttu-id="acae7-102">Практическое руководство. Объявление константы (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="acae7-102">How to: Declare A Constant (Visual Basic)</span></span>
<span data-ttu-id="acae7-103">Использовании `Const` инструкцию, чтобы объявление константы и присвойте ему значение.</span><span class="sxs-lookup"><span data-stu-id="acae7-103">You use the `Const` statement to declare a constant and set its value.</span></span> <span data-ttu-id="acae7-104">Объявляя константу, понятное имя назначается значение.</span><span class="sxs-lookup"><span data-stu-id="acae7-104">By declaring a constant, you assign a meaningful name to a value.</span></span> <span data-ttu-id="acae7-105">После объявления константа не может изменить или присвоить новое значение.</span><span class="sxs-lookup"><span data-stu-id="acae7-105">Once a constant is declared, it cannot be modified or assigned a new value.</span></span>  
  
 <span data-ttu-id="acae7-106">Вы объявите константу в процедуре или в раздел объявлений модуля, класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="acae7-106">You declare a constant within a procedure or in the declarations section of a module, class, or structure.</span></span> <span data-ttu-id="acae7-107">Класс или структура на уровне константы являются `Private` по умолчанию, но также может быть объявлено как `Public`, `Friend`, `Protected`, или `Protected Friend` для соответствующего уровня доступа к коду.</span><span class="sxs-lookup"><span data-stu-id="acae7-107">Class or structure-level constants are `Private` by default, but may also be declared as `Public`, `Friend`, `Protected`, or `Protected Friend` for the appropriate level of code access.</span></span>  
  
 <span data-ttu-id="acae7-108">Константа должна иметь допустимое символическое имя (правила являются те же имени для переменной) и выражение, состоящее из числовой или строковый констант и операторов (но не вызовы функций).</span><span class="sxs-lookup"><span data-stu-id="acae7-108">The constant must have a valid symbolic name (the rules are the same as those for creating variable names) and an expression composed of numeric or string constants and operators (but no function calls).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-declare-a-constant"></a><span data-ttu-id="acae7-109">Объявление константы</span><span class="sxs-lookup"><span data-stu-id="acae7-109">To declare a constant</span></span>  
  
- <span data-ttu-id="acae7-110">Написать объявление, которое включает спецификатор доступа `Const` ключевое слово и выражение, как показано в следующих примерах:</span><span class="sxs-lookup"><span data-stu-id="acae7-110">Write a declaration that includes an access specifier, the `Const` keyword, and an expression, as in the following examples:</span></span>  
  
     [!code-vb[VbEnumsTask#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#8)]  
  
     <span data-ttu-id="acae7-111">Когда [Option Infer](../../../../visual-basic/language-reference/statements/option-infer-statement.md) — `Off` и [Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md) — `On`, константа необходимо объявить явно путем указания типа данных (`Boolean`, `Byte`, `Char`, `DateTime`, `Decimal`, `Double`, `Integer`, `Long`, `Short`, `Single`, или `String`).</span><span class="sxs-lookup"><span data-stu-id="acae7-111">When [Option Infer](../../../../visual-basic/language-reference/statements/option-infer-statement.md) is `Off` and [Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md) is `On`, you must declare a constant explicitly by specifying a data type (`Boolean`, `Byte`, `Char`, `DateTime`, `Decimal`, `Double`, `Integer`, `Long`, `Short`, `Single`, or `String`).</span></span>  
  
     <span data-ttu-id="acae7-112">При `Option Infer` — `On` или `Option Strict` — `Off`, можно объявить без указания типа данных с константой `As` предложение.</span><span class="sxs-lookup"><span data-stu-id="acae7-112">When `Option Infer` is `On` or `Option Strict` is `Off`, you can declare a constant without specifying a data type with an `As` clause.</span></span> <span data-ttu-id="acae7-113">Компилятор определяет тип константы из типа выражения.</span><span class="sxs-lookup"><span data-stu-id="acae7-113">The compiler determines the type of the constant from the type of the expression.</span></span> <span data-ttu-id="acae7-114">Дополнительные сведения см. в разделе [константой, а также типы данных литералов](constant-and-literal-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="acae7-114">For more information, see [Constant and Literal Data Types](constant-and-literal-data-types.md).</span></span>  
  
### <a name="to-declare-a-constant-that-has-an-explicitly-stated-data-type"></a><span data-ttu-id="acae7-115">Объявление константы с явно заданным типом данных</span><span class="sxs-lookup"><span data-stu-id="acae7-115">To declare a constant that has an explicitly stated data type</span></span>  
  
- <span data-ttu-id="acae7-116">Написать объявление, которое включает в себя `As` ключевое слово и явных типов данных, как показано в следующих примерах:</span><span class="sxs-lookup"><span data-stu-id="acae7-116">Write a declaration that includes the `As` keyword and an explicit data type, as in the following examples:</span></span>  
  
     [!code-vb[VbEnumsTask#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#9)]  
  
     <span data-ttu-id="acae7-117">Можно объявить несколько констант в одной строке, несмотря на то, что ваш код более удобочитаемым, если объявляется только одной константы в строке.</span><span class="sxs-lookup"><span data-stu-id="acae7-117">You can declare multiple constants on a single line, although your code is more readable if you declare only a single constant per line.</span></span> <span data-ttu-id="acae7-118">Если в одной строке объявляется несколько констант, все они должны иметь тот же уровень доступа (`Public`, `Private`, `Friend`, `Protected`, или `Protected Friend`).</span><span class="sxs-lookup"><span data-stu-id="acae7-118">If you declare multiple constants on a single line, they must all have the same access level (`Public`, `Private`, `Friend`, `Protected`, or `Protected Friend`).</span></span>  
  
### <a name="to-declare-multiple-constants-on-a-single-line"></a><span data-ttu-id="acae7-119">Объявление нескольких констант в одной строке</span><span class="sxs-lookup"><span data-stu-id="acae7-119">To declare multiple constants on a single line</span></span>  
  
- <span data-ttu-id="acae7-120">Разделите объявления запятой и пробелом, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="acae7-120">Separate the declarations with a comma and a space, as in the following example:</span></span>  
  
    ```  
    Public Const Four As Integer = 4, Five As Integer = 5, Six As Integer = 44  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="acae7-121">См. также</span><span class="sxs-lookup"><span data-stu-id="acae7-121">See also</span></span>

- [<span data-ttu-id="acae7-122">Оператор Const</span><span class="sxs-lookup"><span data-stu-id="acae7-122">Const Statement</span></span>](../../../../visual-basic/language-reference/statements/const-statement.md)
- [<span data-ttu-id="acae7-123">Типы данных констант и литералов</span><span class="sxs-lookup"><span data-stu-id="acae7-123">Constant and Literal Data Types</span></span>](constant-and-literal-data-types.md)
- [<span data-ttu-id="acae7-124">Общие сведения о константах</span><span class="sxs-lookup"><span data-stu-id="acae7-124">Constants Overview</span></span>](constants-overview.md)
- [<span data-ttu-id="acae7-125">Практическое руководство. Объявление константы</span><span class="sxs-lookup"><span data-stu-id="acae7-125">How to: Declare A Constant</span></span>](how-to-declare-a-constant.md)
- [<span data-ttu-id="acae7-126">Константы, определенные пользователем</span><span class="sxs-lookup"><span data-stu-id="acae7-126">User-Defined Constants</span></span>](user-defined-constants.md)
- [<span data-ttu-id="acae7-127">Типы данных констант и литералов</span><span class="sxs-lookup"><span data-stu-id="acae7-127">Constant and Literal Data Types</span></span>](constant-and-literal-data-types.md)
- [<span data-ttu-id="acae7-128">Практическое руководство. Группы значений связанных констант</span><span class="sxs-lookup"><span data-stu-id="acae7-128">How to: Group Related Constant Values Together</span></span>](how-to-group-related-constant-values-together.md)
- [<span data-ttu-id="acae7-129">Общие сведения о перечислениях</span><span class="sxs-lookup"><span data-stu-id="acae7-129">Enumerations Overview</span></span>](enumerations-overview.md)
- [<span data-ttu-id="acae7-130">Практическое руководство. Объявление перечислений</span><span class="sxs-lookup"><span data-stu-id="acae7-130">How to: Declare Enumerations</span></span>](how-to-declare-enumerations.md)
- [<span data-ttu-id="acae7-131">Практическое руководство. Ссылка на член перечисления</span><span class="sxs-lookup"><span data-stu-id="acae7-131">How to: Refer to an Enumeration Member</span></span>](how-to-refer-to-an-enumeration-member.md)
- [<span data-ttu-id="acae7-132">Перечисления и уточнение имен</span><span class="sxs-lookup"><span data-stu-id="acae7-132">Enumerations and Name Qualification</span></span>](enumerations-and-name-qualification.md)
- [<span data-ttu-id="acae7-133">Практическое руководство. Перебор элементов перечисления</span><span class="sxs-lookup"><span data-stu-id="acae7-133">How to: Iterate Through An Enumeration</span></span>](how-to-iterate-through-an-enumeration.md)
- [<span data-ttu-id="acae7-134">Практическое руководство. Определение строки, связанной со значением из перечисления</span><span class="sxs-lookup"><span data-stu-id="acae7-134">How to: Determine the String Associated with an Enumeration Value</span></span>](how-to-determine-the-string-associated-with-an-enumeration-value.md)
- [<span data-ttu-id="acae7-135">Когда следует использовать перечисление</span><span class="sxs-lookup"><span data-stu-id="acae7-135">When to Use an Enumeration</span></span>](when-to-use-an-enumeration.md)

- [<span data-ttu-id="acae7-136">Общие сведения о перечислениях</span><span class="sxs-lookup"><span data-stu-id="acae7-136">Enumerations Overview</span></span>](enumerations-overview.md)
- [<span data-ttu-id="acae7-137">Общие сведения о константах</span><span class="sxs-lookup"><span data-stu-id="acae7-137">Constants Overview</span></span>](constants-overview.md)
- [<span data-ttu-id="acae7-138">Практическое руководство. Объявления перечисления</span><span class="sxs-lookup"><span data-stu-id="acae7-138">How to: Declare an Enumeration</span></span>](how-to-declare-enumerations.md)
- [<span data-ttu-id="acae7-139">Перечисления и уточнение имен</span><span class="sxs-lookup"><span data-stu-id="acae7-139">Enumerations and Name Qualification</span></span>](enumerations-and-name-qualification.md)
- [<span data-ttu-id="acae7-140">Оператор Option Strict</span><span class="sxs-lookup"><span data-stu-id="acae7-140">Option Strict Statement</span></span>](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [<span data-ttu-id="acae7-141">Константы и перечисления</span><span class="sxs-lookup"><span data-stu-id="acae7-141">Constants and Enumerations</span></span>](../../../../visual-basic/language-reference/constants-and-enumerations.md)
