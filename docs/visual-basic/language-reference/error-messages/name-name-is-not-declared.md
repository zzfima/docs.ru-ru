---
title: "Имя &quot;&lt;имя&gt;&quot; не объявлен | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30451
- vbc30451
dev_langs:
- VB
helpviewer_keywords:
- BC30451
ms.assetid: 765f099b-e21e-47c6-a906-a065444e56b3
caps.latest.revision: 11
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
ms.openlocfilehash: 81b6862a7f8ceb7998b2ea53336ed3af46b1db5f
ms.lasthandoff: 03/13/2017

---
# <a name="name-39ltnamegt39-is-not-declared"></a>Имя "&lt;имя&gt;" не объявлен как
Оператор ссылается на элемент программирования, но компилятор не может найти элемент с указанным именем.  
  
 **Идентификатор ошибки:** BC30451  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1.  Проверьте правильность написания в ссылающемся операторе. [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]не учитывает регистр, но любое другое изменение в орфографии рассматривается как полностью другое имя. Обратите внимание, что символ подчеркивания (`_`) является частью имени и, следовательно, частью орфографии.  
  
2.  Убедитесь, что оператор доступа к членам (`.`) между объектом и его членах. Например, если у вас есть <xref:System.Windows.Forms.TextBox>элемент управления с именем `TextBox1`, чтобы получить доступ к его <xref:System.Windows.Forms.TextBoxBase.Text%2A>свойство, следует ввести `TextBox1.Text`.</xref:System.Windows.Forms.TextBoxBase.Text%2A> </xref:System.Windows.Forms.TextBox> Если вместо этого ввести `TextBox1Text`, будет создано другое имя.  
  
3.  Если правильность написания и синтаксис любой доступ к членам объекта, убедитесь, что элемент был объявлен. Дополнительные сведения см. в разделе [объявленные элементы](../../../visual-basic/programming-guide/language-features/declared-elements/index.md).  
  
4.  Если элемент программирования был объявлен, проверьте его в области видимости. Если ссылающийся оператор находится вне области объявления программного элемента, может потребоваться уточнение имени элемента. Дополнительные сведения см. в разделе [область в Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/scope.md).  
  
## <a name="see-also"></a>См. также  
 [Сводка объявлений и констант](../../../visual-basic/language-reference/keywords/declarations-and-constants-summary.md)   
 [Соглашения об именах Visual Basic](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)   
 [Имена объявленных элементов](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)   
 [Ссылки на объявленные элементы](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
