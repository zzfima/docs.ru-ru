---
title: "&lt;имяТипа&gt; не может наследоваться от &lt;тип&gt; &lt;имяБазовогоТипа&gt;, поскольку он расширяет доступ базового типа &lt;тип&gt; за пределы сборки | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbc30910"
  - "bc30910"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30910"
ms.assetid: 68fc05c5-5d55-4742-9a3b-ea04312594f4
caps.latest.revision: 8
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 8
---
# &lt;имяТипа&gt; не может наследоваться от &lt;тип&gt; &lt;имяБазовогоТипа&gt;, поскольку он расширяет доступ базового типа &lt;тип&gt; за пределы сборки
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Класс или интерфейс наследует базовый класс или интерфейс, но имеет менее строгий уровень доступа.  
  
 Например интерфейс `Public` наследуется от интерфейса `Friend` или класс `Protected` наследуется от класса `Private`.  Это предоставляет доступ к базовому классу или интерфейсу выше установленного уровня.  
  
 **Идентификатор ошибки**: BC30910  
  
### Чтобы исправить эту ошибку  
  
-   Замените уровень доступа производного класса или интерфейса, по крайней мере, на такой же, как у базового класса или интерфейса.  
  
     \-или\-  
  
-   Если требуется менее строгий уровень доступа, удалите оператор `Inherits`.  Наследование от базового класса или интерфейса с более строгими ограничениями невозможно.  
  
## См. также  
 [Оператор Class](../../../visual-basic/language-reference/statements/class-statement.md)   
 [Оператор Interface](../../../visual-basic/language-reference/statements/interface-statement.md)   
 [Инструкция Inherits](../../../visual-basic/language-reference/statements/inherits-statement.md)   
 [Уровни доступа в Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)