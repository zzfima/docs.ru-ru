---
title: "Невозможно обратиться к полю &lt;имя&gt;, так как оно является членом поля с типизированным значением &lt;имя&gt; класса &lt;имяКласса&gt;, базовым классом которого является System.MarshalByRefObject | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbc30310"
  - "bc30310"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30310"
ms.assetid: 2aeb8872-7c87-4f01-98ef-9714ba3eebbe
caps.latest.revision: 9
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 9
---
# Невозможно обратиться к полю &lt;имя&gt;, так как оно является членом поля с типизированным значением &lt;имя&gt; класса &lt;имяКласса&gt;, базовым классом которого является System.MarshalByRefObject
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Класс `System.MarshalByRefObject` разрешает приложения, которые поддерживают удаленный доступ к объектам через границы доменов приложения.  Типы, используемые за пределами границ доменов приложений, должны наследоваться от класса `MarshalByRejectObject`.  Состояние объекта не должно копироваться, поскольку члены объекта нельзя использовать вне домена приложения, в котором они были созданы.  
  
 **Идентификатор ошибки**: BC30310  
  
### Чтобы исправить эту ошибку  
  
1.  Проверьте допустимость члена, на который представлена ссылка.  
  
2.  Явно укажите ключевое слово `Me` для члена.  
  
## См. также  
 <xref:System.MarshalByRefObject>   
 [Оператор Dim](../../../visual-basic/language-reference/statements/dim-statement.md)