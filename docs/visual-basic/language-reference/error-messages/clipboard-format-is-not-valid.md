---
title: "Недопустимый формат буфера обмена | Microsoft Docs"
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
  - "vbrID460"
dev_langs: 
  - "VB"
ms.assetid: 71a4a045-65bb-417d-b3bd-99a9fa3c53f6
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Недопустимый формат буфера обмена
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Указанный формат буфера обмена несовместим с выполняемым методом.  Возможны следующие причины данной ошибки:  
  
-   Использование метода `GetText` или `SetText` буфера обмена с форматом буфера обмена, отличным от `vbCFText` или `vbCFLink`.  
  
-   Использование метода `GetData` или `SetData` буфера обмена с форматом буфера обмена, отличным от `vbCFBitmap`, `vbCFDIB` или `vbCFMetafile`.  
  
-   Использование метода `DataObject` `GetData` или метода `SetData` с форматом буфера обмена в диапазоне, зарезервированном Microsoft Windows для зарегистрированных форматов \(&HC000\-&HFFFF\), но при этом данный формат буфера обмена не был зарегистрирован с помощью Microsoft Windows.  
  
### Чтобы исправить эту ошибку  
  
-   Удалите недопустимый формат и укажите допустимый.  
  
## См. также  
 [Буфер обмена. Добавление других форматов](../Topic/Clipboard:%20Adding%20Other%20Formats.md)