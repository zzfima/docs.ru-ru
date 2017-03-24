---
title: "Пространство имен или тип, указанный в Imports на уровне проекта&lt;qualifiedelementname&gt;&quot;не содержит никаких общих членов или не удается найти | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc40057
- bc40057
dev_langs:
- VB
helpviewer_keywords:
- BC40057
ms.assetid: 4ae3506e-2ebe-4ff3-995d-14ac60db5e9f
caps.latest.revision: 10
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 5dae6f92f573a57d0974c860500bc7420f55a94f
ms.lasthandoff: 03/13/2017

---
# <a name="namespace-or-type-specified-in-the-project-level-imports-39ltqualifiedelementnamegt39-doesn39t-contain-any-public-member-or-cannot-be-found"></a>Пространство имен или тип, указанный в Imports на уровне проекта&lt;qualifiedelementname&gt;"не содержит никаких общих членов или не найден
Пространство имен или тип, указанный в Imports на уровне проекта\<qualifiedelementname настроек "не содержит никаких общих членов или не найден. Убедитесь, что пространство имен или тип определен и содержит хотя бы один открытый член. Убедитесь, что имя псевдонима не содержит других псевдонимов.  
  
 Свойство импорта для проекта указывает содержащий элемент, который не может быть найден или не определяет никаких `Public` члены.  
  
 Объект *содержащий элемент* может быть пространства имен, класса, структуры, модуля, интерфейса или перечисления. Содержащий элемент содержит элементы, такие как переменные, процедуры или другие содержащие элементы.  
  
 Импорт нужен, чтобы код для доступа к членам пространства имен или типа без их уточнения. Проект может также потребоваться добавить ссылку на пространство имен или тип. Дополнительные сведения см. в разделе «Импорт содержащих элементов» в [ссылки на объявленные элементы](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).  
  
 Если компилятор не может найти указанный содержащий элемент, он не может разрешить ссылки, которые его используют. Если он находит элемент, но элемент не предоставляет никаких `Public` членов, то ни одна ссылка не может быть успешной. В любом случае нет смысла в импорте элемента.  
  
 Использовать **конструктора проектов** позволяет указать элементы для импорта. Используйте **импортированные пространства имен** раздел **ссылки** страницы. Можно получить **конструктора проектов** , дважды щелкнув **Мой проект** значок в **обозревателе решений**.  
  
 **Идентификатор ошибки:** BC40057  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1.  Откройте **конструктора проектов** и переключитесь в **ссылки** страницы.  
  
2.  В **импортированные пространства имен** убедитесь, что содержащий элемент доступен из проекта.  
  
3.  Убедитесь, что содержащий элемент предоставляет хотя бы один `Public` член.  
  
## <a name="see-also"></a>См. также  
 [Страница "Ссылки" в конструкторе проектов (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/references-page-project-designer-visual-basic)   
 [NIB Практическое руководство: изменение свойств проекта и параметров конфигурации](http://msdn.microsoft.com/en-us/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)   
 [Public](../../../visual-basic/language-reference/modifiers/public.md)   
 [Пространства имен в Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md)   
 [Ссылки на объявленные элементы](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
