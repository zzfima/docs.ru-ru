---
title: "Практическое руководство. Объявление константы (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.constant
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
caps.latest.revision: "20"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 554f659e060087228fb43efd8b9d06103e21e980
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-declare-a-constant-visual-basic"></a>Практическое руководство. Объявление константы (Visual Basic)
Вы используете `Const` инструкцию, чтобы объявление константы и присвойте ему значение. В объявлении константы, понятное имя назначить значение. После объявления константы ее нельзя изменить или присвоить новое значение.  
  
 Объявляется константа внутри процедуры или в разделе объявлений модуля, класса или структуры. Класс или структура уровня константы являются `Private` по умолчанию, но также может быть объявлен как `Public`, `Friend`, `Protected`, или `Protected Friend` для соответствующего уровня доступа к коду.  
  
 Константа должна иметь допустимое символическое имя (правил совпадают имени для переменной) и выражение, состоящее из числовое или строковое констант и операторов (но не вызовов функций).  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-declare-a-constant"></a>Объявление константы  
  
-   Написать объявление, которое включает спецификатор доступа `Const` ключевое слово и выражения, как показано в следующих примерах:  
  
     [!code-vb[VbEnumsTask#8](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-a-constant_1.vb)]  
  
     Когда [Option Infer](../../../../visual-basic/language-reference/statements/option-infer-statement.md) — `Off` и [Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md) — `On`, необходимо объявить константу явно, указав тип данных (`Boolean`, `Byte`, `Char`, `DateTime`, `Decimal`, `Double`, `Integer`, `Long`, `Short`, `Single`, или `String`).  
  
     Когда `Option Infer` — `On` или `Option Strict` — `Off`, можно объявить константу без указания типа данных с `As` предложения. Компилятор определяет тип константы из типа выражения. Дополнительные сведения см. в разделе [константой, а также типы данных литералов](constant-and-literal-data-types.md).  
  
### <a name="to-declare-a-constant-that-has-an-explicitly-stated-data-type"></a>Объявление константы с явно заданным типом данных  
  
-   Написать объявление, которое включает в себя `As` ключевое слово и явного типа данных, как показано в следующих примерах:  
  
     [!code-vb[VbEnumsTask#9](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-a-constant_2.vb)]  
  
     Можно объявить несколько констант в одной строке, несмотря на то, что код является более удобочитаемым, если объявить одной константы в строке. Если в одной строке объявляется несколько констант, все они должны иметь тот же уровень доступа (`Public`, `Private`, `Friend`, `Protected`, или `Protected Friend`).  
  
### <a name="to-declare-multiple-constants-on-a-single-line"></a>Чтобы объявить несколько констант в одной строке  
  
-   Разделите объявления запятой и пробелом, как показано в следующем примере:  
  
    ```  
    Public Const Four As Integer = 4, Five As Integer = 5, Six As Integer = 44  
    ```  
  
## <a name="see-also"></a>См. также  
 [Оператор Const](../../../../visual-basic/language-reference/statements/const-statement.md)  
 [Типы данных констант и литералов](constant-and-literal-data-types.md)  
 [Общие сведения о константах](constants-overview.md) [как: объявление константы](how-to-declare-a-constant.md) [константы, определенные пользователем](user-defined-constants.md) [типы данных констант и литералов](constant-and-literal-data-types.md) [как: группы Значений связанных констант](how-to-group-related-constant-values-together.md) [Общие сведения о перечислениях](enumerations-overview.md) [как: объявление перечисления](how-to-declare-enumerations.md) [как: ссылка на член перечисления](how-to-refer-to-an-enumeration-member.md) [Перечисления и уточнение имен](enumerations-and-name-qualification.md) [как: перебор элементов перечисления](how-to-iterate-through-an-enumeration.md) [как: определение строки, связанной со значением перечисления](how-to-determine-the-string-associated-with-an-enumeration-value.md) [Когда следует использовать перечисление](when-to-use-an-enumeration.md)

 [Общие сведения о перечислениях](enumerations-overview.md)  
 [Общие сведения о константах](constants-overview.md)  
 [Как: объявление перечисления](how-to-declare-enumerations.md)  
 [Перечисления и уточнение имен](enumerations-and-name-qualification.md)  
 [Оператор Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md)  
 [Константы и перечисления](../../../../visual-basic/language-reference/constants-and-enumerations.md)
