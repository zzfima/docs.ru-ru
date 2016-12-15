---
title: "Переменная &lt;имяПеременной&gt; скрывает содержащуюся в блоке переменную | Microsoft Docs"
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
  - "vbc30616"
  - "bc30616"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30616"
ms.assetid: e7658ebc-da45-451b-a409-a0f8915f0beb
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Переменная &lt;имяПеременной&gt; скрывает содержащуюся в блоке переменную
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Имя переменной, содержащейся в блоке, совпадает с именем другой локальной переменной.  
  
 **Идентификатор ошибки**: BC30616  
  
### Чтобы исправить эту ошибку  
  
-   Переименуйте содержащуюся в блоке переменную так, чтобы ее имя не совпадало с именем какой\-либо другой локальной переменной.  Примеры.  
  
    ```  
    Dim a, b, x As Integer  
    If a = b Then  
       Dim y As Integer = 20 ' Uniquely named block variable.  
    End If  
    ```  
  
-   Основной причиной появления этой ошибки является использование оператора `Catch e As Exception` внутри обработчика событий.  В этом случае назовите переменную блока `Catch` именем `ex` вместо `e`.  
  
-   Еще одной типичной причиной возникновения этой ошибки является попытка обращения к локальной переменной, объявленной в блоке `Try`, из блока `Catch`.  Чтобы исправить ошибку в этом случае, объявите переменную вне структуры `Try...Catch...Finally`.  
  
## См. также  
 [Оператор Try...Catch...Finally](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)   
 [Объявление переменной](../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)