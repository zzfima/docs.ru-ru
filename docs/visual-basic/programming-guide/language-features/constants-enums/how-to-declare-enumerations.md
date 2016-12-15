---
title: "Практическое руководство. Объявление перечисления (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "объявления, перечисления"
  - "объявление перечислений"
  - "перечисления [Visual Basic], объявление"
ms.assetid: db4ca1c3-f429-4c81-ae81-29e0157b29fd
caps.latest.revision: 24
caps.handback.revision: 24
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Практическое руководство. Объявление перечисления (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Перечисления создаются в разделе объявлений класса или модуля с помощью оператора `Enum`.  Нельзя объявить перечисление в методе.  Чтобы указать соответствующий уровень доступа, используйте `Private`, `Protected` `Friend` или `Public`.  
  
 Тип `Enum` имеет имя, базовый тип и набор полей, каждое из которых представляет собой константу.  Имя должно быть допустимым квалификатором [!INCLUDE[vbprvblong](../../../../visual-basic/developing-apps/customizing-extending-my/includes/vbprvblong_md.md)].  Базовый тип должен быть одним из целочисленных типов — `Byte`, `Short` `Long` или `Integer`.  Тип `Integer` используется по умолчанию.  Перечисления всегда имеют строгие типы и не взаимозаменяемы с целочисленными типами.  
  
 Перечисления не могут иметь значений с плавающей точкой.  Если перечислению присваивается значение с плавающей точкой при `Option Strict On`, то это приводит к ошибке компиляции.  Если `Option Strict` `Off`, то значение автоматически преобразуется к типу `Enum`.  
  
 Сведения об именах и использовании оператора `Imports` для того, чтобы использовать имена без необходимой квалификации содержатся в разделе [Перечисления и уточнение имен](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md).  
  
### Объявление перечисления  
  
1.  Напишите объявление, включающее в себя уровень кода доступа, ключевое слово `Enum` и допустимое имя, как в следующих примерах, каждый из которых объявляет различные `Enum`.  
  
     [!code-vb[VbEnumsTask#3](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-enumerations_1.vb)]  
  
2.  Определите константы в перечислении.  По умолчанию первая константа перечисления инициализируется `0`, а каждая последующая константа инициализируется значением, на единицу большим, чем значение предыдущей константы.  Например, следующее перечисление `Days` содержит константу с именем `Sunday` со значением `0`, константу с именем `Monday` со значением `1`, константу с именем `Tuesday` со значением `2` и так далее:  
  
     [!code-vb[VbEnumsTask#4](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-enumerations_2.vb)]  
  
3.  Следует использовать оператор присваивания, чтобы явным образом присвоить значения константам перечисления.  Можно присваивать целочисленные значения, включая отрицательные.  Например, константы с отрицательными значениями могут означать ту или иную ошибку.  В следующем примере константе `Invalid` явным образом присваивается значение `–1`, а константе `Sunday` — значение `0`.  Поскольку константа `Saturday` идет в перечислении первой, она также инициализируется `0`.  Значением `Monday` является `1` \(на единицу больше, чем значение `Sunday`\); значением `Tuesday` является `2` и т. д.  
  
     [!code-vb[VbEnumsTask#5](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-enumerations_3.vb)]  
  
### Объявление перечисления в виде явного типа  
  
-   Определите тип перечисления с помощью выражения `As`, как показано в следующем примере.  
  
     [!code-vb[VbEnumsTask#6](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-enumerations_4.vb)]  
  
## См. также  
 [Перечисления и уточнение имен](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)   
 [Практическое руководство. Ссылка на член перечисления](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)   
 [Практическое руководство. Перебор элементов перечисления в Visual Basic](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md)   
 [Практическое руководство. Определение строки, связанной со значением из перечисления](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md)   
 [Когда следует использовать перечисление](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)   
 [Общие сведения о константах](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)   
 [Типы данных констант и литералов](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md)   
 [Константы и перечисления](../../../../visual-basic/language-reference/constants-and-enumerations.md)