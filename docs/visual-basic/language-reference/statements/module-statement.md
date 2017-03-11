---
title: "Оператор Module | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "Module"
  - "vb.Module"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "классы [Visual Basic], в сравнении с модулями"
  - "декларации, модули"
  - "Module - оператор"
  - "модули"
  - "модули, классы"
  - "модули, объявление"
  - "стандартные модули"
ms.assetid: a1243afc-14a5-45df-95d5-51118aeac362
caps.latest.revision: 24
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 24
---
# Оператор Module
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Объявляет имя модуля и представляет определения переменных, свойств, событий и процедур, которые включены в модуль.  
  
## Синтаксис  
  
```  
[ <attributelist> ] [ accessmodifier ]  Module name  
    [ statements ]  
End Module  
```  
  
## Части  
 `attributelist`  
 Необязательный.  Дополнительные сведения см. в разделе [Список атрибутов](../../../visual-basic/language-reference/statements/attribute-list.md).  
  
 `accessmodifier`  
 Необязательный.  Может принимать следующие значения:  
  
-   [Открытый](../../../visual-basic/language-reference/modifiers/public.md)  
  
-   [Friend](../../../visual-basic/language-reference/modifiers/friend.md)  
  
 Дополнительные сведения см. в разделе [Уровни доступа в Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
 `name`  
 Обязательный.  Имя этого модуля.  См. раздел [Имена объявленных элементов](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).  
  
 `statements`  
 Необязательный.  Операторы, которые определяют переменные, свойства, события, процедуры и вложенные типы этого модуля.  
  
 `End Module`  
 Завершает определение `Module`.  
  
## Заметки  
 Оператор `Module` определяет ссылочный тип, доступный для всего пространства имен.   *Модуль*  \(иногда называемый *стандартный модуль*\)  имеет некоторое сходство с классом, однако, существуют важные различия.  Каждый модуль имеет ровно один экземпляр и не требует создания или присваивания переменной.  Модули не поддерживают наследование и не реализуют интерфейсы.  Обратите внимание, что модуль не является *типом* \(таким как класс или структура\), поэтому нельзя объявлять элемент программирования с типом данных "модуль".  
  
 Можно использовать `Module` только на уровне пространства имен.  Это означает, что *контекст объявления* для модуля должен быть исходным файлом или пространством имен и не может быть классом, структурой, модулем, интерфейсом, процедурой или блоком.  Нельзя вкладывать модуль в другой модуль или в какой\-либо тип.  Дополнительные сведения см. в разделе [Контексты объявления и уровни доступа по умолчанию](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).  
  
 Модуль имеет то же время существования, что и программа.  Поскольку все элементы модуля являются `Shared`, они также имеют время существования равное времени существования программы.  
  
 Модули по умолчанию имеют уровень доступа [Friend](../../../visual-basic/language-reference/modifiers/friend.md).  Уровни доступа можно настроить с помощью модификаторов доступа.  Дополнительные сведения см. в разделе [Уровни доступа в Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
 Все элементы модуля являются неявно `Shared`.  
  
## Классы и модули  
 Эти элементы имеют много общего, но существуют важные различия.  
  
-   **Терминология.** Предыдущие версии Visual Basic различают два типа модулей: *модули класса* \(файлы CLS\) и *стандартные модули* \(файлы BAS\).  В текущей версии они называются соответственно *классами* и *модулями*.  
  
-   **Общие члены.** Можно управлять тем, является ли член класса общим или членом экземпляра.  
  
-   **Объектная ориентация.** Классы являются объектно ориентированными, а модули — нет.  Поэтому только классы могут быть созданы как объекты.  Дополнительные сведения см. в разделе [Объекты и классы](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md).  
  
## Правила  
  
-   **Модификаторы.** Все элементы модулей неявно [Shared](../../../visual-basic/language-reference/modifiers/shared.md).  Нельзя использовать ключевое слово `Shared` при объявлении элементов, также невозможно изменить статус "shared" любого элемента.  
  
-   **Наследование.** Модуль не может наследовать от типа, отличного от <xref:System.Object>, от которого наследуют все модули.  В частности, один модуль не может наследовать от другого.  
  
     Нельзя использовать [Инструкция Inherits](../../../visual-basic/language-reference/statements/inherits-statement.md) в определении модуля даже для указания <xref:System.Object>.  
  
-   **Атрибут по умолчанию.** В модуле нельзя определять свойства по умолчанию.  Дополнительные сведения см. в разделе [Default](../../../visual-basic/language-reference/modifiers/default.md).  
  
## Поведение  
  
-   **Уровень доступа.** В модуле можно объявить каждый элемент со своим собственным уровнем доступа.  Элементы модуля по умолчанию имеют уровень доступа [Public](../../../visual-basic/language-reference/modifiers/public.md), за исключением переменных и констант, которые по умолчанию имеют уровень доступа [Private](../../../visual-basic/language-reference/modifiers/private.md).  Если модуль содержит более ограниченный доступ, чем один из его элементов, заданный уровень доступа к модулю имеет более высокий приоритет.  
  
-   **Область действия.** Область действия модуля распространяется на все его пространство имен.  
  
     Областью действия для каждого элемента модуля является весь модуль.  Обратите внимание, что все элементы претерпевают *повышение типа*, в результате чего их область действия расширяется до пространства имен, содержащего модуль.  Дополнительные сведения см. в разделе [Повышение типа](../../../visual-basic/programming-guide/language-features/declared-elements/type-promotion.md).  
  
-   **Квалификация.** В проекте может быть несколько модулей; можно объявлять элементы с одним и тем же именем в двух или нескольких модулях.  Однако если ссылка на элемент модуля находится за пределами модуля, то в ней необходимо указывать соответствующее имя модуля.  Дополнительные сведения см. в разделе [Ссылки на объявленные элементы](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).  
  
## Пример  
 [!code-vb[VbVbalrStatements#69](../../../visual-basic/language-reference/error-messages/codesnippet/visualbasic/module-statement_1.vb)]  
  
## См. также  
 [Оператор Class](../../../visual-basic/language-reference/statements/class-statement.md)   
 [Оператор Namespace](../../../visual-basic/language-reference/statements/namespace-statement.md)   
 [Оператор Structure](../../../visual-basic/language-reference/statements/structure-statement.md)   
 [Оператор Interface](../../../visual-basic/language-reference/statements/interface-statement.md)   
 [Оператор Property](../../../visual-basic/language-reference/statements/property-statement.md)   
 [Повышение типа](../../../visual-basic/programming-guide/language-features/declared-elements/type-promotion.md)