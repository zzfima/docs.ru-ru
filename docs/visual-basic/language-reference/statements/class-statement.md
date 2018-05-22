---
title: Оператор Class (Visual Basic)
ms.date: 05/12/2018
f1_keywords:
- vb.Class
helpviewer_keywords:
- class modules
- Class statement [Visual Basic]
- classes [Visual Basic], fields
- fields [Visual Basic], of classes
- class types [Visual Basic], class statements
- classes [Visual Basic], creating
- classes [Visual Basic], data members
- data members [Visual Basic], of classes
ms.assetid: f2664f38-eb5a-4d4b-a374-1d041521fb6c
ms.openlocfilehash: 1d81ce148e237df6997934f70c294630f6cc7b8d
ms.sourcegitcommit: 22c3c8f74eaa138dbbbb02eb7d720fce87fc30a9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/17/2018
---
# <a name="class-statement-visual-basic"></a>Оператор Class (Visual Basic)
Объявляет имя класса и вводит определение переменных, свойств, событий и процедур, которые включаются в класс.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
[ <attributelist> ] [ accessmodifier ] [ Shadows ] [ MustInherit | NotInheritable ] [ Partial ] _  
Class name [ ( Of typelist ) ]  
    [ Inherits classname ]  
    [ Implements interfacenames ]  
    [ statements ]  
End Class  
```  
  
## <a name="parts"></a>Части  
  
|Термин|Определение|  
|---|---|  
|`attributelist`|Необязательный. В разделе [список атрибутов](../../../visual-basic/language-reference/statements/attribute-list.md).|  
|`accessmodifier`|Необязательный. Ниже указаны доступные значения.<br /><br /> -   [Public](../../../visual-basic/language-reference/modifiers/public.md)<br />-   [Защищенные](../../../visual-basic/language-reference/modifiers/protected.md)<br />-   [Friend](../../../visual-basic/language-reference/modifiers/friend.md)<br />-   [Закрытый](../../../visual-basic/language-reference/modifiers/private.md)<br />-   [Protected Friend](../../language-reference/modifiers/protected-friend.md)<br />- [Protected Private](../../language-reference/modifiers/private-protected.md)<br/><br/> В разделе [уровни в Visual Basic доступа](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).|  
|`Shadows`|Необязательный. В разделе [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).|  
|`MustInherit`|Необязательный. В разделе [MustInherit](../../../visual-basic/language-reference/modifiers/mustinherit.md).|  
|`NotInheritable`|Необязательный. В разделе [NotInheritable](../../../visual-basic/language-reference/modifiers/notinheritable.md).|  
|`Partial`|Необязательный. Указывает частичное определение класса. В разделе [частичного](../../../visual-basic/language-reference/modifiers/partial.md).|  
|`name`|Обязательно. Имя этого класса. В разделе [имена объявленных элементов](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).|  
|`Of`|Необязательный. Указывает, что это универсальный класс.|  
|`typelist`|Является обязательным, если используется [из](../../../visual-basic/language-reference/statements/of-clause.md) ключевое слово. Список параметров типа для этого класса. В разделе [введите список](../../../visual-basic/language-reference/statements/type-list.md).|  
|`Inherits`|Необязательный. Указывает, что этот класс наследует члены другого класса. В разделе [Инструкция Inherits](../../../visual-basic/language-reference/statements/inherits-statement.md).|  
|`classname`|Является обязательным, если используется `Inherits` инструкции. Имя класса, из которого происходит данный класс.|  
|`Implements`|Необязательный. Указывает, что этот класс реализует члены одного или нескольких интерфейсов. В разделе [реализует оператор](../../../visual-basic/language-reference/statements/implements-statement.md).|  
|`interfacenames`|Является обязательным, если используется `Implements` инструкции. Имена интерфейсов, реализуемых этого класса.|  
|`statements`|Необязательный. Операторы, которые определяют члены этого класса.|  
|`End Class`|Обязательно. Завершает `Class` определения.|  
  
## <a name="remarks"></a>Примечания  
 Объект `Class` инструкция определяет новый тип данных. Объект *класс* является основной строительный блок объектно ориентированное программирование (OOP). Дополнительные сведения см. в разделе [объекты и классы](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md).  
  
 Можно использовать `Class` только на уровне пространства имен или модуля. Это означает *контекст объявления* для класса должен быть исходный файл, пространство имен, класс, структура, модуль или интерфейс и не может быть процедурой или блоком. Дополнительные сведения см. в разделе [Контексты объявления и уровни доступа по умолчанию](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).  
  
 Каждый экземпляр класса имеет время существования, независимое от всех других экземпляров. Это время существования начинается, когда она была создана программой [оператор New](../../../visual-basic/language-reference/operators/new-operator.md) предложение или функцией, такой как <xref:Microsoft.VisualBasic.Interaction.CreateObject%2A>. Оно заканчивается, когда все переменные, указывающие на экземпляр было присвоено значение [ничего](../../../visual-basic/language-reference/nothing.md) или экземпляры других классов.  
  
 По умолчанию для классов [Friend](../../../visual-basic/language-reference/modifiers/friend.md) доступа. Вы можете настроить уровни доступа с помощью модификаторов доступа. Дополнительные сведения см. в разделе [уровни в Visual Basic доступа](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
## <a name="rules"></a>Правила  
  
-   **Вложение.** Можно определить один класс внутри другого. Внешний класс называется *содержащий класс*, а внутренний класс — *вложенных классов*.  
  
-   **Наследование.** Если класс использует [инструкцию наследует](../../../visual-basic/language-reference/statements/inherits-statement.md), можно указать только один базовый класс или интерфейс. Класс не может наследовать от более чем одного элемента.  
  
     Класс не может наследовать от другого класса с более строгим уровнем доступа. Например `Public` класс не может наследовать от `Friend` класса.  
  
     Класс не может наследовать от вложенного в него класса.  
  
-   **Реализация.** Если класс использует [оператор Implements](../../../visual-basic/language-reference/statements/implements-statement.md), должен реализовывать все члены каждого интерфейса, укажите в `interfacenames`. Исключением является повторная реализация члена базового класса. Дополнительные сведения см. в разделе «Повторная реализация» в [реализует](../../../visual-basic/language-reference/statements/implements-clause.md).  
  
-   **Свойство по умолчанию.** Класс можно указать только одно свойство в качестве его *свойство по умолчанию*. Дополнительные сведения см. в разделе [по умолчанию](../../../visual-basic/language-reference/modifiers/default.md).  
  
## <a name="behavior"></a>Поведение  
  
-   **Уровень доступа.** В пределах класса можно объявить каждый член со своим собственным уровнем доступа. По умолчанию члены класса [открытый](../../../visual-basic/language-reference/modifiers/public.md) доступ к, за исключением переменных и констант, который по умолчанию для [закрытый](../../../visual-basic/language-reference/modifiers/private.md) доступа. Если класс более ограниченный доступ, чем один из его членов, уровень доступа класса имеет приоритет.  
  
-   **Область действия.** Класс — область действия его содержащего пространства имен, класса, структуры или модуля.  
  
     Область каждого члена класса является весь класс.  
  
     **Время существования.** Visual Basic не поддерживает статические классы. Функциональный эквивалент статического класса обеспечивается модуля. Дополнительные сведения см. в разделе [оператор Module](../../../visual-basic/language-reference/statements/module-statement.md).  
  
     Члены класса имеют время существования в зависимости от того, как и где они объявлены. Дополнительные сведения см. в разделе [время существования в Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md).  
  
-   **Квалификация.** Код вне класса необходимо предварять именем члена с именем этого класса.  
  
     Если код внутри вложенного класса делает неопределенную ссылку на элемент программирования, Visual Basic ищет элемент сначала во вложенном классе, затем в содержащий его класс, и т. д для внешнего содержащего элемента.  
  
## <a name="classes-and-modules"></a>Классы и модули  
 Эти элементы имеют много общего, но существуют некоторые важные различия.  
  
-   **Терминология.** Предыдущие версии Visual Basic распознает два типа модулей: *модулей класса* (файлы CLS) и *стандартные модули* (файлы BAS). Текущая версия вызывает эти *классы* и *модули*соответственно.  
  
-   **Общие члены.** Можно управлять ли член класса общим или членом экземпляра.  
  
-   **Ориентация на объекты.** Классы являются объектно ориентированного, но модули не будут. Можно создать один или несколько экземпляров класса. Дополнительные сведения см. в разделе [объекты и классы](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md).  
  
## <a name="example"></a>Пример  
 В следующем примере используется `Class` инструкции для определения класса и несколько членов.  
  
 [!code-vb[VbVbalrStatements#62](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/class-statement_1.vb)]  
  
## <a name="see-also"></a>См. также  
 [Объекты и классы](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)  
 [Структуры и классы](../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md)  
 [Оператор Interface](../../../visual-basic/language-reference/statements/interface-statement.md)  
 [Оператор Module](../../../visual-basic/language-reference/statements/module-statement.md)  
 [Оператор Property](../../../visual-basic/language-reference/statements/property-statement.md)  
 [Время существования. Создание и уничтожение объектов](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)  
 [Универсальные типы в Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)  
 [Практическое руководство. Использование универсального класса](../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md)
