---
title: Практическое руководство. Объявление перечисления (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- declarations [Visual Basic], enumerations
- enumerations [Visual Basic], declaring
- declaring enumerations [Visual Basic]
ms.assetid: db4ca1c3-f429-4c81-ae81-29e0157b29fd
ms.openlocfilehash: e2dbdbbf6bf7fe3e4b71cbe7edc7a19b18f96ef2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33650807"
---
# <a name="how-to-declare-enumerations-visual-basic"></a>Практическое руководство. Объявление перечисления (Visual Basic)
Создать перечисление с `Enum` инструкции в разделе объявлений класса или модуля. Нельзя объявить перечисление в методе. Чтобы указать соответствующий уровень доступа, используйте `Private`, `Protected`, `Friend`, или `Public`.  
  
 `Enum` Тип имеет имя, базовый тип и набор полей, каждое из которых представляет собой константу. Имя должно быть допустимым квалификатором Visual Basic .NET. Базовый тип должен быть одним из целочисленных типов —`Byte`, `Short`, `Long` или `Integer`. Значение по умолчанию — `Integer`. Перечисления всегда строго типизированы и не является взаимозаменяемым с целочисленными типами.  
  
 Перечисления не могут иметь значения с плавающей запятой. Если перечислению присваивается значение с плавающей запятой с `Option Strict On`, приведет к ошибке компилятора. Если `Option Strict` — `Off`, значение автоматически преобразуется в `Enum` типа.  
  
 Сведения об именах и как использовать `Imports` разделе инструкции, чтобы сделать уточнение имен при необходимости [перечисления и уточнение имен](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md).  
  
### <a name="to-declare-an-enumeration"></a>Для объявления перечисления  
  
1.  Написать объявление, которое включает уровень доступа к коду, `Enum` ключевое слово и допустимое имя, как показано в следующих примерах, каждый из которых объявляет различные `Enum`.  
  
     [!code-vb[VbEnumsTask#3](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-enumerations_1.vb)]  
  
2.  Определения констант в перечислении. По умолчанию первая константа перечисления инициализируется `0`, и каждая последующая константа инициализируется значение на единицу больше, чем значение предыдущей константы. Например, следующее перечисление `Days`, содержит константу с именем `Sunday` со значением `0`, константу с именем `Monday` со значением `1`, константу с именем `Tuesday` со значением `2`, и т. д.  
  
     [!code-vb[VbEnumsTask#4](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-enumerations_2.vb)]  
  
3.  Можно явно назначить значения константы перечисления с помощью оператора присваивания. Можно назначить любое целочисленное значение, включая отрицательные числа. Например может потребоваться константы с отрицательными значениями в ту или иную ошибку. В следующем примере константа `Invalid` явно назначено значение `–1`, а константа `Sunday` присваивается значение `0`. Поскольку это первая константа перечисления, `Saturday` также инициализируется значение `0`. Значение `Monday` — `1` (на единицу больше, чем значение `Sunday`); значение `Tuesday` — `2`, и т. д.  
  
     [!code-vb[VbEnumsTask#5](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-enumerations_3.vb)]  
  
### <a name="to-declare-an-enumeration-as-an-explicit-type"></a>Чтобы объявить перечисление как явный тип  
  
-   Укажите тип перечисления с помощью `As` предложения, как показано в следующем примере.  
  
     [!code-vb[VbEnumsTask#6](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-enumerations_4.vb)]  
  
## <a name="see-also"></a>См. также  
 [Перечисления и уточнение имен](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)  
 [Практическое руководство. Ссылка на элемент перечисления](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)  
 [Как: перебор элементов перечисления в Visual Basic](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md)  
 [Практическое руководство. Определение строки, связанной со значением из перечисления](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md)  
 [Когда следует использовать перечисление](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)  
 [Общие сведения о константах](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)  
 [Типы данных констант и литералов](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md)  
 [Константы и перечисления](../../../../visual-basic/language-reference/constants-and-enumerations.md)
