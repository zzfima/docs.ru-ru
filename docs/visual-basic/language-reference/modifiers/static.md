---
title: "Static (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Static"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Static - ключевое слово"
  - "static - модификатор"
ms.assetid: 19013910-4658-47b6-a22e-1744b527979e
caps.latest.revision: 22
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 22
---
# Static (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Определяет, что одна или несколько объявленных локальных переменных продолжают сохранять самые последние значения после завершения процедуры, в которых они объявлены.  
  
## Заметки  
 Как правило, локальная переменная в процедуре прекращает свое существование сразу же после окончания выполнения процедуры.  Статические переменные продолжают существовать, сохраняя самое последнее значение.  При следующем вызове процедуры переменная не инициализируется повторно, а хранит последнее значение, которое ей было присвоено при последнем вызове процедуры.  Статические переменные продолжают существовать в течение времени существования класса или модуля, в которых она определена.  
  
## Правила  
  
-   **Контекст объявления.** Можно использовать `Static` только для локальных переменных.  Это означает, что контекст объявления для переменной `Static` должен быть классом, структурой, модулем или интерфейсом, и не может быть исходным файлом, пространством имен, структурой или модулем.  
  
     Нельзя использовать `Static` внутри структуры процедуры.  
  
-   Типы данных локальных переменных `Static` не могут быть выведены.  Дополнительные сведения см. в разделе [Вывод локального типа](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).  
  
-   **Комбинированные модификаторы.** Нельзя указывать в одном объявлении `Static` вместе с `ReadOnly`, `Shadows` или `Shared`.  
  
## Поведение  
 При объявлении статическую переменную в процедуре `Shared` только одна копия статической переменной доступна для всего приложения.  Вызове процедуры по `Shared` с помощью имени класса, а не переменную, указывающий на экземпляр класса.  
  
 При объявлении статическую переменную в процедуре, которая не является `Shared` только одна копия переменной доступна для каждого экземпляра класса.  Вызове non\-совместно используемой процедуры с помощью переменной, которая указывает на конкретный экземпляр класса.  
  
## Пример  
 Следующий пример демонстрирует использование `Static`.  
  
 [!code-vb[VbVbalrKeywords#5](../../../visual-basic/language-reference/codesnippet/visualbasic/static_1.vb)]  
  
 Переменная `Static` `totalSales` инициализируется с помощью значения 0 только один раз.  Каждый раз, когда вводится `updateSales`, переменная `totalSales` по\-прежнему хранит самое последнее вычисленное для нее значение.  
  
 Модификатор `Static` можно использовать в следующем контексте.  
  
 [Оператор Dim](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
## См. также  
 [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md)   
 [Shared](../../../visual-basic/language-reference/modifiers/shared.md)   
 [Время существования в Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)   
 [Объявление переменной](../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)   
 [Структуры](../../../visual-basic/programming-guide/language-features/data-types/structures.md)   
 [Вывод локального типа](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)   
 [Объекты и классы](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)