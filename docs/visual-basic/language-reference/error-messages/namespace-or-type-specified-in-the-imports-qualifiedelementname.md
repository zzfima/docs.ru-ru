---
title: Пространство имен или тип, указанный в Imports &#39; &lt;qualifiedelementname&gt;&#39; &#39; t содержат публичных членов или не найден
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc40056
- vbc40056
helpviewer_keywords:
- BC40056
ms.assetid: b59f5754-444f-4378-9272-9678b437e84a
caps.latest.revision: 8
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 49cd9fa5d5182b2cf2d7fc4623bc8e9aa02bf85e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="namespace-or-type-specified-in-the-imports-39ltqualifiedelementnamegt39-doesn39t-contain-any-public-member-or-cannot-be-found"></a>Пространство имен или тип, указанный в Imports &#39; &lt;qualifiedelementname&gt;&#39; &#39; t содержат публичных членов или не найден
Пространство имен или тип, указанный в Imports\<qualifiedelementname > "не содержат публичных членов или не найден. Убедитесь, что пространство имен или тип определены и содержат хотя бы один открытый член. Убедитесь, что имя псевдонима не содержит других псевдонимов.  
  
 `Imports` Инструкция указывает содержащий элемент, который не может быть найден или не определяет никакие `Public` члены.  
  
 Объект *содержащий элемент* может быть пространства имен, класса, структуры, модуля, интерфейса или перечисления. Элемент-контейнер содержит элементы, такие как переменные, процедуры или другие содержащие элементы.  
  
 Импорт предназначено для обеспечения кода для доступа к членам пространства имен или типа без их уточнения. Проект также может потребоваться добавить ссылку на пространство имен или тип. Дополнительные сведения см. в разделе «Импорт элементов с содержимым» в [ссылки на объявленные элементы](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).  
  
 Если компилятор не может найти указанный содержащий элемент, он не может разрешить ссылки, которые его используют. Если он находит элемент, но элемент не предоставляет никаких `Public` членов, то ни одна ссылка не может быть успешно. В любом случае нет смысла в импорте элемента.  
  
 Имейте в виду, что если импортировать содержащий элемент и присвоить псевдоним импорта, затем нельзя использовать этот псевдоним импорта для импорта другого элемента. Следующий код создает ошибку компилятора.  
  
 `Imports`   `winfrm`   `= System.Windows.Forms`  
  
 `' The following statement is`   `INVALID`   `because it reuses an import alias.`  
  
 `Imports behav =`   `winfrm`  `.Design.Behavior`  
  
 **Идентификатор ошибки:** BC40056  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1.  Убедитесь, что содержащий его элемент доступен из проекта.  
  
2.  Убедитесь, что спецификация содержащего его элемента содержит псевдоним импорта из другого импорта.  
  
3.  Убедитесь, что содержащий элемент предоставляет хотя бы один `Public` член.  
  
## <a name="see-also"></a>См. также  
 [Оператор Imports (пространство имен и тип .NET)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)  
 [Оператор Namespace](../../../visual-basic/language-reference/statements/namespace-statement.md)  
 [Public](../../../visual-basic/language-reference/modifiers/public.md)  
 [Пространства имен в Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md)  
 [Ссылки на объявленные элементы](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
