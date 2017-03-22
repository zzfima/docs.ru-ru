---
title: "Не являющиеся CLS-совместимыми &lt;membername&gt; не допускается в CLS-совместимом интерфейсе | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc40033
- vbc40033
dev_langs:
- VB
helpviewer_keywords:
- BC40033
ms.assetid: 060c4b08-798e-40f1-94cf-c05c524f1b8a
caps.latest.revision: 9
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
ms.openlocfilehash: 2861ef22c9307e5bd7d2eabf4f6e37bbd9086345
ms.lasthandoff: 03/13/2017

---
# <a name="non-cls-compliant-ltmembernamegt-is-not-allowed-in-a-cls-compliant-interface"></a>Не являющиеся CLS-совместимыми &lt;membername&gt; не допускается в CLS-совместимом интерфейсе
Свойство, процедура или событие в интерфейсе помечен как `<CLSCompliant(True)>` при сам интерфейс помечен как `<CLSCompliant(False)>` или не отмечен.  
  
 Для интерфейса в соответствии с [независимость от языка и независимые от языка компоненты](https://msdn.microsoft.com/library/12a7a7h3) (CLS), все его члены должны быть совместимыми.  
  
 При применении <xref:System.CLSCompliantAttribute>к программному элементу, задайте атрибут `isCompliant` параметр либо `True` или `False` , чтобы указать соответствие или несоответствие.</xref:System.CLSCompliantAttribute> Для этого параметра нет значения по умолчанию, и вы должны предоставить его.  
  
 Если не применить <xref:System.CLSCompliantAttribute>на элемент, он считается как несоответствующий.</xref:System.CLSCompliantAttribute>  
  
 По умолчанию данное сообщение является предупреждением. Сведения о сокрытии предупреждений или обработке предупреждений как ошибок см. в разделе [Configuring Warnings in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Идентификатор ошибки:** BC40033  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Если требуется CLS-совместимость и имеется контроль над всем исходным кодом интерфейса, пометьте интерфейс как `<CLSCompliant(True)>` Если все его члены являются совместимыми.  
  
-   Если требуется CLS-совместимость и нет контроля над всем исходным кодом интерфейса, или он не определен как совместимый, определите этот член внутри другого интерфейса.  
  
-   Если требуется, чтобы этот член оставался в текущем интерфейсе, удалите <xref:System.CLSCompliantAttribute>из его определения или пометьте его как `<CLSCompliant(False)>`.</xref:System.CLSCompliantAttribute>  
  
## <a name="see-also"></a>См. также  
 [Оператор Interface](../../../visual-basic/language-reference/statements/interface-statement.md)   
 [\<PAVE НАД настроек написание CLS-совместимого кода](http://msdn.microsoft.com/en-us/4c705105-69a2-4e5e-b24e-0633bc32c7f3)
