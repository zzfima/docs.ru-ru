---
title: Пространство имен или тип, указанный в Imports <qualifiedelementname>, не содержит общих членов или не найден
ms.date: 07/20/2015
f1_keywords:
- bc40056
- vbc40056
helpviewer_keywords:
- BC40056
ms.assetid: b59f5754-444f-4378-9272-9678b437e84a
ms.openlocfilehash: d19a769b33b3b63b7f431b73841f49632e41f9e6
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55288279"
---
# <a name="namespace-or-type-specified-in-the-imports-qualifiedelementname-doesnt-contain-any-public-member-or-cannot-be-found"></a>Пространство имен или тип, указанный в Imports\<полное_имя_элемента > "не содержат открытые члены или не найден
Пространство имен или тип, указанный в Imports\<полное_имя_элемента > "не содержат открытые члены или не найден. Убедитесь, что пространство имен или тип определены и содержат хотя бы один открытый член. Убедитесь, что псевдоним не может содержать другие псевдонимы.  
  
 `Imports` Инструкция указывает содержащий элемент, который не может быть найден или не определяет никакие `Public` членов.  
  
 Объект *содержащий элемент* может быть пространства имен, класса, структуры, модуля, интерфейса или перечисления. Содержащий элемент содержит элементы, такие как переменные, процедуры или другие содержащие элементы.  
  
 Импорт нужен, чтобы код для доступа к членам пространства имен или типа без уточнения их. Проект также может потребоваться добавить ссылку на пространство имен или тип. Дополнительные сведения см. в разделе «Импорт элементов с содержимым» в [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).  
  
 Если компилятор не может найти указанный содержащий элемент, он не может разрешить ссылки, которые ее используют. Если он находит элемент, но элемент не предоставляет никаких `Public` членов, то ни одна ссылка не может быть успешной. В любом случае не имеет смысла в импорте элемента.  
  
 Имейте в виду, что если импортировать элемент и назначить псевдоним импорта, то нельзя использовать этот псевдоним импорта для импорта другого элемента. Следующий код приводит к ошибке компилятора.  
  
 `Imports`   `winfrm`   `= System.Windows.Forms`  
  
 `' The following statement is`   `INVALID`   `because it reuses an import alias.`  
  
 `Imports behav =`   `winfrm`  `.Design.Behavior`  
  
 **Идентификатор ошибки:** BC40056  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1.  Убедитесь, что содержащий элемент доступен из проекта.  
  
2.  Убедитесь, что спецификация содержащего его элемента содержит псевдоним импорта из другой операции импорта.  
  
3.  Убедитесь, что элемент, имеющий предоставляет по крайней мере `Public` член.  
  
## <a name="see-also"></a>См. также
- [Оператор Imports (пространство имен и тип .NET)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)
- [Оператор Namespace](../../../visual-basic/language-reference/statements/namespace-statement.md)
- [Public](../../../visual-basic/language-reference/modifiers/public.md)
- [Пространства имен в Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md)
- [Ссылки на объявленные элементы](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
