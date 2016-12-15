---
title: "Атрибут &lt;имяАтрибута&gt; не может применяться многократно | Microsoft Docs"
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
  - "bc30663"
  - "vbc30663"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30663"
ms.assetid: 3760e7ff-7238-40a1-8676-77d858a64fc0
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Атрибут &lt;имяАтрибута&gt; не может применяться многократно
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Атрибут может применяться только один раз.  Атрибут `AttributeUsage` определяет, может ли атрибут применяться многократно.  
  
 **Идентификатор ошибки:** BC30663  
  
### Чтобы исправить эту ошибку  
  
1.  Убедитесь, что атрибут применяется только один раз.  
  
2.  Если используются пользовательские атрибуты, созданные разработчиком, рассмотрите изменение атрибута `AttributeUsage`, чтобы разрешить многократное использование атрибутов, как в следующем примере.  
  
    ```  
    <AttributeUsage(AllowMultiple := True)>  
    ```  
  
## См. также  
 <xref:System.AttributeUsageAttribute>   
 [Создание настраиваемых атрибутов](../Topic/Creating%20Custom%20Attributes%20\(C%23%20and%20Visual%20Basic\).md)   
 [AttributeUsage](../Topic/AttributeUsage%20\(C%23%20and%20Visual%20Basic\).md)