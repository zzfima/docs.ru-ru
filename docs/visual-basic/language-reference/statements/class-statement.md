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
ms.openlocfilehash: 68401571645d77a41b827c13b3cfc3674076e218
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "58824576"
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
|`attributelist`|Необязательный параметр. См. в разделе [список атрибутов](../../../visual-basic/language-reference/statements/attribute-list.md).|  
|`accessmodifier`|Необязательный параметр. Ниже указаны доступные значения.<br /><br /> -   [Public](../../../visual-basic/language-reference/modifiers/public.md)<br />-   [защищенные](../../../visual-basic/language-reference/modifiers/protected.md)<br />-   [Friend](../../../visual-basic/language-reference/modifiers/friend.md)<br />-   [закрытый](../../../visual-basic/language-reference/modifiers/private.md)<br />-   [Protected Friend](../../language-reference/modifiers/protected-friend.md)<br />- [Частный защищенный](../../language-reference/modifiers/private-protected.md)<br/><br/> См. раздел [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).|  
|`Shadows`|Необязательный параметр. См. в разделе [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).|  
|`MustInherit`|Необязательный параметр. См. в разделе [MustInherit](../../../visual-basic/language-reference/modifiers/mustinherit.md).|  
|`NotInheritable`|Необязательный параметр. См. в разделе [NotInheritable](../../../visual-basic/language-reference/modifiers/notinheritable.md).|  
|`Partial`|Необязательный параметр. Указывает частичное определение класса. См. в разделе [частичного](../../../visual-basic/language-reference/modifiers/partial.md).|  
|`name`|Обязательный. Имя этого класса. См. раздел [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).|  
|`Of`|Необязательный параметр. Указывает, что это универсальный класс.|  
|`typelist`|Требуется при использовании [из](../../../visual-basic/language-reference/statements/of-clause.md) ключевое слово. Список параметров типа для этого класса. См. в разделе [введите список](../../../visual-basic/language-reference/statements/type-list.md).|  
|`Inherits`|Необязательный параметр. Указывает, что этот класс наследует члены другого класса. См. в разделе [оператор Inherits](../../../visual-basic/language-reference/statements/inherits-statement.md).|  
|`classname`|Требуется при использовании `Inherits` инструкции. Имя класса, из которого происходит данный класс.|  
|`Implements`|Необязательный параметр. Указывает, что этот класс реализует члены один или несколько интерфейсов. См. в разделе [реализует оператор](../../../visual-basic/language-reference/statements/implements-statement.md).|  
|`interfacenames`|Требуется при использовании `Implements` инструкции. Имена интерфейсов, реализуемых этого класса.|  
|`statements`|Необязательный параметр. Операторы, которые определяют члены этого класса.|  
|`End Class`|Обязательный. Завершает `Class` определения.|  
  
## <a name="remarks"></a>Примечания  
 Объект `Class` инструкция определяет новый тип данных. Объект *класс* является основным строительным блоком объектно ориентированное программирование (ООП). Дополнительные сведения см. в разделе [объекты и классы](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md).  
  
 Можно использовать `Class` только на уровне пространства имен или модуля. Это означает, что *контекст объявления* для класса должен быть исходный файл, пространство имен, класс, структура, модуль или интерфейс, а не может быть процедуры или блока. Дополнительные сведения см. в разделе [Контексты объявления и уровни доступа по умолчанию](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).  
  
 Каждый экземпляр класса имеет время существования, независимое от всех других экземпляров. Это время существования начинается, когда она была создана программой [оператор New](../../../visual-basic/language-reference/operators/new-operator.md) предложение или с помощью функции, такие как <xref:Microsoft.VisualBasic.Interaction.CreateObject%2A>. Оно заканчивается, когда заданы все переменные, указывает на экземпляр [ничего не](../../../visual-basic/language-reference/nothing.md) или экземпляров других классов.  
  
 По умолчанию для классов [Friend](../../../visual-basic/language-reference/modifiers/friend.md) доступа. Вы можете настроить уровни доступа с помощью модификаторов доступа. Дополнительные сведения см. в разделе [уровни в Visual Basic доступа](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
## <a name="rules"></a>Правила  
  
-   **Вложение.** Можно определить один класс в другом. Внешний класс называется *содержащий класс*, и внутренний класс называется *вложенных классов*.  
  
-   **Наследование.** Если класс использует [Inherits Statement](../../../visual-basic/language-reference/statements/inherits-statement.md), можно указать только один базовый класс или интерфейс. Класс не может наследовать от более чем одного элемента.  
  
     Класс не может наследовать от другого класса с более строгий уровень доступа. Например `Public` класс не может наследовать от `Friend` класса.  
  
     Класс не может наследовать от вложенного в него класса.  
  
-   **Реализация.** Если класс использует [оператор Implements](../../../visual-basic/language-reference/statements/implements-statement.md), должен реализовывать все члены каждого интерфейса, указываемое в `interfacenames`. Исключение составляет повторная реализация члена базового класса. Дополнительные сведения см. в разделе «Повторная реализация» в [реализует](../../../visual-basic/language-reference/statements/implements-clause.md).  
  
-   **Свойство по умолчанию.** Класс можно указать не более одного свойства, как его *свойство по умолчанию*. Дополнительные сведения см. в разделе [по умолчанию](../../../visual-basic/language-reference/modifiers/default.md).  
  
## <a name="behavior"></a>Поведение  
  
-   **Уровень доступа.** В классе можно объявить каждый член со своим собственным уровнем доступа. Члены класса по умолчанию [открытый](../../../visual-basic/language-reference/modifiers/public.md) получить доступ к, за исключением переменных и констант, по умолчанию для [частного](../../../visual-basic/language-reference/modifiers/private.md) доступа. Если класс более ограниченный доступ, чем один из его членов, уровень доступа класса имеет приоритет.  
  
-   **Область.** Класс является область действия его содержащего пространства имен, класса, структуры или модуля.  
  
     Область каждого члена класса является весь класс.  
  
     **Время существования.** Visual Basic не поддерживает статические классы. Функциональный эквивалент статического класса обеспечивается модуля. Дополнительные сведения см. в разделе [оператор Module](../../../visual-basic/language-reference/statements/module-statement.md).  
  
     Члены класса имеют время существования, в зависимости от того, как и где они объявлены. Дополнительные сведения см. в разделе [время существования в Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md).  
  
-   **Квалификации.** Код вне класса необходимо указать имя члена с именем этого класса.  
  
     Если код внутри вложенного класса делает внести неквалифицированную ссылку на элемент программирования, Visual Basic сначала выполняет поиск элемента во вложенном классе, затем в содержащий его класс, и т. д для внешнего содержащего элемента.  
  
## <a name="classes-and-modules"></a>Классы и модули  
 Эти элементы имеют много общего, но существуют также некоторые важные различия.  
  
-   **Терминология.** Предыдущие версии Visual Basic распознает два типа модулей: *модулей класса* (файлы CLS) и *стандартные модули* (файлы BAS). Текущая версия вызывает эти *классы* и *модули*, соответственно.  
  
-   **Общие члены.** Указать, можно ли член класса общим или членом экземпляра.  
  
-   **Ориентация на объекты.** Классы являются объектно ориентированными, но модули не будут. Можно создать один или несколько экземпляров класса. Дополнительные сведения см. в разделе [объекты и классы](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md).  
  
## <a name="example"></a>Пример  
 В следующем примере используется `Class` инструкции для определения класса и несколько членов.  
  
 [!code-vb[VbVbalrStatements#62](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#62)]  
  
## <a name="see-also"></a>См. также

- [Объекты и классы](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
- [Структуры и классы](../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md)
- [Оператор Interface](../../../visual-basic/language-reference/statements/interface-statement.md)
- [Оператор Module](../../../visual-basic/language-reference/statements/module-statement.md)
- [Оператор Property](../../../visual-basic/language-reference/statements/property-statement.md)
- [Время существования: Способ создания и уничтожения объектов](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)
- [Generic Types in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [Практическое руководство. Использование универсального класса](../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md)
