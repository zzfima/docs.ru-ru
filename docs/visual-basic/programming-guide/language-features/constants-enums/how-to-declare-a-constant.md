---
title: Практическое руководство. Объявление константы
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
ms.openlocfilehash: 5054d4a4fc02d8bd22efceb01770fc54167d8cb3
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347472"
---
# <a name="how-to-declare-a-constant-visual-basic"></a>Практическое руководство. Объявление константы (Visual Basic)
You use the `Const` statement to declare a constant and set its value. By declaring a constant, you assign a meaningful name to a value. Once a constant is declared, it cannot be modified or assigned a new value.  
  
 You declare a constant within a procedure or in the declarations section of a module, class, or structure. Class or structure-level constants are `Private` by default, but may also be declared as `Public`, `Friend`, `Protected`, or `Protected Friend` for the appropriate level of code access.  
  
 The constant must have a valid symbolic name (the rules are the same as those for creating variable names) and an expression composed of numeric or string constants and operators (but no function calls).  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-declare-a-constant"></a>To declare a constant  
  
- Write a declaration that includes an access specifier, the `Const` keyword, and an expression, as in the following examples:  
  
     [!code-vb[VbEnumsTask#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#8)]  
  
     When [Option Infer](../../../../visual-basic/language-reference/statements/option-infer-statement.md) is `Off` and [Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md) is `On`, you must declare a constant explicitly by specifying a data type (`Boolean`, `Byte`, `Char`, `DateTime`, `Decimal`, `Double`, `Integer`, `Long`, `Short`, `Single`, or `String`).  
  
     When `Option Infer` is `On` or `Option Strict` is `Off`, you can declare a constant without specifying a data type with an `As` clause. The compiler determines the type of the constant from the type of the expression. For more information, see [Constant and Literal Data Types](constant-and-literal-data-types.md).  
  
### <a name="to-declare-a-constant-that-has-an-explicitly-stated-data-type"></a>To declare a constant that has an explicitly stated data type  
  
- Write a declaration that includes the `As` keyword and an explicit data type, as in the following examples:  
  
     [!code-vb[VbEnumsTask#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#9)]  
  
     You can declare multiple constants on a single line, although your code is more readable if you declare only a single constant per line. If you declare multiple constants on a single line, they must all have the same access level (`Public`, `Private`, `Friend`, `Protected`, or `Protected Friend`).  
  
### <a name="to-declare-multiple-constants-on-a-single-line"></a>To declare multiple constants on a single line  
  
- Separate the declarations with a comma and a space, as in the following example:  
  
    ```vb  
    Public Const Four As Integer = 4, Five As Integer = 5, Six As Integer = 44  
    ```  
  
## <a name="see-also"></a>См. также

- [Оператор Const](../../../../visual-basic/language-reference/statements/const-statement.md)
- [Типы данных констант и литералов](constant-and-literal-data-types.md)
- [Общие сведения о константах](constants-overview.md)
- [Практическое руководство. Объявление константы](how-to-declare-a-constant.md)
- [Константы, определенные пользователем](user-defined-constants.md)
- [Типы данных констант и литералов](constant-and-literal-data-types.md)
- [Практическое руководство. Группирование значений связанных констант](how-to-group-related-constant-values-together.md)
- [Общие сведения о перечислениях](enumerations-overview.md)
- [Практическое руководство. Объявление перечислений](how-to-declare-enumerations.md)
- [Практическое руководство. Ссылка на элемент перечисления](how-to-refer-to-an-enumeration-member.md)
- [Перечисления и уточнение имен](enumerations-and-name-qualification.md)
- [Практическое руководство. Перебор элементов перечисления](how-to-iterate-through-an-enumeration.md)
- [Практическое руководство. Определение строки, связанной со значением из перечисления](how-to-determine-the-string-associated-with-an-enumeration-value.md)
- [Когда следует использовать перечисление](when-to-use-an-enumeration.md)

- [Общие сведения о перечислениях](enumerations-overview.md)
- [Общие сведения о константах](constants-overview.md)
- [How to: Declare an Enumeration](how-to-declare-enumerations.md)
- [Перечисления и уточнение имен](enumerations-and-name-qualification.md)
- [Оператор Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [Константы и перечисления](../../../../visual-basic/language-reference/constants-and-enumerations.md)
