---
title: "Имя &lt;имяПространстваИмен&gt; в корневом пространстве имен &lt;полноеИмяПространстваИмен&gt; не является CLS-совместимым | Microsoft Docs"
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
  - "vbc40039"
  - "bc40039"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC40039"
ms.assetid: c5bd5914-ae71-416a-8bed-f76f644f78be
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Имя &lt;имяПространстваИмен&gt; в корневом пространстве имен &lt;полноеИмяПространстваИмен&gt; не является CLS-совместимым
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Сборка помечена как `<CLSCompliant(True)>`, но элемент корневого пространства имен начинается со знака подчеркивания \(`_`\).  
  
 Программный элемент может содержать один или несколько символов подчеркивания, однако, чтобы быть совместимым с [Независимость от языка и независимые от языка компоненты](../Topic/Language%20Independence%20and%20Language-Independent%20Components.md) \(CLS\), он не должен начинается со знака подчеркивания.  См. раздел [Имена объявленных элементов](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).  
  
 При применении атрибута <xref:System.CLSCompliantAttribute> к программному элементу параметру атрибута `isCompliant` присваивается значение `True` или `False`, указывающее на совместимость или несовместимость.  Значение по умолчанию для этого параметра отсутствует, поэтому значение необходимо указать.  
  
 Если к элементу не применяется атрибут <xref:System.CLSCompliantAttribute>, элемент считается несовместимым.  
  
 По умолчанию это сообщение является предупреждающим.  Дополнительные сведения о скрытии предупреждений или их обработке как ошибок см. в разделе [Настройка предупреждений в Visual Basic](/visual-studio/ide/configuring-warnings-in-visual-basic).  
  
 **Идентификатор ошибки**: BC40039  
  
### Чтобы исправить эту ошибку  
  
-   Если требуется CLS\-совместимость, измените имя корневого пространства имен таким образом, чтобы ни один из его элементов не начинался со знака подчеркивания.  
  
-   Если требуется, чтобы имя пространства имен осталось неизменными, удалите <xref:System.CLSCompliantAttribute> из сборки или пометьте его как `<CLSCompliant(False)>`.  
  
## См. также  
 [Оператор Namespace](../../../visual-basic/language-reference/statements/namespace-statement.md)   
 [Пространства имен в Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md)   
 [\/rootnamespace](../../../visual-basic/reference/command-line-compiler/rootnamespace.md)   
 [Страница «Приложение» в конструкторе проектов \(Visual Basic\)](/visual-studio/ide/reference/application-page-project-designer-visual-basic)   
 [Имена объявленных элементов](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)   
 [Соглашения об именах Visual Basic](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)   
 [\<PAVE OVER\> Writing CLS\-Compliant Code](http://msdn.microsoft.com/ru-ru/4c705105-69a2-4e5e-b24e-0633bc32c7f3)