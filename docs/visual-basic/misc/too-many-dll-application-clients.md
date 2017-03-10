---
title: "Слишком много приложений-клиентов DLL | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbrID47"
ms.assetid: 4b87780b-67ad-4c96-9253-db954a751dad
caps.latest.revision: 8
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 8
---
# Слишком много приложений-клиентов DLL
Библиотека динамической компоновки \(DLL\) для [!INCLUDE[vbprvb](../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] может обеспечить доступ ограниченному числу ведущих приложений. Ваше приложение и другие приложения, которые являются узлами [!INCLUDE[vbprvb](../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] \(к некоторым из которых может обращаться ваше приложение\), пытаются получить доступ к библиотеке DLL [!INCLUDE[vbprvb](../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] одновременно.  
  
### Исправление ошибки  
  
-   Уменьшите число открытых приложений, обращающихся к [!INCLUDE[vbprvb](../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)].  
  
## См. также  
 [Типы ошибок](../../visual-basic/programming-guide/language-features/error-types.md)