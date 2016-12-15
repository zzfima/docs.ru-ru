---
title: "CLS-несовместимый &lt;имяЧлена&gt; не допускается в CLS-совместимом интерфейсе | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "bc40033"
  - "vbc40033"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC40033"
ms.assetid: 060c4b08-798e-40f1-94cf-c05c524f1b8a
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# CLS-несовместимый &lt;имяЧлена&gt; не допускается в CLS-совместимом интерфейсе
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Свойство, процедура или событие в интерфейсе помечены как `<CLSCompliant(True)>`, тогда как сам интерфейс помечен как `<CLSCompliant(False)>` или не помечен вовсе.  
  
 Чтобы интерфейс был совместим с [Независимость от языка и независимые от языка компоненты](../Topic/Language%20Independence%20and%20Language-Independent%20Components.md) \(CLS\), все его члены должны быть совместимыми.  
  
 При применении атрибута <xref:System.CLSCompliantAttribute> к программному элементу параметру атрибута `isCompliant` присваивается значение `True` или `False`, указывающее на совместимость или несовместимость.  Значение по умолчанию для этого параметра отсутствует, поэтому значение необходимо указать.  
  
 Если к элементу не применяется атрибут <xref:System.CLSCompliantAttribute>, элемент считается несовместимым.  
  
 По умолчанию это сообщение является предупреждающим.  Дополнительные сведения о скрытии предупреждений или их обработке как ошибок см. в разделе [Настройка предупреждений в Visual Basic](/visual-studio/ide/configuring-warnings-in-visual-basic).  
  
 **Идентификатор ошибки:** BC40033  
  
### Чтобы исправить эту ошибку  
  
-   Если необходима CLS\-совместимость и имеется контроль над всем исходным кодом интерфейса, пометьте интерфейс как `<CLSCompliant(True)>`, если все его члены являются совместимыми.  
  
-   Если требуется CLS\-совместимость и нет контроля над всем исходным кодом интерфейса, или он не определен как совместимый, определите этот член внутри другого интерфейса.  
  
-   Если требуется, чтобы этот член оставался в текущем интерфейсе, удалите <xref:System.CLSCompliantAttribute> из его определения или пометьте его как `<CLSCompliant(False)>`.  
  
## См. также  
 [Оператор Interface](../../../visual-basic/language-reference/statements/interface-statement.md)   
 [\<PAVE OVER\> Writing CLS\-Compliant Code](http://msdn.microsoft.com/ru-ru/4c705105-69a2-4e5e-b24e-0633bc32c7f3)