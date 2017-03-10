---
title: "Не удается создать требуемый временный файл | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbrID322"
dev_langs: 
  - "VB"
ms.assetid: 53617b5b-eb06-4188-b4c2-8607cb9fbc79
caps.latest.revision: 6
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 6
---
# Не удается создать требуемый временный файл
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Диск, содержащий каталог, который указан переменной среды TEMP, переполнен, или переменная среды TEMP указывает недопустимый или доступный только для чтения диск или каталог.  
  
### Чтобы исправить эту ошибку  
  
1.  Если диск переполнен, удалите некоторые файлы.  
  
2.  Укажите другой диск в переменной среды TEMP.  
  
3.  Укажите допустимый диск для переменной среды TEMP.  
  
4.  Удалите ограничение на доступ только для чтения из указанного в текущий момент диска или каталога.  
  
## См. также  
 [Типы ошибок](../../../visual-basic/programming-guide/language-features/error-types.md)