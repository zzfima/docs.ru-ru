---
title: Характеристики объявленных элементов
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
ms.openlocfilehash: 4e03cd28fed5e0ae109337739251c11a0ff3424a
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74331628"
---
# <a name="declared-element-characteristics-visual-basic"></a>Характеристики объявленных элементов (Visual Basic)
*Характеристика* объявленного элемента — это аспект этого элемента, который влияет на способ взаимодействия кода с ним. С каждым объявленным элементом связано одно или несколько из следующих характеристик:  
  
- *Тип данных* — значения, которые может содержать элемент, и способ хранения этих значений. Дополнительные сведения см. в разделе [Типы данных](../../../../visual-basic/language-reference/data-types/index.md).  
  
- Время *существования* — период времени выполнения, в течение которого элемент доступен для использования. Дополнительные сведения см. [в разделе время существования в Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md).  
  
- *Scope* — набор всего кода, который может ссылаться на элемент, без уточнения его имени. Дополнительные сведения см. в разделе [руководство. Управление областью действия переменной](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-control-the-scope-of-a-variable.md).  
  
- *Уровень доступа* — разрешение для кода, которое использует элемент. Дополнительные сведения см. в разделе [руководство. Управление доступностью переменной](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-control-the-availability-of-a-variable.md).  
  
## <a name="characteristics-of-the-elements"></a>Характеристики элементов  
 В следующей таблице показаны объявленные элементы и характеристики, которые применяются к каждому из них.  
  
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
|Возврат функции|Да|Да|Да|Нет|  
|оператора|Да|Нет|Да|Да|  
|Интерфейс|Нет|Нет|Да|Да|  
|Class|Нет|Нет|Да|Да|  
|событие|Нет|Нет|Да|Да|  
|Делегат|Нет|Нет|Да|Да|  
  
 <sup>1</sup> область иногда называется *видимостью*.  
  
## <a name="see-also"></a>См. также

- [Объявленные элементы](../../../../visual-basic/programming-guide/language-features/declared-elements/index.md)
- [Имена объявленных элементов](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)
- [Ссылки на объявленные элементы](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [Время существования в Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)
- [Область в Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)
- [Уровни доступа в Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [Типы данных](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
- [Объявление переменных](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
