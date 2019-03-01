---
title: Static (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Static
helpviewer_keywords:
- static modifier
- Static keyword [Visual Basic]
ms.assetid: 19013910-4658-47b6-a22e-1744b527979e
ms.openlocfilehash: 9ee2c6eb123907a9e25092224a1f45578717a8c7
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2019
ms.locfileid: "56977153"
---
# <a name="static-visual-basic"></a>Static (Visual Basic)
Указывает, что один или несколько объявленных локальных переменных по-прежнему существует и сохранять свои последние значения после завершения процедуры, в котором они объявлены.  
  
## <a name="remarks"></a>Примечания  
 Как правило локальную переменную в процедуре перестает существовать как только выполнение процедуры прерывается. Статическая переменная продолжает существовать и сохраняет его самое последнее значение. В следующий раз, код вызывает процедуру, переменная не инициализируется, и она содержит последнее значение, которое было назначено его. Статическая переменная продолжает существовать в течение времени существования класс или модуль, который определен в.  
  
## <a name="rules"></a>Правила  
  
-   **Контекст объявления.** Можно использовать `Static` только на локальные переменные. Это означает, что контекст объявления для `Static` переменной должен быть процедурой или блок в процедуре, и не может быть исходным файлом, пространства имен, класса, структуры или модуля.  
  
     Нельзя использовать `Static` внутри структуры процедуры.  
  
-   Типы данных `Static` локальные переменные не могут быть получены. Дополнительные сведения см. в разделе [вывод локального типа](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).  
  
-   **Комбинированные модификаторы.** Нельзя указать `Static` вместе с `ReadOnly`, `Shadows`, или `Shared` в одном объявлении.  
  
## <a name="behavior"></a>Поведение  
 При объявлении статической переменной в `Shared` процедура, только одна копия статическая переменная доступна для всего приложения. Вы вызываете `Shared` имя процедуры с помощью класса, не переменную, которая указывает на экземпляр класса.  
  
 При объявлении статической переменной в процедуре, которая не `Shared`, только одна копия переменной доступен для каждого экземпляра класса. Вызов процедуры без общего доступа, используя переменную, указывающую к определенному экземпляру класса.  
  
## <a name="example"></a>Пример  
 В следующем примере показано использование функции `Static`.  
  
 [!code-vb[VbVbalrKeywords#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class1.vb#5)]  
  
 `Static` Переменной `totalSales` присваивается значение 0 только один раз. При каждом вводе `updateSales`, `totalSales` по-прежнему имеет самое последнее значение, вычисленное для нее.  
  
 `Static` Модификатор может использоваться в этом контексте:  
  
 [Оператор Dim](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
## <a name="see-also"></a>См. также
- [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md)
- [Общие](../../../visual-basic/language-reference/modifiers/shared.md)
- [Время существования в Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)
- [Объявление переменных](../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [Структуры](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [Вывод локального типа](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [Объекты и классы](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
