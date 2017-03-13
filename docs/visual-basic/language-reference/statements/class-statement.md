---
title: "Оператор Class (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Class"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "модули класса"
  - "Class - оператор"
  - "типы классов, операторы class"
  - "классы [Visual Basic], создание"
  - "классы [Visual Basic], члены данных"
  - "классы [Visual Basic], поля"
  - "члены данных, классов"
  - "поля, классов"
ms.assetid: f2664f38-eb5a-4d4b-a374-1d041521fb6c
caps.latest.revision: 29
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 29
---
# Оператор Class (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Объявляет имя класса и представляет определения переменных, свойств, событий и процедур, которые включаются в класс.  
  
## Синтаксис  
  
```  
[ <attributelist> ] [ accessmodifier ] [ Shadows ] [ MustInherit | NotInheritable ] [ Partial ] _  
Class name [ ( Of typelist ) ]  
    [ Inherits classname ]  
    [ Implements interfacenames ]  
    [ statements ]  
End Class  
```  
  
## Части  
  
|||  
|-|-|  
|Термин|Определение|  
|`attributelist`|Необязательный.  См. [Список атрибутов](../../../visual-basic/language-reference/statements/attribute-list.md).|  
|`accessmodifier`|Необязательный.  Может принимать следующие значения:<br /><br /> -   [Открытый](../../../visual-basic/language-reference/modifiers/public.md)<br />-   [Защищенный](../../../visual-basic/language-reference/modifiers/protected.md)<br />-   [Friend](../../../visual-basic/language-reference/modifiers/friend.md)<br />-   [Закрытый](../../../visual-basic/language-reference/modifiers/private.md)<br />-   `Protected Friend`<br /><br /> Дополнительные сведения см. в разделе [Уровни доступа в Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).|  
|`Shadows`|Необязательный.  См. раздел [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).|  
|`MustInherit`|Необязательный.  Дополнительные сведения см. в разделе [MustInherit](../../../visual-basic/language-reference/modifiers/mustinherit.md).|  
|`NotInheritable`|Необязательный.  Дополнительные сведения см. в разделе [NotInheritable](../../../visual-basic/language-reference/modifiers/notinheritable.md).|  
|`Partial`|Необязательный.  Указывает частичное определение класса.  Дополнительные сведения см. в разделе [Partial](../../../visual-basic/language-reference/modifiers/partial.md).|  
|`name`|Обязательный.  Имя этого класса.  См. раздел [Имена объявленных элементов](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).|  
|`Of`|Необязательный.  Указывает на принадлежность к универсальному классу.|  
|`typelist`|Является обязательным, если используется ключевое слово [Of](../../../visual-basic/language-reference/statements/of-clause.md).  Список типов параметров для данного класса.  См. раздел [Список типов](../../../visual-basic/language-reference/statements/type-list.md).|  
|`Inherits`|Необязательный.  Указывает на то, что данный класс наследует члены другого класса.  Дополнительные сведения см. в разделе [Инструкция Inherits](../../../visual-basic/language-reference/statements/inherits-statement.md).|  
|`classname`|Является обязательным, если используется оператор `Inherits`.  Имя класса, от которого наследует данный класс.|  
|`Implements`|Необязательный.  Указывает на то, что этот класс реализует члены одного или нескольких интерфейсов.  Дополнительные сведения см. в разделе [Оператор Implements](../../../visual-basic/language-reference/statements/implements-statement.md).|  
|`interfacenames`|Является обязательным, если используется оператор `Implements`.  Имена интерфейсов, реализуемых данным классом.|  
|`statements`|Необязательный.  Операторы, определяющие члены этого класса.|  
|`End Class`|Обязательный.  Завершает определение `Class`.|  
  
## Заметки  
 Оператор `Class` определяет новый тип данных.  *Класс* является основным строительным блоком в объектно\-ориентированном программировании \(OOP\).  Дополнительные сведения см. в разделе [Объекты и классы](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md).  
  
 Оператор `Class` можно использовать только на уровне пространства имен или модуля.  Это означает, что *контекстом объявления* для класса должен быть исходный файл, пространство имен, класс, структура, модуль или интерфейс и не может быть процедура или блок.  Дополнительные сведения см. в разделе [Контексты объявления и уровни доступа по умолчанию](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).  
  
 Каждый экземпляр класса имеет время жизни, не зависящее от всех других экземпляров.  Это время жизни начинается при создании экземпляра предложением [Оператор New](../../../visual-basic/language-reference/operators/new-operator.md) или функцией, например <xref:Microsoft.VisualBasic.Interaction.CreateObject%2A>.  Оно заканчивается, когда все переменные, указывающие на экземпляр были установлены в [Nothing](../../../visual-basic/language-reference/nothing.md) или в экземпляры других классов.  
  
 Классы по умолчанию имеют доступ [Friend](../../../visual-basic/language-reference/modifiers/friend.md).  Уровни доступа можно настроить с помощью модификаторов доступа.  Дополнительные сведения см. в разделе [Уровни доступа в Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
## Правила  
  
-   **Вложения.** Можно определить один класс внутри другого.  Внешний класс называется *содержащим классом*, а внутренний класс — *вложенным классом*.  
  
-   **Наследование.** Если класс использует [Инструкция Inherits](../../../visual-basic/language-reference/statements/inherits-statement.md), то можно указать только один базовый класс или интерфейс.  Класс не может наследовать от нескольких элементов.  
  
     Класс не может наследовать от другого класса с более строгим уровнем доступа.  Например, класс `Public` не может наследовать от класса `Friend`.  
  
     Класс не может наследовать от вложенного в него класса.  
  
-   **Реализация.** Если класс использует [Оператор Implements](../../../visual-basic/language-reference/statements/implements-statement.md), то необходимо реализовать каждый член, определенный каждым интерфейсом в `interfacenames`.  Исключение составляет повторная реализация члена базового класса.  Дополнительные сведения см. в главе "Повторная реализация" раздела [Implements](../../../visual-basic/language-reference/statements/implements-clause.md).  
  
-   **Атрибут по умолчанию.** Класс может указать только одно свойство в качестве *свойства по умолчанию*.  Дополнительные сведения см. в разделе [Default](../../../visual-basic/language-reference/modifiers/default.md).  
  
## Поведение  
  
-   **Уровень доступа.** В классе можно объявить каждый член со своим собственным уровнем доступа.  Члены класса по умолчанию имеют доступ [Public](../../../visual-basic/language-reference/modifiers/public.md), за исключением переменных и констант, которые по умолчанию имеют доступ [Private](../../../visual-basic/language-reference/modifiers/private.md).  Если класс имеет более ограниченный доступ, чем один из его членов, уровень доступа к заданному классу имеет больший приоритет.  
  
-   **Область действия.** Область действия класса — его пространство имен, класс, структура или модуль.  
  
     Областью действия каждого члена класса является весь класс.  
  
     **Время существования.** Visual Basic не поддерживает статические классы.  Функциональный эквивалент статического класса обеспечивается модулем.  Дополнительные сведения см. в разделе [Оператор Module](../../../visual-basic/language-reference/statements/module-statement.md).  
  
     Время существования членов класса зависит от того, как и где они были объявлены.  Дополнительные сведения см. в разделе [Время существования в Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md).  
  
-   **Квалификация.** Код вне класса должен предварять имя члена именем этого класса.  
  
     Если код внутри вложенного класса делает неполную ссылку на элемент программирования, Visual Basic ищет элемент сначала во вложенном классе, затем в содержащем его классе, и так далее до выхода из внешнего содержащего элемента.  
  
## Классы и модули  
 Эти элементы имеют много общего, но существуют важные различия.  
  
-   **Терминология.** Предыдущие версии Visual Basic различают два типа модулей: *модули класса* \(файлы CLS\) и *стандартные модули* \(файлы BAS\).  В текущей версии они называются соответственно *классами* и *модулями*.  
  
-   **Общие члены.** Можно управлять тем, является ли член класса общим или членом экземпляра.  
  
-   **Объектная ориентация.** Классы являются объектно ориентированными, а модули — нет.  Пользователь может создать один или несколько экземпляров класса.  Дополнительные сведения см. в разделе [Объекты и классы](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md).  
  
## Пример  
 В следующем примере оператор `Class` используется для определения класса и нескольких членов.  
  
 [!code-vb[VbVbalrStatements#62](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/class-statement_1.vb)]  
  
## См. также  
 [Объекты и классы](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)   
 [Структуры и классы](../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md)   
 [Оператор Interface](../../../visual-basic/language-reference/statements/interface-statement.md)   
 [Оператор Module](../../../visual-basic/language-reference/statements/module-statement.md)   
 [Оператор Property](../../../visual-basic/language-reference/statements/property-statement.md)   
 [Время существования: создание и уничтожение объектов](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)   
 [Универсальные типы в Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)   
 [Практическое руководство. Использование универсального класса](../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md)