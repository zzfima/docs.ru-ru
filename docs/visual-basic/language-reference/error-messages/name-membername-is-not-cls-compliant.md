---
title: "Имя &lt;membername&gt; не является CLS-совместимым"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc40031
- vbc40031
helpviewer_keywords:
- BC40031
ms.assetid: e2b885dc-cbf9-49ff-bbbe-531657ea99f7
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: ba0dda520e37b27f9b7ad3c214508ee370162598
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="name-ltmembernamegt-is-not-cls-compliant"></a>Имя &lt;membername&gt; не является CLS-совместимым
Сборка помечена как `<CLSCompliant(True)>` , но предоставляет член с именем, которое начинается со знака подчеркивания (`_`).  
  
 Программный элемент может содержать один или несколько символов подчеркивания, но чтобы быть совместимым с [независимость от языка и независимые от языка компоненты](../../../standard/language-independence-and-language-independent-components.md) (CLS), он не должен начинаться с символа подчеркивания. В разделе [имена объявленных элементов](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).  
  
 При применении атрибута <xref:System.CLSCompliantAttribute> к программному элементу вы задаете для параметра `isCompliant` атрибута значение `True` или `False` , чтобы указать совместимость или несовместимость. Для этого параметра нет значения по умолчанию, и вы должны предоставить его.  
  
 Если вы не применяете <xref:System.CLSCompliantAttribute> к элементу, он считается несовместимым.  
  
 По умолчанию данное сообщение является предупреждением. Сведения о сокрытии предупреждений или обработке предупреждений как ошибок см. в разделе [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Идентификатор ошибки:** BC40031  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Если вы можете управлять исходным кодом, измените имя члена, чтобы он не начинается с символа подчеркивания.  
  
-   Если требуется, чтобы имя члена осталось неизменными, удалите <xref:System.CLSCompliantAttribute> из его определения или пометьте его как `<CLSCompliant(False)>`. Можно также пометить сборку как `<CLSCompliant(True)>`.  
  
## <a name="see-also"></a>См. также  
 [Имена объявленных элементов](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)  
 [Соглашения об именах Visual Basic](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)  

