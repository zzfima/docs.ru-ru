---
title: "Объект или класс не поддерживает набор событий | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbrID459"
dev_langs: 
  - "VB"
ms.assetid: 785df3f3-2aae-4a25-af36-1f9879d4e5fd
caps.latest.revision: 8
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 8
---
# Объект или класс не поддерживает набор событий
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Предпринята попытка использования переменной `WithEvents` с компонентом, который не может служить источником событий для указанного набора событий.  Если, например требуется приемник событий объекта, создайте другой объект, который `Implements` \(реализует\) первый объект.  Хотя может показаться, что можно управлять событиями из реализованного объекта, это не всегда является правильным решением.  Ключевое слово `Implements` реализует только интерфейс для методов и свойств.  `WithEvents` не поддерживается для закрытых`UserControls`, поскольку сведения о типе, необходимые для вызова `ObjectEvent`, не доступны во время выполнения.  
  
### Чтобы исправить эту ошибку  
  
1.  Получить события для компонента, который не является источником событий, невозможно.  
  
## См. также  
 [WithEvents](../../../visual-basic/language-reference/modifiers/withevents.md)   
 [Оператор Implements](../../../visual-basic/language-reference/statements/implements-statement.md)