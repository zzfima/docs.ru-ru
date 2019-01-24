---
title: Имя &lt;membername&gt; не является CLS-совместимым
ms.date: 07/20/2015
f1_keywords:
- bc40031
- vbc40031
helpviewer_keywords:
- BC40031
ms.assetid: e2b885dc-cbf9-49ff-bbbe-531657ea99f7
ms.openlocfilehash: b950be530eb80fd1c65b48e1625eb344c642d260
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54626372"
---
# <a name="name-ltmembernamegt-is-not-cls-compliant"></a>Имя &lt;membername&gt; не является CLS-совместимым
Сборка помечена как `<CLSCompliant(True)>` , но предоставляет член с именем, начинающимся со знака подчеркивания (`_`).  
  
 Программный элемент может содержать один или несколько символов подчеркивания, но чтобы быть совместимым с [независимость от языка и независимые от языка компоненты](../../../standard/language-independence-and-language-independent-components.md) (CLS), он не должен начинаться с символа подчеркивания. См. раздел [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).  
  
 При применении атрибута <xref:System.CLSCompliantAttribute> к программному элементу вы задаете для параметра `isCompliant` атрибута значение `True` или `False` , чтобы указать совместимость или несовместимость. Для этого параметра нет значения по умолчанию, и вы должны предоставить значение.  
  
 Если вы не применяете <xref:System.CLSCompliantAttribute> к элементу, он считается несовместимым.  
  
 По умолчанию данное сообщение является предупреждением. Сведения о сокрытии предупреждений или обработке предупреждений как ошибок см. в разделе [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Идентификатор ошибки:** BC40031  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Если вы можете контролировать исходный код, измените имя члена таким образом, чтобы он не начинается с символа подчеркивания.  
  
-   Если требуется, что имя члена остаются неизменными, удалите <xref:System.CLSCompliantAttribute> из его определения или пометьте его как `<CLSCompliant(False)>`. Можно также пометить ее как `<CLSCompliant(True)>`.  
  
## <a name="see-also"></a>См. также
- [Имена объявленных элементов](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)
- [Соглашения об именах Visual Basic](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)

