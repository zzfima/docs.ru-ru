---
title: Оператор Module
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
ms.openlocfilehash: 56fc4f9383f1fc4779358ef18a4e5c611d897eda
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348021"
---
# <a name="module-statement"></a>Оператор Module

Объявляет имя модуля и вводит определение переменных, свойств, событий и процедур, которые входят в модуль.

## <a name="syntax"></a>Синтаксис

```vb
[ <attributelist> ] [ accessmodifier ]  Module name
    [ statements ]
End Module
```

## <a name="parts"></a>Части

`attributelist`  
Необязательный элемент. См. [список атрибутов](../../../visual-basic/language-reference/statements/attribute-list.md).

`accessmodifier`  
Необязательный элемент. Ниже указаны доступные значения.

- [Public](../../../visual-basic/language-reference/modifiers/public.md)

- [Friend](../../../visual-basic/language-reference/modifiers/friend.md)

См. раздел [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).

`name`  
Обязательно. Имя этого модуля. См. раздел [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).

`statements`  
Необязательный элемент. Инструкции, которые определяют переменные, свойства, события, процедуры и вложенные типы этого модуля.

`End Module`  
Завершает определение `Module`.

## <a name="remarks"></a>Примечания

Оператор `Module` определяет ссылочный тип, доступный в пределах его пространства имен. *Модуль* (иногда называемый *стандартным модулем*) аналогичен классу, но с некоторыми важными различиями. Каждый модуль имеет ровно один экземпляр и не требует создания или назначения переменной. Модули не поддерживают наследование или реализуют интерфейсы. Обратите внимание, что модуль не является *типом* в том смысле, что класс или структура — нельзя объявить программный элемент для типа данных модуля.

`Module` можно использовать только на уровне пространства имен. Это означает, что *контекст объявления* для модуля должен быть исходным файлом или пространством имен и не может быть классом, структурой, модулем, интерфейсом, процедурой или блоком. Модуль нельзя вложить в другой модуль или в любой тип. Дополнительные сведения см. в разделе [Контексты объявления и уровни доступа по умолчанию](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).

Модуль имеет то же время, что и программа. Поскольку все члены `Shared`, они также имеют время существования, равное значению программы.

Модули по умолчанию имеют доступ [Friend](../../../visual-basic/language-reference/modifiers/friend.md) . Уровни доступа можно изменить с помощью модификаторов доступа. Дополнительные сведения см. [в разделе уровни доступа в Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).

Все члены модуля являются неявными `Shared`.

## <a name="classes-and-modules"></a>Классы и модули

У этих элементов много сходства, но есть и некоторые важные отличия.

- **Терминология.** В предыдущих версиях Visual Basic распознаются два типа модулей: *модули классов* (CLS-файлы) и *стандартные модули* (файлы. BAS). Текущая версия вызывает эти *классы* и *модули*соответственно.

- **Общие члены.** Можно контролировать, является ли член класса общим или членом экземпляра.

- **Объектная ориентация.** Классы являются объектно-ориентированными, но модули — нет. Таким образом, можно создавать экземпляры только классов в виде объектов. Дополнительные сведения см. в разделе [объекты и классы](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md).

## <a name="rules"></a>Правила

- **Модификаторы.** Все члены модуля неявно являются [общими](../../../visual-basic/language-reference/modifiers/shared.md). Нельзя использовать ключевое слово `Shared` при объявлении элемента, и нельзя изменить общее состояние любого члена.

- **Наследование.** Модуль не может наследовать от любого типа, кроме <xref:System.Object>, от которого наследуются все модули. В частности, один модуль не может наследовать от другого.

  Нельзя использовать [инструкцию Inherits](../../../visual-basic/language-reference/statements/inherits-statement.md) в определении модуля даже для указания <xref:System.Object>.

- **Свойство по умолчанию.** В модуле нельзя определить свойства по умолчанию. Дополнительные сведения см. в разделе [Default](../../../visual-basic/language-reference/modifiers/default.md).

## <a name="behavior"></a>Поведение

- **Уровень доступа.** Внутри модуля можно объявить каждый элемент с собственным уровнем доступа. Члены модуля по умолчанию имеют [открытый](../../../visual-basic/language-reference/modifiers/public.md) доступ, за исключением переменных и констант, которые по умолчанию имеют [частный](../../../visual-basic/language-reference/modifiers/private.md) доступ. Если модуль имеет более ограниченный доступ, чем один из его членов, приоритет имеет указанный уровень доступа к модулю.

- **Которых.** Модуль находится в пределах пространства имен.

  Областью действия каждого члена модуля является весь модуль. Обратите внимание, что все члены проводят *продвижение по типам*, что приводит к повышению уровня их области до пространства имен, содержащего модуль. Дополнительные сведения см. в разделе [повышение типа](../../../visual-basic/programming-guide/language-features/declared-elements/type-promotion.md).

- **Квалификацию.** В проекте может быть несколько модулей, и члены с одинаковыми именами можно объявить в двух или более модулях. Однако необходимо определить любую ссылку на такой элемент с соответствующим именем модуля, если ссылка находится за пределами этого модуля. Для получения дополнительной информации см. [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).

## <a name="example"></a>Пример

[!code-vb[VbVbalrStatements#69](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#69)]

## <a name="see-also"></a>См. также

- [Оператор Class](../../../visual-basic/language-reference/statements/class-statement.md)
- [Оператор Namespace](../../../visual-basic/language-reference/statements/namespace-statement.md)
- [Оператор Structure](../../../visual-basic/language-reference/statements/structure-statement.md)
- [Оператор Interface](../../../visual-basic/language-reference/statements/interface-statement.md)
- [Оператор Property](../../../visual-basic/language-reference/statements/property-statement.md)
- [Повышение типа](../../../visual-basic/programming-guide/language-features/declared-elements/type-promotion.md)
