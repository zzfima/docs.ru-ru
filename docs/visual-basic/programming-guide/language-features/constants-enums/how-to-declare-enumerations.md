---
title: Практическое руководство. Объявление перечисления (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- declarations [Visual Basic], enumerations
- enumerations [Visual Basic], declaring
- declaring enumerations [Visual Basic]
ms.assetid: db4ca1c3-f429-4c81-ae81-29e0157b29fd
ms.openlocfilehash: f168d6d9cd6970353e75fa35a7e52cc7156fda72
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59343346"
---
# <a name="how-to-declare-enumerations-visual-basic"></a>Практическое руководство. Объявление перечисления (Visual Basic)
Создать перечисление с `Enum` инструкцию в раздел объявлений класса или модуля. Не удается объявить перечисление в методе. Чтобы указать соответствующий уровень доступа, используйте `Private`, `Protected`, `Friend`, или `Public`.  
  
 `Enum` Тип имеет имя, базовый тип и набор полей, каждый из которых представляет константу. Имя должно быть допустимым квалификатором Visual Basic .NET. Базовый тип должен быть одним из целочисленных типов —`Byte`, `Short`, `Long` или `Integer`. Значение по умолчанию — `Integer`. Перечисления всегда строго типизированы и не являются взаимозаменяемыми с целочисленными типами.  
  
 Перечисления не могут иметь значения с плавающей запятой. Если перечислению присваивается значение с плавающей запятой с `Option Strict On`, приведет к ошибке компилятора. Если `Option Strict` — `Off`, значение автоматически преобразуется в `Enum` типа.  
  
 Сведения об именах и как использовать `Imports` инструкцию, чтобы сделать уточнение имен нет необходимости, см. в разделе [перечисления и уточнение имен](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md).  
  
### <a name="to-declare-an-enumeration"></a>Для объявления перечисления  
  
1. Написать объявление, которое включает в себя уровень доступа к коду, `Enum` ключевое слово и допустимое имя, как показано в следующих примерах, каждый из которых объявляет различные `Enum`.  
  
     [!code-vb[VbEnumsTask#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#3)]  
  
2. Определения констант в перечислении. По умолчанию первая константа перечисления инициализируется `0`, и последующие константы инициализируются значение на единицу превышающего значение предыдущей константы. Например, следующее перечисление `Days`, содержит константу с именем `Sunday` со значением `0`, константу с именем `Monday` со значением `1`, константу с именем `Tuesday` со значением `2`, и т. д.  
  
     [!code-vb[VbEnumsTask#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#4)]  
  
3. Можно явно назначить значения константы перечисления, с помощью оператора присваивания. Можно назначить любое целочисленное значение, включая отрицательные числа. Например можно привести константы с отрицательными значениями для представления ошибок. В следующем примере, константа `Invalid` явным образом присваивается значение `–1`, а константа `Sunday` присваивается значение `0`. Так как это первая константа перечисления, `Saturday` также присваивается значение `0`. Значение `Monday` — `1` (на единицу превышающего значение `Sunday`); значение `Tuesday` является `2`, и т. д.  
  
     [!code-vb[VbEnumsTask#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#5)]  
  
### <a name="to-declare-an-enumeration-as-an-explicit-type"></a>Для объявления перечисления как явный тип  
  
-   Укажите тип перечисления с помощью `As` предложения, как показано в следующем примере.  
  
     [!code-vb[VbEnumsTask#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#6)]  
  
## <a name="see-also"></a>См. также

- [Перечисления и уточнение имен](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)
- [Практическое руководство. Ссылка на член перечисления](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)
- [Практическое руководство. Перебор элементов перечисления в Visual Basic](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md)
- [Практическое руководство. Определение строки, связанной со значением из перечисления](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md)
- [Когда следует использовать перечисление](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)
- [Общие сведения о константах](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)
- [Типы данных констант и литералов](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md)
- [Константы и перечисления](../../../../visual-basic/language-reference/constants-and-enumerations.md)
