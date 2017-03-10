---
title: "Операнд оператора AddressOf должен быть именем метода (без скобок) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbc30577"
  - "bc30577"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30577"
ms.assetid: c2c55640-5c61-4e66-97a4-4322020c6001
caps.latest.revision: 10
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 10
---
# Операнд оператора AddressOf должен быть именем метода (без скобок)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Оператор `AddressOf` создает экземпляр делегата процедуры, ссылающийся на указанную процедуру.  Синтаксис выглядит следующим образом:  
  
 `AddressOf` `procedurename`  
  
 Вы поставили скобки вокруг аргумента `AddressOf`, в чем нет необходимости.  
  
 **Идентификатор ошибки**: BC30577  
  
### Чтобы исправить эту ошибку  
  
1.  Удалите скобки вокруг аргумента, который следует за `AddressOf`.  
  
2.  Убедитесь, что аргумент является именем метода.  
  
## См. также  
 [Оператор AddressOf](../../../visual-basic/language-reference/operators/addressof-operator.md)   
 [Делегаты](../../../visual-basic/programming-guide/language-features/delegates/delegates.md)