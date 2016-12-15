---
title: "Имя &lt;имя&gt; не объявлено | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "bc30451"
  - "vbc30451"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30451"
ms.assetid: 765f099b-e21e-47c6-a906-a065444e56b3
caps.latest.revision: 11
caps.handback.revision: 11
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Имя &lt;имя&gt; не объявлено
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Оператор ссылается на элемент программирования, однако компилятор не может найти элемент с указанным именем.  
  
 **Идентификатор ошибки**: BC30451  
  
### Чтобы исправить эту ошибку  
  
1.  Проверьте правильность написания имени в инструкции, содержащей ссылку.  [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] не учитывает регистр, но любое другое изменение в орфографии рассматривается как полностью другое имя.  Обратите внимание, что подчеркивание \(`_`\) является частью имени и частью орфографии.  
  
2.  Проверьте наличие оператора доступа \(`.`\) между объектом и его элементом.  Например, если имеется элемент управления <xref:System.Windows.Forms.TextBox> `TextBox1`, то для доступа к свойству <xref:System.Windows.Forms.TextBoxBase.Text%2A> необходимо написать `TextBox1.Text`.  Если вместо этого ввести `TextBox1Text`, то создается другое имя.  
  
3.  Если соблюдена правильность правописания и задан правильный синтаксис доступа к элементу любого объекта, убедитесь, что элемент был объявлен.  Дополнительные сведения см. в разделе [Объявленные элементы](../../../visual-basic/programming-guide/language-features/declared-elements/index.md).  
  
4.  Если элемент программирования был объявлен, убедитесь, что он находится в области действия.  Если оператор, на который выполняется ссылка, находится вне области объявления элемента программирования, то может потребоваться уточнение имени элемента.  Дополнительные сведения см. в разделе [Область видимости в Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/scope.md).  
  
## См. также  
 [Сводка по объявлениям и константам](../../../visual-basic/language-reference/keywords/declarations-and-constants-summary.md)   
 [Соглашения об именах Visual Basic](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)   
 [Имена объявленных элементов](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)   
 [Ссылки на объявленные элементы](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)