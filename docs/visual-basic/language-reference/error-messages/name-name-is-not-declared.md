---
title: "Имя &#39; &lt;имя&gt;&#39; не объявлена"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30451
- vbc30451
helpviewer_keywords: BC30451
ms.assetid: 765f099b-e21e-47c6-a906-a065444e56b3
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 7a63ae74c7179d71756e2b9b4bf6b41a71ce12a6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="name-39ltnamegt39-is-not-declared"></a>Имя &#39; &lt;имя&gt;&#39; не объявлена
Оператор ссылается на элемент программирования, но компилятор не может найти элемент с указанным именем.  
  
 **Идентификатор ошибки:** BC30451  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1.  Проверьте правильность написания в ссылающемся операторе. [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]не учитывается регистр, но любое другое изменение в орфографии рассматривается как полностью другое имя. Обратите внимание, что символ подчеркивания (`_`) является частью имени и, следовательно, частью орфографии.  
  
2.  Убедитесь, что оператор доступа к членам (`.`) между объектом и его членах. Например, если у вас есть элемент управления <xref:System.Windows.Forms.TextBox> с именем `TextBox1`, то для доступа к его свойству <xref:System.Windows.Forms.TextBoxBase.Text%2A> следует ввести `TextBox1.Text`. Если вместо этого ввести `TextBox1Text`, будет создано другое имя.  
  
3.  Если правильность написания и имеет правильный синтаксис любой доступ к членам объекта, убедитесь, что был объявлен элемент. Дополнительные сведения см. в разделе [объявленные элементы](../../../visual-basic/programming-guide/language-features/declared-elements/index.md).  
  
4.  Если программный элемент объявлен, проверьте, что он находится в области. Если ссылающийся оператор находится вне области объявления программного элемента, может потребоваться уточнение имени элемента. Дополнительные сведения см. в разделе [области в Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/scope.md).  
  
## <a name="see-also"></a>См. также  
 [Сводка по объявлениям и константам](../../../visual-basic/language-reference/keywords/declarations-and-constants-summary.md)  
 [Соглашения об именах Visual Basic](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)  
 [Имена объявленных элементов](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)  
 [Ссылки на объявленные элементы](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
