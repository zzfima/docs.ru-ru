---
title: "Слишком много файлов | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbrID67"
dev_langs: 
  - "VB"
ms.assetid: 2ff203e2-bba6-43ae-b72f-8e92a881c98f
caps.latest.revision: 7
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 7
---
# Слишком много файлов
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Число созданных в корневом каталоге файлов превышает допустимое для операционной системы, или число открытых файлов превышает число, заданное параметром **files\=** в файле CONFIG.SYS.  
  
### Чтобы исправить эту ошибку  
  
1.  Если программа открывает, закрывает или сохраняет файлы в корневом каталоге, измените ее таким образом, чтобы в ней использовался подкаталог.  
  
2.  Увеличьте число файлов, заданное параметром **files\=** в файле CONFIG.SYS, и перезапустите компьютер.  
  
## См. также  
 [Типы ошибок](../../../visual-basic/programming-guide/language-features/error-types.md)