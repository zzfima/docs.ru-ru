---
title: "Пользовательские константы (Visual Basic) | Документы Microsoft"
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
- constants, circular references
- Const statement [Visual Basic], user-defined constants
- user-defined constants
- scope, constants
- constants, user-defined
- circular references between constants
ms.assetid: a1206d5c-c45e-4ac2-970a-4a0be6a05fdd
caps.latest.revision: 19
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
ms.openlocfilehash: e5942d8663a8866b2f9794a86756f2bf25660ba5
ms.lasthandoff: 03/13/2017

---
# <a name="user-defined-constants-visual-basic"></a>Константы, определенные пользователем (Visual Basic)
Константа представляет собой значимое имя, вместо числа или строки, которые не изменяются. Константы хранят значения, которые, как и предполагает название, остаются неизменными во время выполнения приложения. Можно использовать константы, определенные элементами управления или компонентов, с которыми работают, или создавать собственные. Созданные пользователем константы называются *пользовательские*.  
  
 Объявление константы с `Const` инструкция, использующая те же правила, что для создания имени переменной. Если `Option Strict` — `On`, необходимо явно объявлять тип константы.  
  
## <a name="const-statement-usage"></a>Использование оператора Const  
 A `Const` оператор может представляет числовые и временные показатели:  
  
 [!code-vb[VbEnumsTask&#10;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/user-defined-constants_1.vb)]  
  
 Также можно определить `String` константы:  
  
 [!code-vb[VbEnumsTask&#13;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/user-defined-constants_2.vb)]  
  
 Выражение справа от знака равенства ( `=` ) часто является числом или буквенной строкой, но она может быть выражением, результатом вычисления в строку или число (хотя это выражение не может содержать вызовы функций). Вы даже можете определить константы в терминах ранее определенных констант:  
  
 [!code-vb[VbEnumsTask&#15;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/user-defined-constants_3.vb)]  
  
## <a name="scope-of-user-defined-constants"></a>Область действия константы, определенные пользователем  
 A `Const` областью инструкции является таким же, как и для переменной, объявленной в том же расположении. Можно указать область в любой из следующих способов:  
  
-   Чтобы создать константу, которая существует только в пределах процедуры, объявите ее в этой процедуре.  
  
-   Чтобы создать константу, доступную всем процедурам класса, но не для кода за пределами модуля, следует объявите ее в разделе объявлений класса.  
  
-   Чтобы создать константу, которая доступна всем членам сборки, но не внешним клиентам сборки, объявите его с помощью `Friend` ключевое слово в раздел объявлений класса.  
  
-   Чтобы создать константу, доступную в рамках всего приложения, следует объявить ее с помощью `Public` ключевых слов в объявлениях раздел класса.  
  
 Дополнительные сведения см. в разделе [как: объявления констант](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-a-constant.md).  
  
### <a name="avoiding-circular-references"></a>Чтобы избежать циклических ссылок  
 Поскольку константы могут определяться другими константами, существует возможность случайного создания *цикла*, или циклической ссылки между двумя или несколькими константами. Цикл возникает, когда два или несколько открытых констант, каждый из которых определяется в терминах других, как показано в следующем примере:  
  
 [!code-vb[VbEnumsTask №&16;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/user-defined-constants_4.vb)]  
[!code-vb[VbEnumsTask&17;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/user-defined-constants_5.vb)]  
  
 При возникновении цикла, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] приводит к ошибке компилятора.  
  
## <a name="see-also"></a>См. также  
 [Оператор Const](../../../../visual-basic/language-reference/statements/const-statement.md)   
 [Типы данных констант и литералов](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md)   
 [Константы и перечисления](../../../../visual-basic/programming-guide/language-features/constants-enums/index.md)   
 [Константы и перечисления](../../../../visual-basic/language-reference/constants-and-enumerations.md)   
 [Общие сведения о перечислениях](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md)   
 [Общие сведения о константах](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)   
 [Практическое руководство: объявление перечисления](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)   
 [Перечисления и уточнение имен](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)   
 [Оператор Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
