---
title: Характеристики объявленных элементов (Visual Basic)
ms.date: 07/20/2015
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
ms.openlocfilehash: 27dad8b2fbfbc8d17090df201bf36eb080966f51
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43536525"
---
# <a name="declared-element-characteristics-visual-basic"></a>Характеристики объявленных элементов (Visual Basic)
Объект *характеристика* объявленного элемента является аспектом элемента, определяющее, каким образом код может взаимодействовать с ним. Каждый объявленный элемент имеет один или несколько из следующих характеристик, связанный с ним:  
  
-   *Тип данных* — значения, которые может содержать элемент, и способ их хранения. Дополнительные сведения см. в разделе [Типы данных](../../../../visual-basic/language-reference/data-types/index.md).  
  
-   *Время существования* — период времени выполнения, в течение которого элемент доступен для использования. Дополнительные сведения см. в разделе [время существования в Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md).  
  
-   *Область* — набор весь код, который можно ссылаться на элемент без указания полного имени. Дополнительные сведения см. в разделе [как: управление областью действия переменной](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-control-the-scope-of-a-variable.md).  
  
-   *Уровень доступа* — разрешение коду на использование этого элемента. Дополнительные сведения см. в разделе [как: Управление доступностью переменной](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-control-the-availability-of-a-variable.md).  
  
## <a name="characteristics-of-the-elements"></a>Характеристики элементов  
 Следующая таблица показывает объявленные элементы и характеристики, которые применяются для каждого из них.  
  
|Элемент|Тип данных|Время существования|Область <sup>1</sup>|Уровень доступа|  
|-------------|---------------|--------------|------------------------|------------------|  
|Переменная|Да|Да|Да|Да|  
|Константа|Да|Нет|Да|Да|  
|Перечисление|Да|Нет|Да|Да|  
|Структура|Нет|Нет|Да|Да|  
|Свойство.|Да|Да|Да|Да|  
|Метод|Нет|Да|Да|Да|  
|Процедура (`Sub` или `Function`)|Нет|Да|Да|Да|  
|Параметр процедуры|Да|Да|Да|Нет|  
|Функции|Да|Да|Да|Нет|  
|Оператор|Да|Нет|Да|Да|  
|Интерфейс|Нет|Нет|Да|Да|  
|Класс|Нет|Нет|Да|Да|  
|событие|Нет|Нет|Да|Да|  
|делегат|Нет|Нет|Да|Да|  
  
 <sup>1</sup> области иногда называется *видимость*.  
  
## <a name="see-also"></a>См. также  
 [Объявленные элементы](../../../../visual-basic/programming-guide/language-features/declared-elements/index.md)  
 [Имена объявленных элементов](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)  
 [Ссылки на объявленные элементы](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)  
 [Время существования в Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)  
 [Область, в Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)  
 [Уровни доступа в Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)  
 [Типы данных](../../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 [Объявление переменных](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
