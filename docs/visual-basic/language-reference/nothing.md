---
title: "Nothing (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "Nothing"
  - "vb.Nothing"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Nothing - ключевое слово"
  - "Nothing - ключевое слово, синтаксис"
ms.assetid: 06176e2d-bbf7-4a37-afaa-a86ad21ee99f
caps.latest.revision: 31
caps.handback.revision: 31
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Nothing (Visual Basic)
[!INCLUDE[vs2017banner](../../csharp/includes/vs2017banner.md)]

Представляет значение по умолчанию любого типа данных.  Для ссылочных типов значение по умолчанию `null` ссылка.  Для типов значений, зависят от значений по умолчанию, является ли тип значения null.  
  
> [!NOTE]
>  Для типов значений, не допускающие значения null `Nothing` в Visual Basic отличается от  `null` в c\#.  В Visual Basic, если нужно задать переменную типа значения null `Nothing`переменная имеет значение по умолчанию для своего объявленного типа.  В c\# при присвоении переменной значения типа null `null`возникает ошибка времени компиляции.  
  
## Заметки  
 `Nothing` представляет значение по умолчанию для типа данных.  Зависит от значений по умолчанию, является ли переменная типа значения или ссылочного типа.  
  
 Переменная a *тип значения* непосредственно содержащий его значение.  Типы значений включают все числовые типы данных `Boolean`"  `Char`"  `Date`все структуры и перечисления.  Переменная a *ссылочный тип* хранит ссылку на экземпляр объекта в памяти.  Ссылочные типы включают классы, массивы, делегаты и строки.  Дополнительные сведения см. в разделе [Типы значений и ссылочные типы](../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md).  
  
 Если переменная типа значения, то применяются расширения функциональности `Nothing` зависит от того, является ли переменная типа данных значения null.  Для представления значения null тип значения, добавьте a `?` модификатор к имени типа.  Присвоить `Nothing` присваивает значение переменной значение null  `null`.  Дополнительные сведения и примеры см. в разделе [Типы значения, допускающие Null](../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md).  
  
 Если переменная типа значения, не допускает значения null, присвоить `Nothing` на него задается значение по умолчанию для своего объявленного типа.  Если тип содержит элементы переменных, для них задаются соответствующие значения по умолчанию.  Следующий пример иллюстрирует это для скалярных типов.  
  
 [!code-vb[VbVbalrKeywords#7](../../visual-basic/language-reference/codesnippet/VisualBasic/nothing_1.vb)]  
  
 Если переменная ссылочного типа, то присвоить `Nothing` к переменным наборам его к a  `null` ссылка на тип переменной.  Переменная, которой присваивается a `null` ссылка не связана с любым объектом.  Это показано в приведенном ниже примере.  
  
 [!code-vb[VbVbalrKeywords#8](../../visual-basic/language-reference/codesnippet/VisualBasic/nothing_2.vb)]  
  
 Проверяющий, является ли переменная ссылки или типа значения \(null\) `null`не используйте  `= Nothing` OR  `<> Nothing`.  Всегда пользуйтесь `Is Nothing` OR  `IsNot Nothing`.  
  
 Для строк в Visual Basic, равно пустой строке `Nothing`.  Следовательно, `"" = Nothing` \- true.  
  
 В следующем примере показаны сравнения с использованием операторов `Is` и `IsNot`.  
  
 [!code-vb[VbVbalrKeywords#9](../../visual-basic/language-reference/codesnippet/VisualBasic/nothing_3.vb)]  
  
 Если объявить переменную без использования предложения `As` и задать ей значение `Nothing`, переменная имеет тип `Object`.  Примером этого является `Dim something = Nothing`.  Ошибка времени компиляции в этом случае при возникновении `Option Strict` и  `Option Infer` .  
  
 При присвоении объектной переменной ключевого слова `Nothing` она больше не ссылается на какой\-либо экземпляр объекта.  Если переменная ранее содержала ссылку на экземпляр, задание ключевого слова `Nothing` не удаляет экземпляр как таковой.  Использование экземпляра прекращается, и связанные с ним память и системные ресурсы освобождаются только после того, как сборщик мусора \(GC\) обнаружит, что не осталось активных ссылок на экземпляр.  
  
 `Nothing` отличается от  <xref:System.DBNull> объект, который представляет неинициализированных версий или несуществующий столбец базы данных.  
  
## См. также  
 [Оператор Dim](../../visual-basic/language-reference/statements/dim-statement.md)   
 [Время существования: создание и уничтожение объектов](../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)   
 [Время существования в Visual Basic](../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)   
 [Оператор Is](../../visual-basic/language-reference/operators/is-operator.md)   
 [Оператор IsNot](../../visual-basic/language-reference/operators/isnot-operator.md)   
 [Типы значения, допускающие Null](../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)