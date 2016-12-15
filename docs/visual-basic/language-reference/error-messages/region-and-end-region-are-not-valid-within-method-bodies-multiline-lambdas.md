---
title: "Операторы #Region и #End Region недопустимы в телах методов/многострочных лямбда-операторах | Microsoft Docs"
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
  - "bc32025"
  - "vbc32025"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC32025"
ms.assetid: 43707bf1-1c6b-4d82-b081-e5a17dca51c1
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Операторы #Region и #End Region недопустимы в телах методов/многострочных лямбда-операторах
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Блок `#Region` должен быть объявлен на уровне класса, модуля или пространства имен.  Свертываемая область может включать одну или несколько процедур, но не может начинаться или заканчиваться внутри процедуры.  
  
 **Идентификатор ошибки**: BC32025  
  
### Чтобы исправить эту ошибку  
  
1.  Убедитесь, что предыдущая процедура корректно завершается оператором `End Function` или `End Sub`.  
  
2.  Убедитесь, что директивы `#Region` и `#End Region` находятся в одном блоке кода.  
  
## См. также  
 [Директива \#Region](../../../visual-basic/language-reference/directives/region-directive.md)