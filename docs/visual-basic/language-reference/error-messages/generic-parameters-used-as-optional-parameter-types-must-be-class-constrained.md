---
title: "Универсальные параметры, используемые как типы необязательных параметров, должны быть ограничены классом | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbc32124"
  - "bc32124"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC32124"
ms.assetid: 55aa8b2a-9ce3-4620-a710-2f9b0feb6143
caps.latest.revision: 8
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 8
---
# Универсальные параметры, используемые как типы необязательных параметров, должны быть ограничены классом
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Процедура объявлена с дополнительным параметром, использующим параметр типа, который не обязательно должен быть ссылочного типа.  
  
 Для каждого дополнительного параметра всегда необходимо указывать значение по умолчанию.  Если параметр имеет ссылочный тип, дополнительное значение должно быть `Nothing`, которое является допустимым для любого ссылочного типа.  Тем не менее, если параметр имеет тип значения, этот тип должен иметь простой тип данных, предустановленный в Visual Basic.  Это происходит потому, что составные типы значения, например структуры, определенные пользователем, не имеют допустимого значения по умолчанию.  
  
 При использовании параметра типа для дополнительного параметра необходимо, чтобы он был ссылочного типа во избежание наличия типа значения без допустимого значения по умолчанию.  Это означает, что необходимо ограничить параметр типа ключевым словом `Class` или при помощи имени определенного класса.  
  
 **Идентификатор ошибки:** BC32124  
  
### Чтобы исправить эту ошибку  
  
-   Ограничьте параметр типа принятием только ссылочного типа, или не используйте его для дополнительного параметра.  
  
## См. также  
 [Универсальные типы в Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)   
 [Список типов](../../../visual-basic/language-reference/statements/type-list.md)   
 [Оператор Class](../../../visual-basic/language-reference/statements/class-statement.md)   
 [Необязательные параметры](../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md)   
 [Структуры](../../../visual-basic/programming-guide/language-features/data-types/structures.md)   
 [Nothing](../../../visual-basic/language-reference/nothing.md)