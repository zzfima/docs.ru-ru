---
title: "Практическое руководство: объявление перечисления (Visual Basic) | Документы Microsoft"
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
- declarations, enumerations
- enumerations [Visual Basic], declaring
- declaring enumerations
ms.assetid: db4ca1c3-f429-4c81-ae81-29e0157b29fd
caps.latest.revision: 24
author: dotnet-bot
ms.author: dotnetcontent
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
ms.openlocfilehash: 8ff8bf2df39bed0597740bcda968283ec854f447
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-declare-enumerations-visual-basic"></a>Практическое руководство. Объявление перечисления (Visual Basic)
Создание перечисления с `Enum` инструкции в разделе объявлений класса или модуля. Нельзя объявить перечисление в методе. Чтобы указать соответствующий уровень доступа, используйте `Private`, `Protected`, `Friend`, или `Public`.  
  
 `Enum` Тип имеет имя, базовый тип и набор полей, каждое из которых представляет собой константу. Имя должно быть допустимым [!INCLUDE[vbprvblong](../../../../visual-basic/developing-apps/customizing-extending-my/includes/vbprvblong_md.md)] квалификатор. Базовый тип должен быть одним из целочисленных типов —`Byte`, `Short`, `Long` или `Integer`. Значение по умолчанию — `Integer`. Перечисления всегда имеют строгие типы и не взаимозаменяемы с целочисленными типами.  
  
 Перечисления не могут иметь значений с плавающей запятой. Если перечислению присваивается значение с плавающей запятой с `Option Strict On`, приведет к ошибке компилятора. Если `Option Strict` — `Off`, значение автоматически преобразуется в `Enum` типа.  
  
 Сведения об именах и использование `Imports` разделе инструкции, чтобы сделать уточнение имен нет необходимости, [перечисления и уточнение имен](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md).  
  
### <a name="to-declare-an-enumeration"></a>Объявление перечисления  
  
1.  Написать объявление, которое включает уровень доступа к коду, `Enum` ключевое слово и допустимое имя, как показано в следующих примерах, каждый из которых объявляет различные `Enum`.  
  
     [!code-vb[VbEnumsTask&#3;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-enumerations_1.vb)]  
  
2.  Определите константы в перечислении. По умолчанию первая константа перечисления инициализируется `0`, и каждая последующая константа инициализируется значение на единицу больше, чем значение предыдущей константы. Например, следующее перечисление `Days`, содержит константу с именем `Sunday` со значением `0`, константу с именем `Monday` со значением `1`, константу с именем `Tuesday` со значением `2`, и т. д.  
  
     [!code-vb[VbEnumsTask&#4;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-enumerations_2.vb)]  
  
3.  Можно явным образом присвоить значения константам перечисления с помощью оператора присваивания. Можно назначить любое целочисленное значение, включая отрицательные числа. Например можно привести константы с отрицательными значениями в ту или иную ошибку. В следующем примере константа `Invalid` явным образом присваивается значение `–1`, а константа `Sunday` присваивается значение `0`. Поскольку это первая константа перечисления, `Saturday` также инициализируется значение `0`. Значение `Monday` — `1` (на единицу больше, чем значение `Sunday`); значение `Tuesday` — `2`, и т. д.  
  
     [!code-vb[VbEnumsTask&#5;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-enumerations_3.vb)]  
  
### <a name="to-declare-an-enumeration-as-an-explicit-type"></a>Для объявления перечисления в виде явного типа  
  
-   Укажите тип перечисления с помощью `As` , как показано в следующем примере.  
  
     [!code-vb[VbEnumsTask №&6;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-enumerations_4.vb)]  
  
## <a name="see-also"></a>См. также  
 [Перечисления и уточнение имен](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)   
 [Практическое руководство: ссылка на член перечисления](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)   
 [Практическое руководство: перебор элементов перечисления в Visual Basic](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md)   
 [Практическое руководство: определение строки, связанной со значением перечисления](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md)   
 [Когда следует использовать перечисление](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)   
 [Общие сведения о константах](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)   
 [Типы данных констант и литералов](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md)   
 [Константы и перечисления](../../../../visual-basic/language-reference/constants-and-enumerations.md)
