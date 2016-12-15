---
title: "Ожидается Optional | Microsoft Docs"
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
  - "bc30202"
  - "vbc30202"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30202"
ms.assetid: 6f75060c-2db4-4a79-b5d1-5780c09a74cd
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Ожидается Optional
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

За необязательным аргументом в объявлении процедуры следует обязательный аргумент.  Каждый следующий аргумент после необязательного аргумента также должен быть необязательным.  
  
 **Идентификатор ошибки:** BC30202  
  
### Чтобы исправить эту ошибку  
  
1.  Если аргумент является обязательным, переместите его в списке аргументов в позицию, предшествующую необязательному аргументу.  
  
2.  Если аргумент является необязательным, используйте ключевое слово `Optional`.  
  
## См. также  
 [Необязательные параметры](../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md)