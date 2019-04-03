---
title: Оператор модуля (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- Module
- vb.Module
helpviewer_keywords:
- modules, classes
- modules
- Module statement [Visual Basic]
- modules, declaring
- standard modules
- classes [Visual Basic], vs. modules
- declarations [Visual Basic], modules
ms.assetid: a1243afc-14a5-45df-95d5-51118aeac362
ms.openlocfilehash: f546498e5282bcf58d07a06968bb4303e4e6d7b9
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2019
ms.locfileid: "58838148"
---
# <a name="module-statement"></a>Оператор Module
Объявляет имя модуля и вводит определение переменных, свойств, событий и процедур, которые включены в модуль.  
  
## <a name="syntax"></a>Синтаксис  
  
```vb 
[ <attributelist> ] [ accessmodifier ]  Module name  
    [ statements ]  
End Module  
```  
  
## <a name="parts"></a>Части  
 `attributelist`  
 Необязательный параметр. См. в разделе [список атрибутов](../../../visual-basic/language-reference/statements/attribute-list.md).  
  
 `accessmodifier`  
 Необязательный параметр. Ниже указаны доступные значения.  
  
-   [Public](../../../visual-basic/language-reference/modifiers/public.md)  
  
-   [Friend](../../../visual-basic/language-reference/modifiers/friend.md)  
  
 См. раздел [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
 `name`  
 Обязательный. Имя этого модуля. См. раздел [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).  
  
 `statements`  
 Необязательный параметр. Операторы, которые определяют переменные, свойства, события, процедуры и вложенные типы этого модуля.  
  
 `End Module`  
 Завершает `Module` определения.  
  
## <a name="remarks"></a>Примечания  
 Объект `Module` инструкция определяет ссылочный тип, доступный на протяжении всего его пространство имен. Объект *модуль* (иногда называют *стандартного модуля*) похож на класс, но некоторые важные различия. Каждый модуль имеет только один экземпляр и не должны быть созданы и присваивается переменной. Модули не поддерживают наследование и не реализуют интерфейсы. Обратите внимание, что модуль не является *тип* в том смысле, что класс или структура, нельзя объявлять программный элемент как имеющие тип данных модуля.  
  
 Можно использовать `Module` только на уровне пространства имен. Это означает, что *контекст объявления* для модуля должен быть исходным файлом или пространством имен и не может быть класс, структура, модуль, интерфейс, процедуры или блока. Нельзя вкладывать модуль в другом модуле, или внутри любого типа. Дополнительные сведения см. в разделе [Контексты объявления и уровни доступа по умолчанию](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).  
  
 Модуль имеет одинаковое время существования программы. Так как все его члены являются `Shared`, они также имеют время существования, равный программы.  
  
 По умолчанию модули [Friend](../../../visual-basic/language-reference/modifiers/friend.md) доступа. Вы можете настроить уровни доступа с помощью модификаторов доступа. Дополнительные сведения см. в разделе [уровни в Visual Basic доступа](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
 Все члены модуля являются неявно `Shared`.  
  
## <a name="classes-and-modules"></a>Классы и модули  
 Эти элементы имеют много общего, но существуют также некоторые важные различия.  
  
-   **Терминология.** Предыдущие версии Visual Basic распознает два типа модулей: *модулей класса* (файлы CLS) и *стандартные модули* (файлы BAS). Текущая версия вызывает эти *классы* и *модули*, соответственно.  
  
-   **Общие члены.** Указать, можно ли член класса общим или членом экземпляра.  
  
-   **Ориентация на объекты.** Классы являются объектно ориентированными, но модули не будут. Поэтому только классы могут быть созданы как объекты. Дополнительные сведения см. в разделе [объекты и классы](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md).  
  
## <a name="rules"></a>Правила  
  
-   **Модификаторы.** Все элементы модуля являются неявно [Shared](../../../visual-basic/language-reference/modifiers/shared.md). Нельзя использовать `Shared` ключевое слово при объявлении члена, а также невозможно изменить состояние любого члена общего доступа.  
  
-   **Наследование.** Модуль не может наследовать от любого типа, отличного от <xref:System.Object>, из всех модулей, которые наследуют. В частности один модуль не может наследовать от другого.  
  
     Нельзя использовать [Inherits Statement](../../../visual-basic/language-reference/statements/inherits-statement.md) в определении модуля, даже для указания <xref:System.Object>.  
  
-   **Свойство по умолчанию.** Не удается определить свойства по умолчанию в модуле. Дополнительные сведения см. в разделе [по умолчанию](../../../visual-basic/language-reference/modifiers/default.md).  
  
## <a name="behavior"></a>Поведение  
  
-   **Уровень доступа.** Внутри модуля можно объявить каждый член со своим собственным уровнем доступа. Элементы модуля по умолчанию [открытый](../../../visual-basic/language-reference/modifiers/public.md) получить доступ к, за исключением переменных и констант, по умолчанию для [частного](../../../visual-basic/language-reference/modifiers/private.md) доступа. Если модуль более ограниченный доступ, чем один из его членов, уровень доступа указанный модуль имеет приоритет.  
  
-   **Область.** Модуль — область действия его пространство имен.  
  
     Областью для каждого элемента модуля является весь модуль. Обратите внимание, что все элементы претерпевают *повышение типа*, который приводит к их области, повышаются до пространства имен, содержащего модуль. Дополнительные сведения см. в разделе [повышение типа](../../../visual-basic/programming-guide/language-features/declared-elements/type-promotion.md).  
  
-   **Квалификации.** Может быть несколько модулей в проекте, и можно объявить члены с тем же именем в два или несколько модулей. Тем не менее любая ссылка на элемент с именем соответствующего модуля необходимо уточнить, если ссылка находится за пределами этого модуля. Для получения дополнительной информации см. [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).  
  
## <a name="example"></a>Пример  
 [!code-vb[VbVbalrStatements#69](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#69)]  
  
## <a name="see-also"></a>См. также

- [Оператор Class](../../../visual-basic/language-reference/statements/class-statement.md)
- [Оператор Namespace](../../../visual-basic/language-reference/statements/namespace-statement.md)
- [Оператор Structure](../../../visual-basic/language-reference/statements/structure-statement.md)
- [Оператор Interface](../../../visual-basic/language-reference/statements/interface-statement.md)
- [Оператор Property](../../../visual-basic/language-reference/statements/property-statement.md)
- [Повышение типа](../../../visual-basic/programming-guide/language-features/declared-elements/type-promotion.md)
