---
title: ". (Доступ к членам) (язык Entity SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
ms.assetid: 4733e3b2-3efa-4b96-b591-ac31350e96ad
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# . (Доступ к членам) (язык Entity SQL)
Оператор «точка» \(.\) является в языке [!INCLUDE[esql](../../../../../../includes/esql-md.md)] оператором доступа к элементу.  Оператор доступа к элементу можно использовать, чтобы выдавать значение свойства или поля экземпляра структурного типа концептуальной модели.  
  
## Синтаксис  
  
```  
expression.identifier  
```  
  
## Аргументы  
 `expression`  
 Экземпляр структурного типа концептуальной модели.  
  
 `identifier`  
 Свойство или поле, принадлежащее экземпляру объекта.  
  
## Заметки  
 Оператор «точка» \(.\) можно использовать для извлечения полей из записи подобно извлечению свойств сложного типа или типа сущности.  Например, если «n» типа Name является элементом типа Person и «p» является экземпляром типа Person, то@@  «p.n» будет допустимым выражением доступа к элементу, которое выдаст значение типа Name.  
  
 `select p.Name.FirstName from LOB.Person as p`  
  
## См. также  
 [Справочник по Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)