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
ms.openlocfilehash: b4a7e2b63b930b98ee082c0104c24f6857b5b35b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="user-defined-constants-visual-basic"></a>Константы, определенные пользователем (Visual Basic)
Константа представляет собой значимое имя, занимает место в число или строку, которая не изменяет. Как можно понять из их названия, константы хранят значения, которые остаются постоянными в ходе выполнения приложения. Можно использовать константы, определенные элементы управления или компонентов, которыми вы работаете, или можно создать свой собственный. Созданные пользователем константы называются *пользовательские*.  
  
 Объявление константы с `Const` инструкция, использующая те же правила, что для создания имени переменной. Если `Option Strict` — `On`, необходимо явно объявить тип константы.  
  
## <a name="const-statement-usage"></a>Использование оператора Const  
 Объект `Const` оператор может представляет числовые и временные показатели:  
  
 [!code-vb[VbEnumsTask#10](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/user-defined-constants_1.vb)]  
  
 Также можно определить `String` константы:  
  
 [!code-vb[VbEnumsTask#13](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/user-defined-constants_2.vb)]  
  
 Выражение справа от знака равенства ( `=` ) часто является номером или строковый литерал, но она может быть выражением, результатом вычисления числа или строки (хотя это выражение не может содержать вызовы функций). Можно даже определить константы с точки зрения ранее заданные константы:  
  
 [!code-vb[VbEnumsTask#15](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/user-defined-constants_3.vb)]  
  
## <a name="scope-of-user-defined-constants"></a>Область действия константы, определенные пользователем  
 Объект `Const` область оператора такая же, что и переменная, объявленная в том же расположении. Можно указать область, в каком-либо из следующих способов:  
  
-   Чтобы создать константу, которая существует только в пределах процедуры, объявите ее в рамках этой процедуры.  
  
-   Чтобы создать константу, доступную всем процедурам класса, но не для кода за пределами модуля, объявите его в раздел объявлений класса.  
  
-   Чтобы создать константу, которая доступна всем членам сборки, но не внешним клиентам сборки, объявите ее с помощью `Friend` ключевое слово в раздел объявлений класса.  
  
-   Чтобы создать константу, доступную в приложении, объявите его с помощью `Public` ключевое слово в объявлениях статьи класса.  
  
 Дополнительные сведения см. в разделе [как: объявлять константы](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-a-constant.md).  
  
### <a name="avoiding-circular-references"></a>Как избежать циклических ссылок  
 Поскольку константы могут определяться другими константами, существует возможность случайного создания *цикл*, или циклической ссылки между двумя или несколькими константами. Цикл происходит, если у вас есть два или более открытые константы, каждый из которых определяется на основе другой, как показано в следующем примере:  
  
 [!code-vb[VbEnumsTask#16](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/user-defined-constants_4.vb)]  
[!code-vb[VbEnumsTask#17](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/user-defined-constants_5.vb)]  
  
 При возникновении цикла, Visual Basic создает ошибку компилятора.  
  
## <a name="see-also"></a>См. также  
 [Оператор Const](../../../../visual-basic/language-reference/statements/const-statement.md)  
 [Типы данных констант и литералов](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md)  
 [Константы и перечисления](../../../../visual-basic/programming-guide/language-features/constants-enums/index.md)  
 [Константы и перечисления](../../../../visual-basic/language-reference/constants-and-enumerations.md)  
 [Общие сведения о перечислениях](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md)  
 [Общие сведения о константах](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)  
 [Как: объявление перечисления](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)  
 [Перечисления и уточнение имен](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)  
 [Оператор Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
