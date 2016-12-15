---
title: "Выражение имеет тип &lt;имяТипа&gt; который является ограниченным и не может использоваться для доступа к членам, унаследованным от Object или ValueType | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "bc31393"
  - "vbc31393"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC31393"
ms.assetid: 2963cf3f-c527-4aa7-b67c-ee80b6d23186
caps.latest.revision: 6
caps.handback.revision: 6
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Выражение имеет тип &lt;имяТипа&gt; который является ограниченным и не может использоваться для доступа к членам, унаследованным от Object или ValueType
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Выражение имеет тип, который не может быть упакован средой CLR, но обращается к члену, для которого требуется упаковка.  
  
 Термин *упаковка* обозначает обработку, необходимую для преобразования типа к `Object` или, в некоторых случаях, к <xref:System.ValueType>.  Среда CLR не поддерживает упаковку определенных типов структуры, например <xref:System.ArgIterator>, <xref:System.RuntimeArgumentHandle> и <xref:System.TypedReference>.  
  
 Это выражение пытается использовать ограниченный тип, чтобы вызвать метод, унаследованный от <xref:System.Object> или <xref:System.ValueType>, например <xref:System.Object.GetHashCode%2A> или <xref:System.Object.ToString%2A>.  Чтобы получить доступ к этому методу, в [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] выполняется неявное преобразование упаковки, которое вызывает эту ошибку.  
  
 **Идентификатор ошибки**: BC31393  
  
### Чтобы исправить эту ошибку  
  
1.  Найдите выражение, вычисляющее указанный тип.  
  
2.  Найдите часть оператора, в которой вызывается метод, унаследованный от <xref:System.Object> или <xref:System.ValueType>.  
  
3.  Перепишите оператор, чтобы избежать вызова метода.  
  
## См. также  
 [Явные и неявные преобразования](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)