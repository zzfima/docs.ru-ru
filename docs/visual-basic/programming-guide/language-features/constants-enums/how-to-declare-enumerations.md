---
title: Инструкции. объявление перечислений
ms.date: 07/20/2015
helpviewer_keywords:
- declarations [Visual Basic], enumerations
- enumerations [Visual Basic], declaring
- declaring enumerations [Visual Basic]
ms.assetid: db4ca1c3-f429-4c81-ae81-29e0157b29fd
ms.openlocfilehash: 042aea045313bcaf3832274acf1000f87a084b72
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74354048"
---
# <a name="how-to-declare-enumerations-visual-basic"></a>Практическое руководство. Объявление перечисления (Visual Basic)
Перечисление создается с помощью оператора `Enum` в разделе Declarations класса или модуля. Нельзя объявить перечисление в методе. Чтобы указать соответствующий уровень доступа, используйте `Private`, `Protected`, `Friend`или `Public`.  
  
 Тип `Enum` имеет имя, базовый тип и набор полей, каждый из которых представляет константу. Имя должно быть допустимым квалификатором Visual Basic .NET. Базовый тип должен быть одним из целочисленных типов —`Byte`, `Short`, `Long` или `Integer`. значение по умолчанию — `Integer`. Перечисления всегда являются строго типизированными и не взаимозаменяемы с целочисленными типами чисел.  
  
 Перечисления не могут иметь значения с плавающей запятой. Если перечислению присваивается значение с плавающей запятой с `Option Strict On`, возникает ошибка компилятора. Если `Option Strict` `Off`, значение автоматически преобразуется в тип `Enum`.  
  
 Сведения об именах и об использовании оператора `Imports` для уточнения имени не требуется, см. в разделе [перечисления и квалификация имени](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md).  
  
### <a name="to-declare-an-enumeration"></a>Объявление перечисления  
  
1. Напишите объявление, которое включает уровень доступа к коду, ключевое слово `Enum` и допустимое имя, как в следующих примерах, каждый из которых объявляет разные `Enum`.  
  
     [!code-vb[VbEnumsTask#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#3)]  
  
2. Определите константы в перечислении. По умолчанию первая константа в перечислении инициализируется `0`, а последующие константы инициализируются значением, которое больше, чем предыдущая константа. Например, следующее перечисление `Days`содержит константу с именем `Sunday` со значением `0`, константу с именем `Monday` со значением `1`, константу с именем `Tuesday` и значением `2`и т. д.  
  
     [!code-vb[VbEnumsTask#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#4)]  
  
3. Можно явно назначать значения константам в перечислении с помощью оператора присваивания. Можно назначить любое целочисленное значение, включая отрицательные числа. Например, для представления ошибок могут потребоваться константы со значениями меньше нуля. В следующем перечислении константе `Invalid` явно присваивается значение `–1`, а константе `Sunday` присваивается значение `0`. Так как это первая константа в перечислении, `Saturday` также инициализируется значением `0`. Значение `Monday` `1` (по одному больше значения `Sunday`); значение `Tuesday` равно `2`и т. д.  
  
     [!code-vb[VbEnumsTask#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#5)]  
  
### <a name="to-declare-an-enumeration-as-an-explicit-type"></a>Объявление перечисления в явном типе  
  
- Укажите тип перечисления с помощью предложения `As`, как показано в следующем примере.  
  
     [!code-vb[VbEnumsTask#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#6)]  
  
## <a name="see-also"></a>См. также

- [Перечисления и уточнение имен](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)
- [Практическое руководство. Ссылка на элемент перечисления](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)
- [Пошаговое руководство. перебор перечислений в Visual Basic](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md)
- [Практическое руководство. Определение строки, связанной со значением из перечисления](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md)
- [Когда следует использовать перечисление](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)
- [Общие сведения о константах](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)
- [Типы данных констант и литералов](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md)
- [Константы и перечисления](../../../../visual-basic/language-reference/constants-and-enumerations.md)
