---
title: Свойство по умолчанию &#39; &lt;propertyname1&gt; &#39; конфликтует со свойством по умолчанию &#39; &lt;имя_свойства2&gt; &#39; в &#39; &lt;classname&gt; &#39;и должен быть объявлен &#39;Shadows&#39;
ms.date: 07/20/2015
f1_keywords:
- vbc40007
- bc40007
helpviewer_keywords:
- BC40007
ms.assetid: 692ccf76-5715-4f11-a972-84cf9de30bc1
ms.openlocfilehash: 3099467fa3c5a162c13c9235fb8d55375953ba3a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54521430"
---
# <a name="default-property-39ltpropertyname1gt39-conflicts-with-default-property-39ltpropertyname2gt39-in-39ltclassnamegt39-and-so-should-be-declared-39shadows39"></a>Свойство по умолчанию &#39; &lt;propertyname1&gt; &#39; конфликтует со свойством по умолчанию &#39; &lt;имя_свойства2&gt; &#39; в &#39; &lt;classname&gt; &#39;и должен быть объявлен &#39;Shadows&#39;
Свойство объявлено с тем же именем, что это свойство, определенное в базовом классе. В этом случае свойство в данном классе должно затемнять свойство базового класса.  
  
 Это сообщение является предупреждением. `Shadows` подразумевается по умолчанию. Дополнительные сведения о сокрытии предупреждений и обработке предупреждений как ошибок см. в разделе [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Идентификатор ошибки:** BC40007  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Добавление `Shadows` объявляемого ключевое слово объявления, или измените имя свойства.  
  
## <a name="see-also"></a>См. также
- [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md)
- [Сокрытие в Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
