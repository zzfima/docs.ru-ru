---
title: Static
ms.date: 07/20/2015
f1_keywords:
- vb.Static
helpviewer_keywords:
- static modifier
- Static keyword [Visual Basic]
ms.assetid: 19013910-4658-47b6-a22e-1744b527979e
ms.openlocfilehash: f020756466888f51298abb423997906ddc7caff7
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350764"
---
# <a name="static-visual-basic"></a>Static (Visual Basic)
Указывает, что одна или несколько объявленных локальных переменных должны продолжать существовать и сохранить их последние значения после завершения процедуры, в которой они объявляются.  
  
## <a name="remarks"></a>Примечания  
 Как правило, локальная переменная в процедуре прекращает свое существование сразу после остановки процедуры. Статическая переменная продолжает существовать и сохраняет ее Последнее значение. В следующий раз, когда код вызывает процедуру, переменная не инициализируется повторно, и она по-прежнему содержит Последнее назначенное ей значение. Статическая переменная будет существовать в течение времени существования класса или модуля, в котором он определен.  
  
## <a name="rules"></a>Правила  
  
- **Контекст объявления.** `Static` можно использовать только для локальных переменных. Это означает, что контекст объявления для переменной `Static` должен быть процедурой или блоком в процедуре и не может быть исходным файлом, пространством имен, классом, структурой или модулем.  
  
     Нельзя использовать `Static` внутри процедуры структуры.  
  
- Невозможно вывести типы данных `Static` локальных переменных. Дополнительные сведения см. в разделе [определение локального типа](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).  
  
- **Комбинированные модификаторы.** В одном объявлении нельзя указать `Static` вместе с `ReadOnly`, `Shadows`или `Shared`.  
  
## <a name="behavior"></a>Поведение  
 При объявлении статической переменной в `Shared`ной процедуре для всего приложения доступна только одна копия статической переменной. Процедура `Shared` вызывается с помощью имени класса, а не переменной, указывающей на экземпляр класса.  
  
 При объявлении статической переменной в процедуре, которая не `Shared`, для каждого экземпляра класса доступна только одна копия переменной. Для вызова процедуры, которая не является общей, используется переменная, указывающая на конкретный экземпляр класса.  
  
## <a name="example"></a>Пример  
 В следующем примере показано использование функции `Static`.  
  
 [!code-vb[VbVbalrKeywords#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class1.vb#5)]  
  
 Переменная `Static` `totalSales` инициализируется значением 0 только один раз. Каждый раз при вводе `updateSales``totalSales` по-прежнему будет иметь самое последнее значение, вычисленное для него.  
  
 Модификатор `Static` можно использовать в этом контексте:  
  
 [Оператор Dim](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
## <a name="see-also"></a>См. также

- [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md)
- [Общие](../../../visual-basic/language-reference/modifiers/shared.md)
- [Время существования в Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)
- [Объявление переменных](../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [Структуры](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [Вывод локального типа](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [Объекты и классы](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
