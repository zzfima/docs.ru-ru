---
title: "Недопустимое имя файла или номер | Microsoft Docs"
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
  - "vbrID52"
dev_langs: 
  - "VB"
ms.assetid: d0e96aea-7621-48f6-a78b-5d37d18aaa4e
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Недопустимое имя файла или номер
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

При попытке получения доступа к указанному файлу возникла ошибка.  Возможны следующие причины данной ошибки:  
  
-   Оператор содержит ссылку на файл с именем или номером, который не был указан в операторе `FileOpen` или был указан в этом операторе `FileOpen`, однако впоследствии был закрыт.  
  
-   Оператор ссылается на файл с номером, который не входит в диапазон номеров файлов.  
  
-   Оператор ссылается на имя или номер файла, которые являются недопустимыми.  
  
### Чтобы исправить эту ошибку  
  
1.  Убедитесь, что имя файла указано в операторе `FileOpen`.  Обратите внимание, что при вызове оператора `FileClose` без аргументов все открытые файлы могут быть случайно закрыты.  
  
2.  Если код создает номера файлов алгоритмически, убедитесь, что эти номера являются допустимыми.  
  
3.  Убедитесь, что имена файлов соответствуют соглашениям операционной системы.  
  
## См. также  
 <xref:Microsoft.VisualBasic.FileSystem.FileOpen%2A>   
 [Соглашения об именах Visual Basic](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)