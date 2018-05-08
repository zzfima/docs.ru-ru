---
title: Static (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Static
helpviewer_keywords:
- static modifier
- Static keyword [Visual Basic]
ms.assetid: 19013910-4658-47b6-a22e-1744b527979e
ms.openlocfilehash: 2cbd99a026a5ebf0e215ee5732d62ccf639d3836
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="static-visual-basic"></a>Static (Visual Basic)
Указывает один или несколько объявленных локальных переменных должны по-прежнему существует и сохранять свои последние значения после завершения процедуры, в котором они объявлены.  
  
## <a name="remarks"></a>Примечания  
 Как правило локальная переменная в процедуре перестает существовать как только выполнение процедуры прерывается. Статическая переменная продолжает существовать и сохраняет самое последнее значение. В следующий раз, код вызывает процедуру, переменная не инициализируется повторно, и она содержит последнее значение, присвоенное его. Статическая переменная продолжает существовать в течение времени существования класс или модуль, который определен в.  
  
## <a name="rules"></a>Правила  
  
-   **Контекст объявления.** Можно использовать `Static` только для локальных переменных. Это означает, что контекст объявления для `Static` переменной должен быть процедурой или блок в процедуре, и не может быть исходным файлом, пространства имен, класса, структуры или модуля.  
  
     Нельзя использовать `Static` внутри структуры процедуры.  
  
-   Типы данных `Static` локальные переменные не могут быть получены. Дополнительные сведения см. в разделе [вывод локального типа](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).  
  
-   **Комбинированные модификаторы.** Нельзя указать `Static` вместе с `ReadOnly`, `Shadows`, или `Shared` в одном объявлении.  
  
## <a name="behavior"></a>Поведение  
 При объявлении статической переменной в `Shared` процедура, только одна копия статическая переменная доступна для всего приложения. Вызывается `Shared` имя процедуры с помощью класса, не переменной, которая указывает на экземпляр класса.  
  
 При объявлении статической переменной в процедуре, которая не `Shared`, только одна копия переменной доступен для каждого экземпляра класса. Вызов процедуры без общего доступа с помощью переменной, указывающий на экземпляр класса.  
  
## <a name="example"></a>Пример  
 В следующем примере показано использование функции `Static`.  
  
 [!code-vb[VbVbalrKeywords#5](../../../visual-basic/language-reference/codesnippet/VisualBasic/static_1.vb)]  
  
 `Static` Переменной `totalSales` присваивается значение 0, только один раз. Каждый раз при вводе `updateSales`, `totalSales` по-прежнему содержит самое последнее значение, вычисленное для нее.  
  
 `Static` Модификатор может использоваться в этом контексте:  
  
 [Оператор Dim](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
## <a name="see-also"></a>См. также  
 [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md)  
 [Общие](../../../visual-basic/language-reference/modifiers/shared.md)  
 [Время существования в Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)  
 [Объявление переменных](../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)  
 [Структуры](../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [Вывод локального типа](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)  
 [Объекты и классы](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
