---
title: Константы, определенные пользователем
ms.date: 07/20/2015
helpviewer_keywords:
- constants [Visual Basic], circular references
- Const statement [Visual Basic], user-defined constants
- user-defined constants [Visual Basic]
- scope [Visual Basic], constants
- constants [Visual Basic], user-defined
- circular references between constants [Visual Basic]
ms.assetid: a1206d5c-c45e-4ac2-970a-4a0be6a05fdd
ms.openlocfilehash: 194a420b3749ca5c858a65c07b8c164287c1582a
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74354004"
---
# <a name="user-defined-constants-visual-basic"></a>Константы, определенные пользователем (Visual Basic)
Константа — это понятное имя, которое принимает позицию числа или строки, которые не меняются. Как можно понять из их названия, константы хранят значения, которые остаются постоянными в ходе выполнения приложения. Вы можете использовать константы, определенные элементами управления или компонентами, с которыми вы работаете, или создать собственный. Константы, созданные самостоятельно, описаны как *определяемые пользователем*.  
  
 Вы объявляете константу с помощью инструкции `Const`, используя те же рекомендации, что и при создании имени переменной. Если `Option Strict` `On`, необходимо явно объявить константный тип.  
  
## <a name="const-statement-usage"></a>Использование инструкции const  
 Оператор `Const` может представлять математическое или значение даты и времени:  
  
 [!code-vb[VbEnumsTask#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#10)]  
  
 Он также может определять `String` константы:  
  
 [!code-vb[VbEnumsTask#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#13)]  
  
 Выражение в правой части знака равенства (`=`) часто является строкой или строковым литералом, но оно также может быть выражением, результатом которого является число или строка (хотя это выражение не может содержать вызовы функций). Константы можно даже определять с точки зрения ранее определенных констант:  
  
 [!code-vb[VbEnumsTask#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#15)]  
  
## <a name="scope-of-user-defined-constants"></a>Область определяемых пользователем констант  
 Область действия инструкции `Const` та же, что и у переменной, объявленной в том же расположении. Указать область можно одним из следующих способов.  
  
- Чтобы создать константу, которая существует только в пределах процедуры, объявите ее внутри этой процедуры.  
  
- Чтобы создать константу, доступную для всех процедур в классе, но не для кода за пределами этого модуля, объявите ее в разделе Declarations класса.  
  
- Чтобы создать константу, доступную для всех членов сборки, но не для клиентов сборки, объявите ее с помощью ключевого слова `Friend` в разделе Declarations класса.  
  
- Чтобы создать константу, доступную во всем приложении, объявите ее с помощью ключевого слова `Public` в разделе объявлений класс.  
  
 Дополнительные сведения см. [в разделе инструкции. Объявление константы](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-a-constant.md).  
  
### <a name="avoiding-circular-references"></a>Предотвращение циклических ссылок  
 Поскольку константы могут быть определены с точки зрения других констант, можно случайно создать *цикл*или циклическую ссылку между двумя или более константами. Цикл происходит при наличии двух или более открытых констант, каждая из которых определена в терминах другого, как показано в следующем примере:  
  
 [!code-vb[VbEnumsTask#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#16)]  
[!code-vb[VbEnumsTask#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#17)]  
  
 При возникновении цикла Visual Basic выдает ошибку компилятора.  
  
## <a name="see-also"></a>См. также

- [Оператор Const](../../../../visual-basic/language-reference/statements/const-statement.md)
- [Типы данных констант и литералов](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md)
- [Константы и перечисления](../../../../visual-basic/programming-guide/language-features/constants-enums/index.md)
- [Константы и перечисления](../../../../visual-basic/language-reference/constants-and-enumerations.md)
- [Общие сведения о перечислениях](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md)
- [Общие сведения о константах](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)
- [Инструкции. Объявление перечисления](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)
- [Перечисления и уточнение имен](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)
- [Оператор Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
