---
title: "Характеристики объявленных элементов (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- declared elements [Visual Basic], lifetime
- access levels, declared elements
- declared elements [Visual Basic], scope
- visibility [Visual Basic], declared elements
- elements [Visual Basic], programming
- scope [Visual Basic], declared elements
- lifetime [Visual Basic], declared elements
- declared elements [Visual Basic], access level
- data types [Visual Basic], declared elements
- declared elements [Visual Basic], visibility
ms.assetid: 1bc40fb8-b67c-4428-90a4-76b630ae2583
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 26ee27d3a1d085c6ab45ae850dbdac700aa208a9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="declared-element-characteristics-visual-basic"></a>Характеристики объявленных элементов (Visual Basic)
Объект *характеристика* объявленного элемента называется свойство этого элемента, определяющее, как код может взаимодействовать с ним. У каждого объявленного элемента имеется один или несколько из следующих характеристик, связанные с ним:  
  
-   *Тип данных* — значения, которые может принимать элемент, и способ их хранения. Дополнительные сведения см. в разделе [типы данных](../../../../visual-basic/language-reference/data-types/data-type-summary.md).  
  
-   *Время существования* — период времени выполнения, в течение которого элемент доступен для использования. Дополнительные сведения см. в разделе [время существования в Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md).  
  
-   *Область* — набор весь код, который может ссылаться на элемент неполного имени. Дополнительные сведения см. в разделе [как: управление областью действия переменной](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-control-the-scope-of-a-variable.md).  
  
-   *Уровень доступа* — разрешение коду на использование этого элемента. Дополнительные сведения см. в разделе [как: Управление доступностью переменной](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-control-the-availability-of-a-variable.md).  
  
## <a name="characteristics-of-the-elements"></a>Характеристики элементов  
 В следующей таблице показаны объявленные элементы и характеристики, которые применяются для каждого из них.  
  
|Элемент|Тип данных|Время существования|Область <sup>1</sup>|Уровень доступа|  
|-------------|---------------|--------------|------------------------|------------------|  
|Переменная|Да|Да|Да|Да|  
|Константа|Да|Нет|Да|Да|  
|Перечисление|Да|Нет|Да|Да|  
|Структура|Нет|Нет|Да|Да|  
|Свойство|Да|Да|Да|Да|  
|Метод|Нет|Да|Да|Да|  
|Процедура (`Sub` или `Function`)|Нет|Да|Да|Да|  
|Параметр процедуры|Да|Да|Да|Нет|  
|Функция возврата|Да|Да|Да|Нет|  
|Оператор|Да|Нет|Да|Да|  
|Интерфейс|Нет|Нет|Да|Да|  
|Класс|Нет|Нет|Да|Да|  
|Событие|Нет|Нет|Да|Да|  
|Делегат|Нет|Нет|Да|Да|  
  
 <sup>1</sup> область, иногда называют *видимость*.  
  
## <a name="see-also"></a>См. также  
 [Объявленные элементы](../../../../visual-basic/programming-guide/language-features/declared-elements/index.md)  
 [Имена объявленных элементов](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)  
 [Ссылки на объявленные элементы](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)  
 [Время существования в Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)  
 [Область в Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)  
 [Уровни доступа в Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)  
 [Типы данных](../../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 [Объявление переменных](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
