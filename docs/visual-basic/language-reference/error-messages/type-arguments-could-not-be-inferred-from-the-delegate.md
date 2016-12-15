---
title: "Аргументы типа не могут быть выведены от делегата | Microsoft Docs"
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
  - "bc36564"
  - "vbc36564"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC36564"
ms.assetid: 21312807-e1cd-4ac1-ae1c-c28a9c25164d
caps.latest.revision: 5
caps.handback.revision: 5
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Аргументы типа не могут быть выведены от делегата
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Оператор присваивания использует `AddressOf`, чтобы присвоить адрес универсальной процедуры делегату, но он не поддерживает все аргументы типа универсальной процедуры.  
  
 Как правило, при вызове универсального типа, указывается аргумент типа для каждого параметра типа, определяемого этим универсальным типом.  Если вы не передаете аргументы типа, компилятор пытается определить типы, которые должны быть переданы параметрам типа.  Если контекст не предоставляет достаточно сведений компилятору для определения типов, возникает ошибка.  
  
 **Идентификатор ошибки**: BC36564  
  
### Чтобы исправить эту ошибку  
  
-   Укажите аргументы типа для универсальной процедуры в выражении `AddressOf`.  
  
## См. также  
 [Универсальные типы в Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)   
 [Оператор AddressOf](../../../visual-basic/language-reference/operators/addressof-operator.md)   
 [Универсальные процедуры в Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-procedures.md)   
 [Список типов](../../../visual-basic/language-reference/statements/type-list.md)   
 [Методы расширения](../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)