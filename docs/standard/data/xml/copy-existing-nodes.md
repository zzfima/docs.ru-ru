---
title: "Копирование существующих узлов | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
ms.assetid: 2aa8f65c-cc62-4638-9c46-129dc15be786
caps.latest.revision: 3
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 3
---
# Копирование существующих узлов
Модель XML DOM имеет множество методов и свойств, которые можно использовать для выбора узла, например **SelectSingleNode**, **ChildNodes\[int i\]**, **Attributes\[int i\]**.  После выбора узла его можно вставить в дерево с помощью одного из методов вставки, допустимых для данного типа узла.  Единственное ограничение при выполнении операции вставки узла в дерево состоит в том, что по ее завершении документ должен оставаться документом правильного формата.  При вставке существующего узла в дерево DOM узел удаляется из своей исходной позиции и добавляется в целевую позицию.  
  
## См. также  
 [Модель DOM для XML](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)