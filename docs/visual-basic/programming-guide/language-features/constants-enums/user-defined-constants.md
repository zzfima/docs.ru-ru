---
title: Константы, определенные пользователем (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- constants [Visual Basic], circular references
- Const statement [Visual Basic], user-defined constants
- user-defined constants [Visual Basic]
- scope [Visual Basic], constants
- constants [Visual Basic], user-defined
- circular references between constants [Visual Basic]
ms.assetid: a1206d5c-c45e-4ac2-970a-4a0be6a05fdd
ms.openlocfilehash: dc940105bbeb5e54819b8df5d5b3c831c7a6e145
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54527319"
---
# <a name="user-defined-constants-visual-basic"></a>Константы, определенные пользователем (Visual Basic)
Константа — это понятное имя, заменяющее числа или строки, которые не изменяются. Как можно понять из их названия, константы хранят значения, которые остаются постоянными в ходе выполнения приложения. Вы можете использовать константы, определенные элементы управления или компонентов, которыми вы работаете, или создать свой собственный. Константы, созданных вами самостоятельно называются *пользовательские*.  
  
 Объявление константы с `Const` инструкцию, используя те же правила, как для создания имени переменной. Если `Option Strict` является `On`, необходимо явно объявить тип константы.  
  
## <a name="const-statement-usage"></a>Использование оператора Const  
 Объект `Const` оператор может представляет числовые и временные показатели:  
  
 [!code-vb[VbEnumsTask#10](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/user-defined-constants_1.vb)]  
  
 Он также может определять `String` константы:  
  
 [!code-vb[VbEnumsTask#13](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/user-defined-constants_2.vb)]  
  
 Выражение справа от знака равенства ( `=` ) часто является числом, либо строковый литерал, но он также может быть выражением, результатом является числом или строкой (несмотря на то, что это выражение не может содержать вызовы функций). Вы даже можете определять константы с точки зрения ранее определенных констант:  
  
 [!code-vb[VbEnumsTask#15](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/user-defined-constants_3.vb)]  
  
## <a name="scope-of-user-defined-constants"></a>Область константы, определенные пользователем  
 Объект `Const` инструкции области совпадает со значением, переменной, объявленной в том же расположении. Области можно указать в любом из следующих способов:  
  
-   Чтобы создать константу, которая существует только в рамках процедуры, необходимо объявите ее в рамках этой процедуры.  
  
-   Чтобы создать константу, доступную для всех процедур в пределах класса, но не для кода за пределами модуля, объявите его в раздел объявлений класса.  
  
-   Чтобы создать константу, которая доступна всем членам сборки, но не внешним клиентам сборки, объявите его с помощью `Friend` ключевое слово в раздел объявлений класса.  
  
-   Чтобы создать константу, доступной для всего приложения, объявите его с помощью `Public` ключевое слово в объявлениях разделе класса.  
  
 Дополнительные сведения см. в разделе [Как Объявление константы](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-a-constant.md).  
  
### <a name="avoiding-circular-references"></a>Избежать циклических ссылок  
 Так как константы могут быть определены с точки зрения другие константы, существует возможность случайного создания *цикл*, или циклической ссылки между двумя или более констант. Цикл происходит, когда у вас есть два или более открытые константы, каждый из которых определяется в терминах другой, как показано в следующем примере:  
  
 [!code-vb[VbEnumsTask#16](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/user-defined-constants_4.vb)]  
[!code-vb[VbEnumsTask#17](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/user-defined-constants_5.vb)]  
  
 При возникновении цикла, Visual Basic создает ошибку компилятора.  
  
## <a name="see-also"></a>См. также
- [Оператор Const](../../../../visual-basic/language-reference/statements/const-statement.md)
- [Типы данных констант и литералов](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md)
- [Константы и перечисления](../../../../visual-basic/programming-guide/language-features/constants-enums/index.md)
- [Константы и перечисления](../../../../visual-basic/language-reference/constants-and-enumerations.md)
- [Общие сведения о перечислениях](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md)
- [Общие сведения о константах](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)
- [Практическое руководство. Объявления перечисления](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)
- [Перечисления и уточнение имен](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)
- [Оператор Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
