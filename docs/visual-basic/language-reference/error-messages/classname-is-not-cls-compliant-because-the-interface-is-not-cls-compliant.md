---
title: "&#39; &lt;classname&gt;&#39; не является CLS-совместимым, так как интерфейс &#39;&lt; Имя интерфейса&gt;&#39; он реализует, несовместим с CLS"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc40029
- vbc40029
helpviewer_keywords: BC40029
ms.assetid: 178452f3-5575-4da0-9d6c-53bcddb6a338
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 7bad6aa4c8fa9979824766e83aba75697d6e98d8
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="39ltclassnamegt39-is-not-cls-compliant-because-the-interface-39ltinterfacenamegt39-it-implements-is-not-cls-compliant"></a>&#39; &lt;classname&gt;&#39; не является CLS-совместимым, так как интерфейс &#39;&lt; Имя интерфейса&gt;&#39; он реализует, несовместим с CLS
Класс или интерфейс помечен как `<CLSCompliant(True)>` , если он наследует или реализует тип, помеченный как `<CLSCompliant(False)>` или не помеченный совсем.  
  
 Для класса или интерфейса стандарту [независимость от языка и независимые от языка компоненты](https://msdn.microsoft.com/library/12a7a7h3) (CLS) вся его иерархия наследования должна быть совместимой. Это означает, что каждый тип, от которого он наследуется прямо или косвенно, должен быть совместимым. Аналогично, если класс реализует один или несколько интерфейсов, то все они должны быть совместимыми по всей иерархии наследования.  
  
 Когда вы применяете атрибут <xref:System.CLSCompliantAttribute> к программному элементу, вы задаете для параметра `isCompliant` атрибута значение `True` или `False` , чтобы указать на совместимость или несовместимость. Для этого параметра нет значения по умолчанию, и вы должны предоставить его.  
  
 Если вы не применяете <xref:System.CLSCompliantAttribute> к элементу, он считается несовместимым.  
  
 По умолчанию данное сообщение является предупреждением. Сведения о сокрытии предупреждений или обработке предупреждений как ошибок см. в разделе [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Идентификатор ошибки:** BC40029  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Если требуется совместимость с CLS, определите этот тип в другой иерархии наследования или схеме реализации.  
  
-   Если требуется, чтобы этот тип оставался в текущей иерархии наследования или схеме реализации, удалите <xref:System.CLSCompliantAttribute> из его определения или пометьте его как `<CLSCompliant(False)>`.  
  
## <a name="see-also"></a>См. также  
 [\<PAVE НАД > написание CLS-совместимого кода](http://msdn.microsoft.com/en-us/4c705105-69a2-4e5e-b24e-0633bc32c7f3)
