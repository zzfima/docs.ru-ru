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
# <a name="how-to-declare-a-constant-visual-basic"></a>Практическое руководство. Объявление константы (Visual Basic)
Использовании `Const` инструкцию, чтобы объявление константы и присвойте ему значение. Объявляя константу, понятное имя назначается значение. После объявления константа не может изменить или присвоить новое значение.  
  
 Вы объявите константу в процедуре или в раздел объявлений модуля, класса или структуры. Класс или структура на уровне константы являются `Private` по умолчанию, но также может быть объявлено как `Public`, `Friend`, `Protected`, или `Protected Friend` для соответствующего уровня доступа к коду.  
  
 Константа должна иметь допустимое символическое имя (правила являются те же имени для переменной) и выражение, состоящее из числовой или строковый констант и операторов (но не вызовы функций).  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-declare-a-constant"></a>Объявление константы  
  
-   Написать объявление, которое включает спецификатор доступа `Const` ключевое слово и выражение, как показано в следующих примерах:  
  
     [!code-vb[VbEnumsTask#8](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-a-constant_1.vb)]  
  
     Когда [Option Infer](../../../../visual-basic/language-reference/statements/option-infer-statement.md) — `Off` и [Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md) — `On`, константа необходимо объявить явно путем указания типа данных (`Boolean`, `Byte`, `Char`, `DateTime`, `Decimal`, `Double`, `Integer`, `Long`, `Short`, `Single`, или `String`).  
  
     При `Option Infer` — `On` или `Option Strict` — `Off`, можно объявить без указания типа данных с константой `As` предложение. Компилятор определяет тип константы из типа выражения. Дополнительные сведения см. в разделе [константой, а также типы данных литералов](constant-and-literal-data-types.md).  
  
### <a name="to-declare-a-constant-that-has-an-explicitly-stated-data-type"></a>Объявление константы с явно заданным типом данных  
  
-   Написать объявление, которое включает в себя `As` ключевое слово и явных типов данных, как показано в следующих примерах:  
  
     [!code-vb[VbEnumsTask#9](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-a-constant_2.vb)]  
  
     Можно объявить несколько констант в одной строке, несмотря на то, что ваш код более удобочитаемым, если объявляется только одной константы в строке. Если в одной строке объявляется несколько констант, все они должны иметь тот же уровень доступа (`Public`, `Private`, `Friend`, `Protected`, или `Protected Friend`).  
  
### <a name="to-declare-multiple-constants-on-a-single-line"></a>Объявление нескольких констант в одной строке  
  
-   Разделите объявления запятой и пробелом, как показано в следующем примере:  
  
    ```  
    Public Const Four As Integer = 4, Five As Integer = 5, Six As Integer = 44  
    ```  
  
## <a name="see-also"></a>См. также  
 [Оператор Const](../../../../visual-basic/language-reference/statements/const-statement.md)  
 [Типы данных констант и литералов](constant-and-literal-data-types.md)  
 [Общие сведения о константах](constants-overview.md) [как: объявление константы](how-to-declare-a-constant.md) [константы, определенные пользователем](user-defined-constants.md) [типы данных констант и литералов](constant-and-literal-data-types.md) [как: группы Значений связанных констант](how-to-group-related-constant-values-together.md) [Общие сведения о перечислениях](enumerations-overview.md) [как: объявление перечислений](how-to-declare-enumerations.md) [как: ссылка на член перечисления](how-to-refer-to-an-enumeration-member.md) [Перечисления и уточнение имен](enumerations-and-name-qualification.md) [как: перебор элементов перечисления](how-to-iterate-through-an-enumeration.md) [как: определение строки, связанной со значением из перечисления](how-to-determine-the-string-associated-with-an-enumeration-value.md) [Когда следует использовать перечисление](when-to-use-an-enumeration.md)

 [Общие сведения о перечислениях](enumerations-overview.md)  
 [Общие сведения о константах](constants-overview.md)  
 [Практическое: объявление перечисления](how-to-declare-enumerations.md)  
 [Перечисления и уточнение имен](enumerations-and-name-qualification.md)  
 [Оператор Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md)  
 [Константы и перечисления](../../../../visual-basic/language-reference/constants-and-enumerations.md)
