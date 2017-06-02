---
title: "Поддержка наследования | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 19bb2794-b4e7-402e-8307-1d1517381a08
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Поддержка наследования
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] поддерживает *однотабличное сопоставление*.  Другими словами, в одной таблице базы данных хранится полная иерархия наследования.  Таблица содержит плоское объединение всех возможных столбцов данных для всей иерархии.  \(Объединение является результатом сочетания двух таблиц в одной, в которой имеются строки любой из исходных таблиц.\) Каждая строка в столбцах содержит значения NULL, которые не применяются к типу экземпляра, представленного строкой.  
  
 Стратегия однотабличного сопоставления представляет собой простейшее представление наследования и обеспечивает высокую производительность для многих различных категорий запросов.  
  
 Чтобы реализовать данное сопоставление в [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], в корневом классе иерархии наследования необходимо указать атрибуты и свойства атрибутов.  Дополнительные сведения см. в разделе [Как сопоставить иерархии наследования](../../../../../../docs/framework/data/adonet/sql/linq/how-to-map-inheritance-hierarchies.md).  
  
 Для сопоставления иерархий наследования пользователь среды [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] может также воспользоваться [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)].  
  
## См. также  
 [Дополнительные сведения](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)