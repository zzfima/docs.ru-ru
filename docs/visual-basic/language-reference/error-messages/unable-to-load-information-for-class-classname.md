---
title: "Не удается выполнить загрузку сведений для класса &lt;имяКласса&gt; | Microsoft Docs"
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
  - "vbc30712"
  - "bc30712"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30712"
ms.assetid: c7ffbd6d-05c6-4261-b44b-1bcd521bb350
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Не удается выполнить загрузку сведений для класса &lt;имяКласса&gt;
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Была сформирована ссылка на недоступный класс.  
  
 **Идентификатор ошибки**: BC30712  
  
### Чтобы исправить эту ошибку  
  
1.  Проверьте, что класс был определен и что его имя указано верно.  
  
2.  Попробуйте обратиться к одному из членов, объявленных в модуле.  В некоторых случаях среда отладки не может найти члены, потому что модули, в которых они объявлены, еще не были загружены.  
  
## См. также  
 [Отладка в Visual Studio](/visual-studio/debugger/debugging-in-visual-studio)