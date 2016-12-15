---
title: "XML литералы и XML свойства не поддерживаются во встроенном в ASP.NET коде | Microsoft Docs"
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
  - "vbc31200"
  - "bc31200"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC31200"
ms.assetid: 053e8cba-8584-45cc-9fa0-43d122779772
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# XML литералы и XML свойства не поддерживаются во встроенном в ASP.NET коде
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

XML литералы и XML свойства не поддерживаются во встроенном в ASP.NET коде.Для использования возможностей XML, поместите код в фоновый код.  
  
 XML\-литерал или свойство оси XML определено во встроенном коде \(`<%= =>`\) в файле ASP.NET.  
  
 **Идентификатор ошибки:** BC31200  
  
### Чтобы исправить эту ошибку  
  
-   Переместите код, содержащий XML\-литерал или свойство оси XML\-файла, в файл кода программной части ASP.NET.  
  
## См. также  
 [XML\-литералы](../../../visual-basic/language-reference/xml-literals/index.md)   
 [Свойства оси XML](../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md)   
 [XML](../../../visual-basic/programming-guide/language-features/xml/index.md)