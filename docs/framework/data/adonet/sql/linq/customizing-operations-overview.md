---
title: "Настройка операций. Общие сведения | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: a3546296-1443-4b88-aa6e-d41011041ba7
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Настройка операций. Общие сведения
По умолчанию [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] создает динамический код SQL для операций вставки, обновления и удаления на основе сопоставления. Однако на практике часто приходится добавлять собственную бизнес\-логику для обеспечения безопасности, выполнения проверок и т. д.  
  
 Ниже перечислены возможности, предоставляемые методами [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] для настройки этих операций.  
  
## Возможности загрузки  
 В запросах можно определять, какой объем данных, связанных с основными целевыми объектами, должен извлекаться при подключении к базе данных.  Эта функциональная возможность реализуется, в первую очередь, посредством использования параметров <xref:System.Data.Linq.DataLoadOptions>.  Для получения дополнительной информации см. [Сравнение отложенной и немедленной загрузки](../../../../../../docs/framework/data/adonet/sql/linq/deferred-versus-immediate-loading.md).  
  
## Разделяемые методы  
 При использовании сопоставления по умолчанию технология [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] предоставляет разделяемые методы, которые можно использовать для реализации пользовательской бизнес\-логики.  Для получения дополнительной информации см. [Добавление бизнес\-логики с помощью разделяемых методов](../../../../../../docs/framework/data/adonet/sql/linq/adding-business-logic-by-using-partial-methods.md).  
  
## Хранимые процедуры и пользовательские функции  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] поддерживает использование хранимых процедур и пользовательских функций.  Хранимые процедуры часто используются для настройки операций.  Для получения дополнительной информации см. [Хранимые процедуры](../../../../../../docs/framework/data/adonet/sql/linq/stored-procedures.md).  
  
## См. также  
 [Настройка операций вставки, обновления и удаления](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md)