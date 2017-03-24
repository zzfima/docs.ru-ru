---
title: "Характеристики объявленных элементов (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "уровни доступа, объявленные элементы"
  - "типы данных [Visual Basic], объявленные элементы"
  - "объявленные элементы, уровень доступа"
  - "объявленные элементы, время существования"
  - "объявленные элементы, область действия"
  - "объявленные элементы, видимость"
  - "элементы, программирование"
  - "время существования, объявленные элементы"
  - "область действия, объявленные элементы"
  - "видимость, объявленные элементы"
ms.assetid: 1bc40fb8-b67c-4428-90a4-76b630ae2583
caps.latest.revision: 16
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 16
---
# Характеристики объявленных элементов (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

*Характеристикой* объявленного элемента называется свойство этого элемента, определяющее способы его взаимодействия с кодом.  У каждого объявленного элемента есть одна или несколько следующих связанных с ним характеристик:  
  
-   *Тип данных* — значения, которые может принимать элемент, и способ их хранения.  Дополнительные сведения см. в разделе [Типы данных](../../../../visual-basic/language-reference/data-types/data-type-summary.md).  
  
-   *Время существования* — период времени выполнения, в течение которого элемент доступен для использования.  Дополнительные сведения см. в разделе [Время существования в Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md).  
  
-   *Область действия* — область кода, из которой возможно обращение к элементу без указания его полного имени.  Дополнительные сведения см. в разделе [Практическое руководство. Управление областью действия переменной](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-control-the-scope-of-a-variable.md).  
  
-   *Уровень доступа* — разрешение коду на использование этого элемента.  Дополнительные сведения см. в разделе [Практическое руководство. Управление доступностью переменной](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-control-the-availability-of-a-variable.md).  
  
## Характеристики элементов  
 В следующей таблице приведены объявленные элементы и характеристики каждого из них.  
  
|Элемент|Тип данных|Время существования|Область <sup>1</sup>|Уровень доступа|  
|-------------|----------------|-------------------------|--------------------------|---------------------|  
|Переменная|Да|Да|Да|Да|  
|Константа|Да|Нет|Да|Да|  
|Перечисление|Да|Нет|Да|Да|  
|Структура|Нет|Нет|Да|Да|  
|Свойство.|Да|Да|Да|Да|  
|Метод|Нет|Да|Да|Да|  
|Процедура \(`Sub` или `Function`\)|Нет|Да|Да|Да|  
|Параметр процедуры|Да|Да|Да|Нет|  
|Значение, возвращаемое функцией|Да|Да|Да|Нет|  
|Оператор|Да|Нет|Да|Да|  
|Интерфейс|Нет|Нет|Да|Да|  
|Класс|Нет|Нет|Да|Да|  
|Событие|Нет|Нет|Да|Да|  
|Делегат|Нет|Нет|Да|Да|  
  
 Область <sup>1</sup> иногда называют *видимой*.  
  
## См. также  
 [Объявленные элементы](../../../../visual-basic/programming-guide/language-features/declared-elements/index.md)   
 [Имена объявленных элементов](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)   
 [Ссылки на объявленные элементы](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)   
 [Время существования в Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)   
 [Область видимости в Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)   
 [Уровни доступа в Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)   
 [Типы данных](../../../../visual-basic/programming-guide/language-features/data-types/index.md)   
 [Объявление переменной](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)