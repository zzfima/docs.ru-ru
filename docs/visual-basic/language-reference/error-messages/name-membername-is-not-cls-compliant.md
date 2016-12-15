---
title: "Имя &lt;имяЧлена&gt; не является CLS-совместимым | Microsoft Docs"
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
  - "bc40031"
  - "vbc40031"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC40031"
ms.assetid: e2b885dc-cbf9-49ff-bbbe-531657ea99f7
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Имя &lt;имяЧлена&gt; не является CLS-совместимым
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Сборка помечена как `<CLSCompliant(True)>`, но предоставляет член с именем, которое начинается с подчеркивания \(`_`\).  
  
 Программный элемент может содержать один или несколько символов подчеркивания, однако, чтобы быть совместимым с [Независимость от языка и независимые от языка компоненты](../Topic/Language%20Independence%20and%20Language-Independent%20Components.md) \(CLS\), он не должен начинается со знака подчеркивания.  См. раздел [Имена объявленных элементов](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).  
  
 При применении атрибута <xref:System.CLSCompliantAttribute> к программному элементу параметру атрибута `isCompliant` присваивается значение `True` или `False`, указывающее на совместимость или несовместимость.  Значение по умолчанию для этого параметра отсутствует, поэтому значение необходимо указать.  
  
 Если к элементу не применяется атрибут <xref:System.CLSCompliantAttribute>, элемент считается несовместимым.  
  
 По умолчанию это сообщение является предупреждающим.  Дополнительные сведения о скрытии предупреждений или их обработке как ошибок см. в разделе [Настройка предупреждений в Visual Basic](/visual-studio/ide/configuring-warnings-in-visual-basic).  
  
 **Идентификатор ошибки**: BC40031  
  
### Чтобы исправить эту ошибку  
  
-   Если имеется контроль над исходным кодом, то следует изменить имя члена таким образом, чтобы оно не начиналось со знака подчеркивания.  
  
-   Если требуется, чтобы имя члена осталось неизменными, следует удалить <xref:System.CLSCompliantAttribute> из его определения или пометить его как `<CLSCompliant(False)>`.  Можно также пометить сборку как `<CLSCompliant(True)>`.  
  
## См. также  
 [Имена объявленных элементов](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)   
 [Соглашения об именах Visual Basic](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)   
 [\<PAVE OVER\> Writing CLS\-Compliant Code](http://msdn.microsoft.com/ru-ru/4c705105-69a2-4e5e-b24e-0633bc32c7f3)