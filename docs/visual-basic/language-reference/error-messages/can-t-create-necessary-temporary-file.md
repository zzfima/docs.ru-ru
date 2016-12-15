---
title: "Не удается создать требуемый временный файл | Microsoft Docs"
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
  - "vbrID322"
dev_langs: 
  - "VB"
ms.assetid: 53617b5b-eb06-4188-b4c2-8607cb9fbc79
caps.latest.revision: 6
caps.handback.revision: 6
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Не удается создать требуемый временный файл
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Диск, содержащий каталог, который указан переменной среды TEMP, переполнен, или переменная среды TEMP указывает недопустимый или доступный только для чтения диск или каталог.  
  
### Чтобы исправить эту ошибку  
  
1.  Если диск переполнен, удалите некоторые файлы.  
  
2.  Укажите другой диск в переменной среды TEMP.  
  
3.  Укажите допустимый диск для переменной среды TEMP.  
  
4.  Удалите ограничение на доступ только для чтения из указанного в текущий момент диска или каталога.  
  
## См. также  
 [Типы ошибок](../../../visual-basic/programming-guide/language-features/error-types.md)