---
title: Свойство по умолчанию &#39; &lt;свойство имя_свойства1&gt; &#39; конфликтует со свойством по умолчанию &#39; &lt;имя_свойства2&gt; &#39; в &#39; &lt;classname&gt; &#39;и должен быть объявлен &#39;тени&#39;
ms.date: 07/20/2015
f1_keywords:
- vbc40007
- bc40007
helpviewer_keywords:
- BC40007
ms.assetid: 692ccf76-5715-4f11-a972-84cf9de30bc1
ms.openlocfilehash: b305f7a59a9865ebeb6b6f53607757b719fb4d41
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33586628"
---
# <a name="default-property-39ltpropertyname1gt39-conflicts-with-default-property-39ltpropertyname2gt39-in-39ltclassnamegt39-and-so-should-be-declared-39shadows39"></a>Свойство по умолчанию &#39; &lt;свойство имя_свойства1&gt; &#39; конфликтует со свойством по умолчанию &#39; &lt;имя_свойства2&gt; &#39; в &#39; &lt;classname&gt; &#39;и должен быть объявлен &#39;тени&#39;
Свойство объявлено с тем же именем, как свойство, определенное в базовом классе. В этом случае свойство в данном классе должно скрывать свойство базового класса.  
  
 Это сообщение является предупреждением. `Shadows` подразумевается по умолчанию. Дополнительные сведения о скрытии предупреждений или обработке предупреждений как ошибок см. в разделе [Настройка предупреждений в Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Идентификатор ошибки:** BC40007  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Добавить `Shadows` объявляемого ключевое слово объявления или измените имя свойства.  
  
## <a name="see-also"></a>См. также  
 [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md)  
 [Сокрытие в Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
