---
title: "Не являющиеся CLS-совместимыми &lt;membername&gt; не допускается в CLS-совместимый интерфейс"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc40033
- vbc40033
helpviewer_keywords: BC40033
ms.assetid: 060c4b08-798e-40f1-94cf-c05c524f1b8a
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 358abd338d3ce780c2f0aae7aa8efb53e57b477c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="non-cls-compliant-ltmembernamegt-is-not-allowed-in-a-cls-compliant-interface"></a>Не являющиеся CLS-совместимыми &lt;membername&gt; не допускается в CLS-совместимый интерфейс
Свойство, процедура или событие в интерфейсе помечен как `<CLSCompliant(True)>` когда сам интерфейс помечен как `<CLSCompliant(False)>` или не отмечен.  
  
 Для интерфейса в соответствии с [независимость от языка и независимые от языка компоненты](https://msdn.microsoft.com/library/12a7a7h3) (CLS), все члены должны быть совместимыми.  
  
 При применении атрибута <xref:System.CLSCompliantAttribute> к программному элементу вы задаете для параметра `isCompliant` атрибута значение `True` или `False` , чтобы указать совместимость или несовместимость. Для этого параметра нет значения по умолчанию, и вы должны предоставить его.  
  
 Если вы не применяете <xref:System.CLSCompliantAttribute> к элементу, он считается несовместимым.  
  
 По умолчанию данное сообщение является предупреждением. Сведения о сокрытии предупреждений или обработке предупреждений как ошибок см. в разделе [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Идентификатор ошибки:** BC40033  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Если необходима CLS-совместимость и имеется контроль над исходным кодом интерфейса, пометьте интерфейс как `<CLSCompliant(True)>` Если все его члены являются совместимыми.  
  
-   Если требуется совместимость с CLS и вы можете управлять исходным кодом интерфейса, или он не квалифицирован как совместимый, определите этот член внутри другого интерфейса.  
  
-   Если требуется, чтобы этот член оставался в текущем интерфейсе, удалите <xref:System.CLSCompliantAttribute> из его определения или пометьте его как `<CLSCompliant(False)>`.  
  
## <a name="see-also"></a>См. также  
 [Оператор Interface](../../../visual-basic/language-reference/statements/interface-statement.md)  
 [\<PAVE НАД > написание CLS-совместимого кода](http://msdn.microsoft.com/en-us/4c705105-69a2-4e5e-b24e-0633bc32c7f3)
