---
title: "Свойство &lt;имяСвойства1&gt;, используемое по умолчанию, конфликтует со свойством &lt;имяСвойства2&gt;, используемым по умолчанию в классе &lt;имяКласса&gt;, и должно быть объявлено с ключевым словом Shadows | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc40007"
  - "bc40007"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC40007"
ms.assetid: 692ccf76-5715-4f11-a972-84cf9de30bc1
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Свойство &lt;имяСвойства1&gt;, используемое по умолчанию, конфликтует со свойством &lt;имяСвойства2&gt;, используемым по умолчанию в классе &lt;имяКласса&gt;, и должно быть объявлено с ключевым словом Shadows
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Свойство объявлено с тем же именем, что и свойство, определенное в базовом классе.  В этом случае свойство данного класса должно скрывать свойство базового класса.  
  
 Это сообщение является предупреждением.  `Shadows` подразумевается по умолчанию.  Дополнительные сведения о скрытии предупреждений или их обработке как ошибок см. в разделе [Настройка предупреждений в Visual Basic](/visual-studio/ide/configuring-warnings-in-visual-basic).  
  
 **Идентификатор ошибки**: BC40007  
  
### Чтобы исправить эту ошибку  
  
-   Добавьте в объявление ключевое слово `Shadows` или измените имя объявляемого свойства.  
  
## См. также  
 [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md)   
 [Сокрытие в Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)