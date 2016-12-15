---
title: "Операторы Module могут присутствовать только на уровне файлов или пространств имен | Microsoft Docs"
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
  - "bc30617"
  - "vbc30617"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30617"
ms.assetid: 5e9de8e5-d26b-4fb2-9e28-814413fe9cef
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Операторы Module могут присутствовать только на уровне файлов или пространств имен
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Операторы `Module` должны находиться в начале исходного файла сразу после операторов `Option` и `Imports`, глобальных атрибутов и объявлений пространств имен, но перед всеми остальными объявлениями.  
  
 **Идентификатор ошибки:** BC30617  
  
### Чтобы исправить эту ошибку  
  
-   Переместите оператор `Module` в начало объявления пространства имен или в начало исходного файла.  
  
## См. также  
 [Оператор Module](../../../visual-basic/language-reference/statements/module-statement.md)