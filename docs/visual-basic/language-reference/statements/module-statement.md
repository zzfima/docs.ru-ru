---
title: "Оператор Module"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
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
caps.latest.revision: "24"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 92cdcd1919f21243118108da3bc382ea5d954130
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="module-statement"></a>Оператор Module
Объявляет имя модуля и представляет определения переменных, свойств, событий и процедур, которые включены в модуль.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
[ <attributelist> ] [ accessmodifier ]  Module name  
    [ statements ]  
End Module  
```  
  
## <a name="parts"></a>Части  
 `attributelist`  
 Необязательно. В разделе [список атрибутов](../../../visual-basic/language-reference/statements/attribute-list.md).  
  
 `accessmodifier`  
 Необязательно. Ниже указаны доступные значения.  
  
-   [Public](../../../visual-basic/language-reference/modifiers/public.md)  
  
-   [Friend](../../../visual-basic/language-reference/modifiers/friend.md)  
  
 В разделе [уровни в Visual Basic доступа](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
 `name`  
 Обязательный. Имя этого модуля. В разделе [имена объявленных элементов](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).  
  
 `statements`  
 Необязательно. Операторы, которые определяют переменные, свойства, события, процедуры и вложенные типы этого модуля.  
  
 `End Module`  
 Завершает `Module` определения.  
  
## <a name="remarks"></a>Примечания  
 Объект `Module` инструкция определяет ссылочный тип, доступный всего пространства имен. Объект *модуль* (иногда называется *стандартного модуля*) похож на класс, но некоторые важные различия. Каждый модуль имеет ровно один экземпляр и не должны быть созданы или присваивается переменной. Модули не поддерживают наследование и не реализуют интерфейсы. Обратите внимание, что модуль не *типа* в том смысле, что класс или структура, нельзя объявлять элемент программирования с типом данных модуля.  
  
 Можно использовать `Module` только на уровне пространства имен. Это означает *контекст объявления* для модуля должен быть исходным файлом или пространством имен и не может быть класс, структура, модуль, интерфейса, процедуры или блока. Нельзя вкладывать модуль в другой модуль или в любой тип. Дополнительные сведения см. в разделе [Контексты объявления и уровни доступа по умолчанию](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).  
  
 Модуль имеет то же время существования, в ходе выполнения программы. Так как все его члены являются `Shared`, они также имеют время жизни, равное программы.  
  
 По умолчанию модули [Friend](../../../visual-basic/language-reference/modifiers/friend.md) доступа. Вы можете настроить уровни доступа с помощью модификаторов доступа. Дополнительные сведения см. в разделе [уровни в Visual Basic доступа](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
 Все элементы модуля являются неявно `Shared`.  
  
## <a name="classes-and-modules"></a>Классы и модули  
 Эти элементы имеют много общего, но существуют некоторые важные различия.  
  
-   **Терминология.** Предыдущие версии Visual Basic распознает два типа модулей: *модулей класса* (файлы CLS) и *стандартные модули* (файлы BAS). Текущая версия вызывает эти *классы* и *модули*соответственно.  
  
-   **Общие члены.** Можно управлять ли член класса общим или членом экземпляра.  
  
-   **Ориентация на объекты.** Классы являются объектно ориентированного, но модули не будут. Поэтому только классы могут быть созданы как объекты. Дополнительные сведения см. в разделе [объекты и классы](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md).  
  
## <a name="rules"></a>Правила  
  
-   **Модификаторы.** Все элементы модуля являются неявно [Shared](../../../visual-basic/language-reference/modifiers/shared.md). Нельзя использовать `Shared` ключевого слова при объявлении члена и невозможно изменить состояние любого члена общего доступа.  
  
-   **Наследование.** Модуль не может наследовать от типа, отличного от <xref:System.Object>, из всех модулей, которые наследуют. В частности один модуль не может наследовать от другого.  
  
     Нельзя использовать [инструкцию наследует](../../../visual-basic/language-reference/statements/inherits-statement.md) в определение модуля, даже для указания <xref:System.Object>.  
  
-   **Свойство по умолчанию.** В модуле нельзя определять свойства по умолчанию. Дополнительные сведения см. в разделе [по умолчанию](../../../visual-basic/language-reference/modifiers/default.md).  
  
## <a name="behavior"></a>Поведение  
  
-   **Уровень доступа.** Внутри модуля можно объявить каждый член со своим собственным уровнем доступа. Элементы модуля по умолчанию [открытый](../../../visual-basic/language-reference/modifiers/public.md) доступ к, за исключением переменных и констант, который по умолчанию для [закрытый](../../../visual-basic/language-reference/modifiers/private.md) доступа. Если модуль более ограниченный доступ, чем один из его членов, уровень доступа указанный модуль имеет приоритет.  
  
-   **Область действия.** Модуль — область действия пространства имен.  
  
     Область для каждого элемента модуля является весь модуль. Обратите внимание, что все элементы претерпевают *введите рекламной акции*, что приводит к повышению до пространства имен, содержащего модуль их области. Дополнительные сведения см. в разделе [повышение типа](../../../visual-basic/programming-guide/language-features/declared-elements/type-promotion.md).  
  
-   **Квалификация.** В проекте может быть несколько модулей, и можно объявить члены с тем же именем в два или несколько модулей. Тем не менее если ссылка находится за пределами этого модуля необходимо предварять любая ссылка на элемент с именем соответствующего модуля. Дополнительные сведения см. в разделе [ссылки на объявленные элементы](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).  
  
## <a name="example"></a>Пример  
 [!code-vb[VbVbalrStatements#69](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/module-statement_1.vb)]  
  
## <a name="see-also"></a>См. также  
 [Оператор Class](../../../visual-basic/language-reference/statements/class-statement.md)  
 [Оператор Namespace](../../../visual-basic/language-reference/statements/namespace-statement.md)  
 [Оператор Structure](../../../visual-basic/language-reference/statements/structure-statement.md)  
 [Оператор Interface](../../../visual-basic/language-reference/statements/interface-statement.md)  
 [Оператор Property](../../../visual-basic/language-reference/statements/property-statement.md)  
 [Повышение типа](../../../visual-basic/programming-guide/language-features/declared-elements/type-promotion.md)
