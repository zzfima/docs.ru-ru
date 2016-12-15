---
title: "Конструктор &lt;имя&gt; не может вызывать сам себя | Microsoft Docs"
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
  - "bc30298"
  - "vbc30298"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30298"
ms.assetid: 2d77b7f4-0640-4f89-9c65-f101fd2847c0
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Конструктор &lt;имя&gt; не может вызывать сам себя
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Процедура `Sub New` в классе или структуре вызывает саму себя.  
  
 Конструктор предназначен для инициализации экземпляра класса или структуры при его первом создании.  Класс или структура может иметь несколько конструкторов, если все они имеют различные списки параметров.  Конструктору разрешено вызывать другой конструктор для использования его функциональных возможностей в дополнение к собственным.  Но конструктору бессмысленно вызывать самого себя. Фактически, это может привести к бесконечной рекурсии.  
  
 **Идентификатор ошибки**: BC30298  
  
### Чтобы исправить эту ошибку  
  
1.  Проверьте список параметров вызываемого конструктора.  Он должен отличаться от вызывающего конструктора.  
  
2.  Если не требуется вызывать другой конструктор, удалите вызов `Sub New` полностью.  
  
## См. также  
 [Время существования: создание и уничтожение объектов](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)