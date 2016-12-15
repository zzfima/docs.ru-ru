---
title: "Ошибка автоматизации | Microsoft Docs"
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
  - "vbrID440"
dev_langs: 
  - "VB"
ms.assetid: 2c4be5c5-2f0d-4a2b-96fe-d1b24f08fc4c
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Ошибка автоматизации
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

При выполнении метода либо при получении либо установке значения свойства переменной объекта возникла ошибка.  О ней сообщило приложение, создавшее этот объект.  
  
### Исправление ошибки  
  
1.  Проверьте свойства объекта `Err`, чтобы определить причину и характер ошибки.  
  
2.  Используйте инструкцию `On Error Resume Next` непосредственно перед инструкцией доступа, а затем выполните проверку на наличие ошибок сразу после инструкции доступа.  
  
## См. также  
 [Типы ошибок](../../../visual-basic/programming-guide/language-features/error-types.md)   
 [Обращайтесь к нам](/visual-studio/ide/talk-to-us)