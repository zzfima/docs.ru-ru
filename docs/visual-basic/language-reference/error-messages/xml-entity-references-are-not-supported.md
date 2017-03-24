---
title: "Ссылки на XML-сущности не поддерживаются | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbc31180"
  - "bc31180"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC31180"
ms.assetid: 2a393327-d8e2-4187-85b1-642b4f53b4ae
caps.latest.revision: 6
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 6
---
# Ссылки на XML-сущности не поддерживаются
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Ссылка на сущность \(например `©`\), которая не определена в спецификации XML 1.0, включена как значение XML\-литерала.  В XML\-литералах поддерживаются только ссылки на XML\-сущности `&`, `"`, `<`, `>` и `'`.  
  
 **Идентификатор ошибки**: BC31180  
  
### Чтобы исправить эту ошибку  
  
-   Удалите неподдерживаемую ссылку на сущность.  
  
## См. также  
 [XML\-литералы и спецификация XML 1.0](../../../visual-basic/programming-guide/language-features/xml/xml-literals-and-the-xml-1-0-specification.md)   
 [XML\-литералы](../../../visual-basic/language-reference/xml-literals/index.md)   
 [XML](../../../visual-basic/programming-guide/language-features/xml/index.md)