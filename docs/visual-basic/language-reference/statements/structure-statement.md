---
title: "Оператор Structure | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Structure"
  - "Structure"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "составные типы данных"
  - "Structure - ключевое слово"
  - "Structure - оператор"
  - "типы [Visual Basic], определяемые пользователем"
  - "UDT (пользовательские типы)"
  - "типы, определяемые пользователем, Structure - оператор"
ms.assetid: 9bd1deea-2a89-4cdc-812c-6dcbb947c391
caps.latest.revision: 28
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 28
---
# Оператор Structure
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Объявляет имя структуры и представляет определения переменных, свойств, событий и процедур, которые объединены в структуру.  
  
## Синтаксис  
  
```  
[ <attributelist> ] [ accessmodifier ] [ Shadows ] [ Partial ] _  
Structure name [ ( Of typelist ) ]  
    [ Implements interfacenames ]  
    [ datamemberdeclarations ]  
    [ methodmemberdeclarations ]  
End Structure  
```  
  
## Части  
  
|||  
|-|-|  
|Термин|Определение|  
|`attributelist`|Необязательный.  См. [Список атрибутов](../../../visual-basic/language-reference/statements/attribute-list.md).|  
|`accessmodifier`|Необязательный.  Может принимать следующие значения:<br /><br /> -   [Открытый](../../../visual-basic/language-reference/modifiers/public.md)<br />-   [Защищенный](../../../visual-basic/language-reference/modifiers/protected.md)<br />-   [Friend](../../../visual-basic/language-reference/modifiers/friend.md)<br />-   [Закрытый](../../../visual-basic/language-reference/modifiers/private.md)<br />-   `Protected Friend`<br /><br /> Дополнительные сведения см. в разделе [Уровни доступа в Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).|  
|`Shadows`|Необязательный.  См. раздел [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).|  
|`Partial`|Необязательный.  Показывает частичное определение структуры.  Дополнительные сведения см. в разделе [Partial](../../../visual-basic/language-reference/modifiers/partial.md).|  
|`name`|Обязательный.  Имя данной структуры.  См. раздел [Имена объявленных элементов](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).|  
|`Of`|Необязательный.  Указывает на то, что это общая структура.|  
|`typelist`|Является обязательным, если используется ключевое слово [Of](../../../visual-basic/language-reference/statements/of-clause.md).  Список параметров типа для данной структуры.  См. раздел [Список типов](../../../visual-basic/language-reference/statements/type-list.md).|  
|`Implements`|Необязательный.  Указывает на то, что эта структура реализует члены одного или нескольких интерфейсов.  Дополнительные сведения см. в разделе [Оператор Implements](../../../visual-basic/language-reference/statements/implements-statement.md).|  
|`interfacenames`|Является обязательным, если используется оператор `Implements`.  Имена интерфейсов, реализуемых структурой.|  
|`datamemberdeclarations`|Обязательный.  Ноль или более `Const`, `Dim`, `Enum` или выписка `Event` при объявлении *элементы данных* структуры.|  
|`methodmemberdeclarations`|Необязательный.  Более одного объявления процедур `Function`, `Operator` `Property` или `Sub`, которые выступают в качестве *членов\-методов* структуры.|  
|`End Structure`|Обязательный.  Завершает определение `Structure`.|  
  
## Заметки  
 Инструкция `Structure` определяет тип составного типа значения, который можно настроить.  *Структура* является обобщением определяемых пользователем типов \(UDT\), предыдущих версий Visual Basic.  Для получения дополнительной информации см. [Структуры](../../../visual-basic/programming-guide/language-features/data-types/structures.md).  
  
 Структуры поддерживают работу со многими из тех элементов, с которыми работают классы.  Например, структуры могут иметь свойства и процедуры, реализовывать интерфейсы и иметь параметризованные конструкторы.  Однако в отношении наследования, объявлений и использования между структурами и классами существуют значительные различия.  Также классы относятся к ссылочным типам, а структуры — к типам значений.  Для получения дополнительной информации см. [Структуры и классы](../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md).  
  
 `Structure` можно использовать только на уровне пространства имен или модуля.  Это означает, что *контекст объявления* для структуры должен быть исходным файлом, пространством имен, классом, структурой, модулем или интерфейсом, и не может быть процедурой или блоком.  Для получения дополнительной информации см. [Контексты объявления и уровни доступа по умолчанию](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).  
  
 Структуры имеют по умолчанию доступ [Friend](../../../visual-basic/language-reference/modifiers/friend.md).  Уровни доступа можно настроить с помощью модификаторов доступа.  Для получения дополнительной информации см. [Уровни доступа в Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
## Правила  
  
-   **Вложения.** Можно определить одну структуру внутри другой.  Внешняя структура называется *содержащей структурой*, а внутренние структуры называются *вложенными структурами*.  Однако невозможно будет получить доступ к членам вложенной структуры через содержащую структуру.  Вместо этого следует объявить переменную типа данных вложенной структуры.  
  
-   **Объявление члена.**  Необходимо объявить все элементы структуры.  Член структуры не может быть [Protected](../../../visual-basic/language-reference/modifiers/protected.md) или `Protected Friend`, поскольку ничто не может наследовать от структуры.  Структура, однако, может быть `Protected` или `Protected Friend`.  
  
     Можно объявить ноль или более общей переменной или собственным, события без общего доступа в структуре.  Структура не может содержать только константы, свойства и процедуры, даже если некоторые из них не используются совместно.  
  
-   **Инициализация.** Инициализация значений неиспользуемых совместно данных\-членов структуры не может быть частью их объявлений.  Инициализация таких данных\-членов должна выполняться на структуре с помощью параметризованного конструктора или путем присваивания значения члену после создания экземпляра структуры.  
  
-   **Наследование.** Структура не может наследовать от типа, отличного от <xref:System.ValueType>, от которого наследуют все структуры.  В частности, одна структура не может наследовать от другой.  
  
     Нельзя использовать [Инструкция Inherits](../../../visual-basic/language-reference/statements/inherits-statement.md) в определении структуры, даже для указания <xref:System.ValueType>.  
  
-   **Реализация.** Если структура использует [Оператор Implements](../../../visual-basic/language-reference/statements/implements-statement.md), необходимо реализовать каждый член, определенный каждым интерфейсом, заданным в `interfacenames`.  
  
-   **Атрибут по умолчанию.** Структура может определять максимум одно свойство в качестве *свойства по умолчанию* с помощью модификатора [Default](../../../visual-basic/language-reference/modifiers/default.md).  Для получения дополнительной информации см. [Default](../../../visual-basic/language-reference/modifiers/default.md).  
  
## Поведение  
  
-   **Уровень доступа.** Внутри структуры можно объявить каждый член со своим собственным уровнем доступа.  Все члены структуры по умолчанию имеют доступ [Public](../../../visual-basic/language-reference/modifiers/public.md).  Обратите внимание: если структура сама по себе имеет более ограниченный уровень доступа, это автоматически ограничивает доступ к ее членам, даже если отрегулировать их уровни доступа модификатором доступа.  
  
-   **Область действия.** Область действия структуры — ее пространство имен, класс, структура или модуль.  
  
     Областью действия каждого члена структуры является вся структура.  
  
-   **Время существования.** Для самой структуры не определено время существования.  Вместо этого каждый экземпляр данной структуры имеет время существования, независимое от всех других экземпляров.  
  
     Время существования экземпляра начинается, когда он создается условием [Оператор New](../../../visual-basic/language-reference/operators/new-operator.md).  Оно заканчивается, когда заканчивается время существования переменной, содержащей его.  
  
     Нельзя увеличить время существования экземпляра структуры.  Приближение к функциональности статической структуры обеспечивается модулем.  Для получения дополнительной информации см. [Оператор Module](../../../visual-basic/language-reference/statements/module-statement.md).  
  
     У членов структуры время существования зависит от того, как и где они были объявлены.  Дополнительные сведения содержатся в разделе "Время жизни" в [Оператор Class](../../../visual-basic/language-reference/statements/class-statement.md).  
  
-   **Квалификация.** Код вне структуры должен определять имя члена с именем этой структуры.  
  
     Если код внутри вложенной структуры делает неопределенную ссылку на элемент программирования, Visual Basic ищет элемент сначала во вложенной структуре, затем в его содержащей структуре, и т.д., вплоть до внешнего содержащего элемента.  Для получения дополнительной информации см. [Ссылки на объявленные элементы](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).  
  
-   **Потребление ресурсов памяти**. Как и для всех составных типов данных, нельзя точно подсчитать общее потребление ресурсов памяти структуры простым сложением номинальных объемов памяти, занимаемых отдельными членами структуры.  Более того, нельзя однозначно полагать, что порядок расположения элементов в памяти такой же, как и порядок их объявления.  Если требуется контролировать расположение структуры в памяти, можно применить атрибут <xref:System.Runtime.InteropServices.StructLayoutAttribute> в операторе `Structure`.  
  
## Пример  
 В следующем примере оператор `Structure` применяется для определения набора связанных данных о сотруднике.  Демонстрируется использование компонентов `Public`, `Friend`, и `Private`, позволяющих управлять доступом к элементам данных.  Также показаны компоненты процедуры, свойств и событий.  
  
 [!code-vb[VbVbalrStatements#57](../../../visual-basic/language-reference/error-messages/codesnippet/visualbasic/structure-statement_1.vb)]  
  
## См. также  
 [Оператор Class](../../../visual-basic/language-reference/statements/class-statement.md)   
 [Оператор Interface](../../../visual-basic/language-reference/statements/interface-statement.md)   
 [Оператор Module](../../../visual-basic/language-reference/statements/module-statement.md)   
 [Оператор Dim](../../../visual-basic/language-reference/statements/dim-statement.md)   
 [Оператор Const](../../../visual-basic/language-reference/statements/const-statement.md)   
 [Оператор Enum](../../../visual-basic/language-reference/statements/enum-statement.md)   
 [Оператор Event](../../../visual-basic/language-reference/statements/event-statement.md)   
 [Оператор Operator](../../../visual-basic/language-reference/statements/operator-statement.md)   
 [Оператор Property](../../../visual-basic/language-reference/statements/property-statement.md)   
 [Структуры и классы](../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md)