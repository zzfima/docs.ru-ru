---
title: Свойство <propertyname1>, используемое по умолчанию, конфликтует со свойством <propertyname2>, используемым по умолчанию в классе <classname>, и должно быть объявлено с ключевым словом Shadows
ms.date: 07/20/2015
f1_keywords:
- vbc40007
- bc40007
helpviewer_keywords:
- BC40007
ms.assetid: 692ccf76-5715-4f11-a972-84cf9de30bc1
ms.openlocfilehash: bc75b01532ffb112622d7f9bc837490c627883b3
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55270412"
---
# <a name="default-property-propertyname1-conflicts-with-default-property-propertyname2-in-classname-and-so-should-be-declared-shadows"></a>Свойство по умолчанию "\<propertyname1 >" конфликтует со свойством по умолчанию "\<имя_свойства2 >" в "\<имя_класса >" и должен быть объявлен «Shadows»
Свойство объявлено с тем же именем, что это свойство, определенное в базовом классе. В этом случае свойство в данном классе должно затемнять свойство базового класса.  
  
 Это сообщение является предупреждением. `Shadows` подразумевается по умолчанию. Дополнительные сведения о сокрытии предупреждений и обработке предупреждений как ошибок см. в разделе [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Идентификатор ошибки:** BC40007  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Добавление `Shadows` объявляемого ключевое слово объявления, или измените имя свойства.  
  
## <a name="see-also"></a>См. также
- [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md)
- [Сокрытие в Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
