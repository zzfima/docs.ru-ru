---
title: "Процедура свойства let не определена, а процедура свойства get не вернула объект | Microsoft Docs"
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
  - "vbrID451"
dev_langs: 
  - "VB"
ms.assetid: 8542382a-689f-4e1b-abc0-c1e2dadb92f4
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Процедура свойства let не определена, а процедура свойства get не вернула объект
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Некоторые свойства, методы и операции применимы только к объектам `Collection`.  Указанные операция или свойство применимы только к коллекциям, однако данный объект не является коллекцией.  
  
### Чтобы исправить эту ошибку  
  
1.  Проверьте правильность написания имени объекта или свойства или убедитесь, что данный объект является объектом `Collection`.  
  
2.  Убедитесь, что в методе `Add`, который используется для добавления объекта к коллекции, используется правильный синтаксис и правильное написание идентификаторов.  
  
## См. также  
 <xref:Microsoft.VisualBasic.Collection>