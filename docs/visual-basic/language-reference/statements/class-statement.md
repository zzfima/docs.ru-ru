---
title: Оператор Class
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
ms.openlocfilehash: 3cb276f134e90ce3b3009234eb980d89477e0d09
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74354149"
---
# <a name="class-statement-visual-basic"></a>Оператор Class (Visual Basic)
Объявляет имя класса и вводит определение переменных, свойств, событий и процедур, содержащихся в классе.  
  
## <a name="syntax"></a>Синтаксис  
  
```vb  
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
|`attributelist`|Необязательный элемент. См. [список атрибутов](../../../visual-basic/language-reference/statements/attribute-list.md).|  
|`accessmodifier`|Необязательный элемент. Ниже указаны доступные значения.<br /><br /> -   [Public](../../../visual-basic/language-reference/modifiers/public.md)<br />[защищенный](../../../visual-basic/language-reference/modifiers/protected.md) -   <br />-   [Friend](../../../visual-basic/language-reference/modifiers/friend.md)<br />-   [закрытый](../../../visual-basic/language-reference/modifiers/private.md)<br />-   [защищенный дружественный](../../language-reference/modifiers/protected-friend.md)<br />- [частный защищенный](../../language-reference/modifiers/private-protected.md)<br/><br/> См. раздел [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).|  
|`Shadows`|Необязательный элемент. См. раздел [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).|  
|`MustInherit`|Необязательный элемент. См. раздел [MustInherit](../../../visual-basic/language-reference/modifiers/mustinherit.md).|  
|`NotInheritable`|Необязательный элемент. См. [NotInheritable](../../../visual-basic/language-reference/modifiers/notinheritable.md).|  
|`Partial`|Необязательный элемент. Указывает на частичное определение класса. См. раздел [partial](../../../visual-basic/language-reference/modifiers/partial.md).|  
|`name`|Обязательно. Имя этого класса. См. раздел [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).|  
|`Of`|Необязательный элемент. Указывает, что это универсальный класс.|  
|`typelist`|Требуется, если используется ключевое слово [of](../../../visual-basic/language-reference/statements/of-clause.md) . Список параметров типа для этого класса. См. [список типов](../../../visual-basic/language-reference/statements/type-list.md).|  
|`Inherits`|Необязательный элемент. Указывает, что этот класс наследует члены другого класса. См. раздел [оператор Inherits](../../../visual-basic/language-reference/statements/inherits-statement.md).|  
|`classname`|Требуется, если используется оператор `Inherits`. Имя класса, от которого наследует этот класс.|  
|`Implements`|Необязательный элемент. Указывает, что этот класс реализует члены одного или нескольких интерфейсов. См. [инструкцию Implements](../../../visual-basic/language-reference/statements/implements-statement.md).|  
|`interfacenames`|Требуется, если используется оператор `Implements`. Имена интерфейсов, реализуемых этим классом.|  
|`statements`|Необязательный элемент. Инструкции, которые определяют элементы этого класса.|  
|`End Class`|Обязательно. Завершает определение `Class`.|  
  
## <a name="remarks"></a>Примечания  
 Оператор `Class` определяет новый тип данных. *Класс* является фундаментальным стандартным блоком объектно-ориентированного программирования (ООП). Дополнительные сведения см. в разделе [объекты и классы](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md).  
  
 `Class` можно использовать только на уровне пространства имен или модуля. Это означает, что *контекст объявления* для класса должен быть исходным файлом, пространством имен, классом, структурой, модулем или интерфейсом и не может быть процедурой или блоком. Дополнительные сведения см. в разделе [Контексты объявления и уровни доступа по умолчанию](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).  
  
 Каждый экземпляр класса имеет время существования, не зависящее от всех остальных экземпляров. Это время жизни начинается, когда оно создается с помощью [нового предложения оператора](../../../visual-basic/language-reference/operators/new-operator.md) или функции, например <xref:Microsoft.VisualBasic.Interaction.CreateObject%2A>. Он завершается, когда всем переменным, указывающим на экземпляр, присвоено значение [Nothing](../../../visual-basic/language-reference/nothing.md) или экземпляры других классов.  
  
 Классы по умолчанию имеют доступ [Friend](../../../visual-basic/language-reference/modifiers/friend.md) . Уровни доступа можно изменить с помощью модификаторов доступа. Дополнительные сведения см. [в разделе уровни доступа в Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
## <a name="rules"></a>Правила  
  
- **Вложенности.** Можно определить один класс в другом. Внешний класс называется *содержащим классом*, а внутренний класс называется *вложенным классом*.  
  
- **Наследование.** Если класс использует [инструкцию Inherits](../../../visual-basic/language-reference/statements/inherits-statement.md), можно указать только один базовый класс или интерфейс. Класс не может наследовать более чем от одного элемента.  
  
     Класс не может наследовать от другого класса с более узким уровнем доступа. Например, класс `Public` не может наследовать от класса `Friend`.  
  
     Класс не может наследовать от класса, вложенного в него.  
  
- **Реализации.** Если класс использует [оператор Implements](../../../visual-basic/language-reference/statements/implements-statement.md), необходимо реализовать каждый элемент, определенный каждым интерфейсом, указанным в `interfacenames`. Исключением из этого является перереализация члена базового класса. Дополнительные сведения см. в разделе "перереализация" раздела [Implements](../../../visual-basic/language-reference/statements/implements-clause.md).  
  
- **Свойство по умолчанию.** Класс может указывать не более одного свойства в качестве *свойства по умолчанию*. Дополнительные сведения см. в разделе [Default](../../../visual-basic/language-reference/modifiers/default.md).  
  
## <a name="behavior"></a>Поведение  
  
- **Уровень доступа.** Внутри класса можно объявить каждый элемент с собственным уровнем доступа. Члены класса по умолчанию имеют [открытый](../../../visual-basic/language-reference/modifiers/public.md) доступ, за исключением переменных и констант, которые по умолчанию имеют [частный](../../../visual-basic/language-reference/modifiers/private.md) доступ. Если класс имеет более ограниченный доступ, чем один из его членов, приоритет имеет уровень доступа к классу.  
  
- **Которых.** Класс находится в области по всему его содержащимся пространству имен, классу, структуре или модулю.  
  
     Областью действия каждого члена класса является весь класс.  
  
     **Контролиру.** Visual Basic не поддерживает статические классы. Функциональный эквивалент статического класса предоставляется модулем. Дополнительные сведения см. в разделе [оператор Module](../../../visual-basic/language-reference/statements/module-statement.md).  
  
     У членов класса есть время существования в зависимости от того, как и где они объявляются. Дополнительные сведения см. [в разделе время существования в Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md).  
  
- **Квалификацию.** Код за пределами класса должен уточнять имя члена именем этого класса.  
  
     Если код внутри вложенного класса делает неквалифицированную ссылку на программный элемент, Visual Basic ищет элемент сначала во вложенном классе, затем в его содержащем классе и так далее в самом внешнем содержащем элементе.  
  
## <a name="classes-and-modules"></a>Классы и модули  
 У этих элементов много сходства, но есть и некоторые важные отличия.  
  
- **Терминология.** В предыдущих версиях Visual Basic распознаются два типа модулей: *модули классов* (CLS-файлы) и *стандартные модули* (файлы. BAS). Текущая версия вызывает эти *классы* и *модули*соответственно.  
  
- **Общие члены.** Можно контролировать, является ли член класса общим или членом экземпляра.  
  
- **Объектная ориентация.** Классы являются объектно-ориентированными, но модули — нет. Можно создать один или несколько экземпляров класса. Дополнительные сведения см. в разделе [объекты и классы](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md).  
  
## <a name="example"></a>Пример  
 В следующем примере оператор `Class` используется для определения класса и нескольких элементов.  
  
 [!code-vb[VbVbalrStatements#62](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#62)]  
  
## <a name="see-also"></a>См. также

- [Объекты и классы](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
- [Структуры и классы](../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md)
- [Оператор Interface](../../../visual-basic/language-reference/statements/interface-statement.md)
- [Оператор Module](../../../visual-basic/language-reference/statements/module-statement.md)
- [Оператор Property](../../../visual-basic/language-reference/statements/property-statement.md)
- [Время существования. Создание и уничтожение объектов](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)
- [Generic Types in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [Практическое руководство. Использование универсального класса](../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md)
