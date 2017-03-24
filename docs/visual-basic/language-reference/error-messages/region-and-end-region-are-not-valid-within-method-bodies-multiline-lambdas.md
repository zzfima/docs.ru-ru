---
title: "Операторы #Region и #End Region недопустимы в телах методов/многострочных лямбда-операторах | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
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
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 10
---
# Операторы #Region и #End Region недопустимы в телах методов/многострочных лямбда-операторах
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Блок `#Region` должен быть объявлен на уровне класса, модуля или пространства имен.  Свертываемая область может включать одну или несколько процедур, но не может начинаться или заканчиваться внутри процедуры.  
  
 **Идентификатор ошибки**: BC32025  
  
### Чтобы исправить эту ошибку  
  
1.  Убедитесь, что предыдущая процедура корректно завершается оператором `End Function` или `End Sub`.  
  
2.  Убедитесь, что директивы `#Region` и `#End Region` находятся в одном блоке кода.  
  
## См. также  
 [Директива \#Region](../../../visual-basic/language-reference/directives/region-directive.md)