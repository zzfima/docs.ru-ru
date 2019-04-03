---
title: <expression> нельзя использовать в качестве ограничения типа
ms.date: 07/20/2015
f1_keywords:
- bc32061
- vbc32061
helpviewer_keywords:
- BC32061
ms.assetid: b17821b7-fa14-4397-a211-6e2a14079f09
ms.openlocfilehash: 8dbf510d7c6ee80e2dcd2f9d2552bc870413cbab
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2019
ms.locfileid: "58838109"
---
# <a name="expression-cannot-be-used-as-a-type-constraint"></a>"\<выражение >" не может использоваться в качестве ограничения типа
Список ограничений включает выражение, которое не представляет допустимое ограничение для параметра типа.  
  
 Список ограничений назначает требования на тип аргумента, передаваемого параметру типа. Вы можете указать приведенные ниже требования в любой комбинации.  
  
-   Аргумент типа должен реализовывать один или несколько интерфейсов  
  
-   Аргумент типа должен наследовать не более чем от одного класса  
  
-   Аргумент типа должен предоставлять конструктор без параметров, к которому создающий код может получить доступ (включая ограничение `New` ).  
  
 Если не включать определенный класс или интерфейс в список ограничений, то можно наложить более общее требование, указав одно из приведенных ниже ограничений.  
  
-   Аргумент типа должен быть типом значения (включая ограничение `Structure` ).  
  
-   Аргумент типа должен быть ссылочным типом (включая ограничение `Class` ).  
  
 Нельзя указывать оба ограничения, `Structure` и `Class` , для одного и того же параметра типа, а также нельзя указывать какое-либо из них более одного раза.  
  
 **Идентификатор ошибки:** BC32061  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Проверьте правильность написания выражения и его элементов.  
  
-   Если выражение не соответствует требованиям предыдущего списка, удалите его из списка ограничений.  
  
-   Если выражение ссылается на интерфейс или класс, убедитесь, что у компилятора есть доступ к этому интерфейсу или классу. Возможно, вам потребуется проверить его имя и добавить ссылку в проект. Дополнительные сведения см. в разделе «Ссылки на проекты» в [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).  
  
## <a name="see-also"></a>См. также

- [Generic Types in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [Value Types and Reference Types](../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
- [Ссылки на объявленные элементы](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
