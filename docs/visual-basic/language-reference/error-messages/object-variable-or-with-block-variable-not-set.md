---
title: "Не задана переменная объекта или переменная блока With | Microsoft Docs"
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
  - "vbrID91"
dev_langs: 
  - "VB"
ms.assetid: 2f03e611-f0ed-465c-99a2-a816e034faa3
caps.latest.revision: 9
caps.handback.revision: 7
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Не задана переменная объекта или переменная блока With
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Найдена ссылка на недопустимую переменную.  Чтобы создать объектную переменную, следует объявить ее и затем назначить ей допустимую ссылку на объектную переменную с помощью оператора `Set`.  Аналогичным образом блок `With...End With` необходимо инициализировать посредством выполнения точки входа оператора `With`.  
  
### Чтобы исправить эту ошибку  
  
1.  Убедитесь, что объектная переменная ссылается на допустимый объект, и укажите или задайте повторно ссылку для объекта.  
  
2.  Убедитесь, что для используемой объектной переменной не установлено значение `Nothing`.  
  
3.  Убедитесь, что библиотека объектов, в которой описан объект, была выбрана в диалоговом окне `Add References`.  
  
4.  Убедитесь, что блок `With` инициализируется посредством выполнения точки входа оператора `With`.  
  
## См. также  
 [Объявление переменных объектов](../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)   
 [Оператор With...End With](../../../visual-basic/language-reference/statements/with-end-with-statement.md)