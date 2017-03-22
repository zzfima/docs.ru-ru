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
author: stevehoag
ms.author: shoag
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
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 401d0feb85fccf94a25308d38c3c75198ef9294c
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-declare-a-constant-visual-basic"></a>Практическое руководство. Объявление константы (Visual Basic)
Использовать `Const` инструкцию, чтобы объявить константу и задать его значение. Определяя константу, присваивайте ей понятное имя, значение. После объявления константы ее нельзя изменить или присвоить новое значение.  
  
 Объявление константы в процедуре либо в разделе объявлений модуля, класса или структуры. Класс или структура уровня константы являются `Private` по умолчанию, но также может быть объявлен как `Public`, `Friend`, `Protected`, или `Protected Friend` для соответствующего уровня доступа к коду.  
  
 Константа должна иметь допустимое символьное имя (правила совпадают имени для переменной) и выражение, состоящее из числовое или строковое констант и операторов (но не вызовов функций).  
  
[!INCLUDE[note_settings_general](../../../../csharp/language-reference/compiler-messages/includes/note_settings_general_md.md)]  
  
### <a name="to-declare-a-constant"></a>Объявление константы  
  
-   Написать объявление, которое включает спецификатор доступа `Const` ключевое слово и выражение, как показано в следующих примерах:  
  
     [!code-vb[VbEnumsTask №&8;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-a-constant_1.vb)]  
  
     Когда [Option Infer](../../../../visual-basic/language-reference/statements/option-infer-statement.md) — `Off` и [Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md) — `On`, вы явным образом объявить константу, указав тип данных (`Boolean`, `Byte`, `Char`, `DateTime`, `Decimal`, `Double`, `Integer`, `Long`, `Short`, `Single`, или `String`).  
  
     Когда `Option Infer` — `On` или `Option Strict` — `Off`, можно объявить константу без указания типа данных с `As` предложения. Компилятор определяет тип константы из типа выражения. Дополнительные сведения см. в разделе [константы и типы данных литералов](constant-and-literal-data-types.md).  
  
### <a name="to-declare-a-constant-that-has-an-explicitly-stated-data-type"></a>Объявление константы с явно заданным типом данных  
  
-   Написать объявление, которое включает в себя `As` ключевое слово и явного типа данных, как показано в следующих примерах:  
  
     [!code-vb[VbEnumsTask №&9;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-a-constant_2.vb)]  
  
     В одной строке можно объявить несколько констант, хотя код более удобочитаемым, если объявлена только одна константа в строке. Если в одной строке объявляется несколько констант, все они должны иметь тот же уровень доступа (`Public`, `Private`, `Friend`, `Protected`, или `Protected Friend`).  
  
### <a name="to-declare-multiple-constants-on-a-single-line"></a>Объявление нескольких констант в одной строке  
  
-   Разделите объявления запятой и пробелом, как показано в следующем примере:  
  
    ```  
    Public Const Four As Integer = 4, Five As Integer = 5, Six As Integer = 44  
    ```  
  
## <a name="see-also"></a>См. также  
 [Оператор Const](../../../../visual-basic/language-reference/statements/const-statement.md)   
 [Типы данных констант и литералов](constant-and-literal-data-types.md)   
 [Общие сведения о константах](constants-overview.md)
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
 [когда следует использовать перечисление](when-to-use-an-enumeration.md)

 [Общие сведения о перечислениях](enumerations-overview.md)   
 [Общие сведения о константах](constants-overview.md)   
 [Практическое руководство: объявление перечисления](how-to-declare-enumerations.md)   
 [Перечисления и уточнение имен](enumerations-and-name-qualification.md)   
 [Оператор Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md)   
 [Константы и перечисления](../../../../visual-basic/language-reference/constants-and-enumerations.md)

