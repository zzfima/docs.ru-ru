---
title: Пространство имен или тип, указанный в Imports уровня проекта &#39; &lt;qualifiedelementname&gt;&#39; &#39; t содержат публичных членов или не найден
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc40057
- bc40057
helpviewer_keywords:
- BC40057
ms.assetid: 4ae3506e-2ebe-4ff3-995d-14ac60db5e9f
caps.latest.revision: 10
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 0d0a164562524af239b3b130f681dbc6eff23814
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="namespace-or-type-specified-in-the-project-level-imports-39ltqualifiedelementnamegt39-doesn39t-contain-any-public-member-or-cannot-be-found"></a>Пространство имен или тип, указанный в Imports уровня проекта &#39; &lt;qualifiedelementname&gt;&#39; &#39; t содержат публичных членов или не найден
Пространство имен или тип, указанный в операции импорта на уровне проекта\<qualifiedelementname > "не содержат публичных членов или не найден. Убедитесь, что пространство имен или тип определены и содержат хотя бы один открытый член. Убедитесь, что имя псевдонима не содержит других псевдонимов.  
  
 Указывает свойство импорта проекта, содержащий элемент, который не может быть найден или не определяет никакие `Public` члены.  
  
 Объект *содержащий элемент* может быть пространства имен, класса, структуры, модуля, интерфейса или перечисления. Элемент-контейнер содержит элементы, такие как переменные, процедуры или другие содержащие элементы.  
  
 Импорт предназначено для обеспечения кода для доступа к членам пространства имен или типа без их уточнения. Проект также может потребоваться добавить ссылку на пространство имен или тип. Дополнительные сведения см. в разделе «Импорт элементов с содержимым» в [ссылки на объявленные элементы](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).  
  
 Если компилятор не может найти указанный содержащий элемент, он не может разрешить ссылки, которые его используют. Если он находит элемент, но элемент не предоставляет никаких `Public` членов, то ни одна ссылка не может быть успешно. В любом случае нет смысла в импорте элемента.  
  
 Вы используете **конструктора проектов** указывать элементы для импорта. Используйте **импортированные пространства имен** раздел **ссылки** страницы. Можно получить **конструктора проектов** , дважды щелкнув **Мой проект** значок в **обозревателе решений**.  
  
 **Идентификатор ошибки:** BC40057  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1.  Откройте **конструктора проектов** и переключитесь в **ссылки** страницы.  
  
2.  В **импортированные пространства имен** убедитесь, что содержащий его элемент доступен из проекта.  
  
3.  Убедитесь, что содержащий элемент предоставляет хотя бы один `Public` член.  
  
## <a name="see-also"></a>См. также  
 [Страница "Ссылки" в конструкторе проектов (Visual Basic)](/visualstudio/ide/reference/references-page-project-designer-visual-basic)  
 [Управление свойствами проектов и решений](/visualstudio/ide/managing-project-and-solution-properties)  
 [Public](../../../visual-basic/language-reference/modifiers/public.md)  
 [Пространства имен в Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md)  
 [Ссылки на объявленные элементы](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
