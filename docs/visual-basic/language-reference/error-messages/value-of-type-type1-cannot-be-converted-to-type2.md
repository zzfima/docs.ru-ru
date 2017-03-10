---
title: "Невозможно преобразовать значение типа &lt;тип1&gt; в &lt;тип2&gt; | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbc31194"
  - "bc31194"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC31194"
ms.assetid: 03d50c31-addd-4c90-9c53-725b84f9782e
caps.latest.revision: 5
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 5
---
# Невозможно преобразовать значение типа &lt;тип1&gt; в &lt;тип2&gt;
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Невозможно преобразовать значение типа "тип1" в "тип2".Можно использовать свойство "Value" для получения строкового значения первого элемента "\<родительский\_элемент\>".  
  
 Предпринята попытка неявного приведения XML\-литерала к определенному типу.  XML\-литерал не может быть неявно приведен к указанному типу.  
  
 **Идентификатор ошибки:** BC31194  
  
### Чтобы исправить эту ошибку  
  
-   Используйте свойство `Value` XML\-литерала для указания его значения в качестве `String`.  Используйте функцию `CType`, другую функцию преобразования типа или класс <xref:System.Convert> для приведения значения к указанному типу.  
  
## См. также  
 <xref:System.Convert>   
 [Функции преобразования типов](../../../visual-basic/language-reference/functions/type-conversion-functions.md)   
 [XML\-литералы](../../../visual-basic/language-reference/xml-literals/index.md)   
 [XML](../../../visual-basic/programming-guide/language-features/xml/index.md)