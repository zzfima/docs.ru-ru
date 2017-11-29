---
title: "Канонические функции"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bbcc9928-36ea-4dff-9e31-96549ffed958
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: b80eeedc67678d703664eb705408a72b7e4a2274
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="canonical-functions"></a>Канонические функции
В этом разделе обсуждаются канонические функции, которые поддерживаются всеми поставщиками данных и могут использоваться всеми технологиями запросов. Канонические функции не могут расширяться поставщиком.  
  
 Эти канонические функции будут преобразованы в соответствующие функции источника данных для поставщика. Это позволит формулировать вызовы функций в формате, общем для разных источников данных.  
  
 Эти канонические функции не зависят от типа источника данных, поэтому для них типы аргументов и возвращаемых значений определяются в терминах типов, доступных в концептуальной модели. Однако некоторые источники данных поддерживают не все типы в концептуальной модели.  
  
 При использовании в запросе [!INCLUDE[esql](../../../../../../includes/esql-md.md)] канонической функции будет вызвана соответствующая функция в источнике данных.  
  
 Во всех канонических функциях явным образом определяется обработка входных значений NULL и условия возникновения ошибок. Поставщики хранилищ должны соответствовать этому требованию, однако [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] не контролирует это соответствие.  
  
 Для сценариев LINQ запросы к [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] включают сопоставление методов CLR с методами в базовом источнике данных. Методы CLR сопоставляются с каноническими функциями, и поэтому правильное сопоставление возможно для любого набора методов, независимо от источника данных.  
  
## <a name="canonical-functions-namespace"></a>Пространство имен канонических функций  
 Для канонических функций выделено пространство имен <xref:System.Data.Metadata.Edm>. Пространство имен <xref:System.Data.Metadata.Edm> автоматически включается во все запросы. Однако при импорте другого пространства имен, в котором содержится функция с именем, совпадающим с именем канонической функции (из пространства имен <xref:System.Data.Metadata.Edm>), то пространство имен необходимо указывать явным образом.  
  
## <a name="in-this-section"></a>Содержание  
 [Канонические статистические функции](../../../../../../docs/framework/data/adonet/ef/language-reference/aggregate-canonical-functions.md)  
 Обсуждаются статистические канонические функции языка [!INCLUDE[esql](../../../../../../includes/esql-md.md)].  
  
 [Математические канонические функции](../../../../../../docs/framework/data/adonet/ef/language-reference/math-canonical-functions.md)  
 Обсуждаются математические канонические функции языка [!INCLUDE[esql](../../../../../../includes/esql-md.md)].  
  
 [Строковые канонические функции](../../../../../../docs/framework/data/adonet/ef/language-reference/string-canonical-functions.md)  
 Обсуждаются строковые канонические функции языка [!INCLUDE[esql](../../../../../../includes/esql-md.md)].  
  
 [Канонические функции даты и времени](../../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)  
 Обсуждаются канонические функции даты и времени в языке [!INCLUDE[esql](../../../../../../includes/esql-md.md)].  
  
 [Побитовое канонические функции](../../../../../../docs/framework/data/adonet/ef/language-reference/bitwise-canonical-functions.md)  
 Обсуждаются побитовые канонические функции языка [!INCLUDE[esql](../../../../../../includes/esql-md.md)].  
  
 [Пространственные функции](../../../../../../docs/framework/data/adonet/ef/language-reference/spatial-functions.md)  
 Рассматриваются пространственные канонические функции языка [!INCLUDE[esql](../../../../../../includes/esql-md.md)].  
  
 [Другие канонические функции](../../../../../../docs/framework/data/adonet/ef/language-reference/other-canonical-functions.md)  
 Обсуждаются функции, которые не являются побитовыми, строковыми, математическими, статистическими или функциями даты-времени.  
  
## <a name="see-also"></a>См. также  
 [Общие сведения об Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)  
 [Справочник по Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [Концептуальная модель с сопоставление функций SQL Server](../../../../../../docs/framework/data/adonet/ef/conceptual-model-canonical-to-sql-server-functions-mapping.md)  
 [Определяемые пользователем функции](../../../../../../docs/framework/data/adonet/ef/language-reference/user-defined-functions-entity-sql.md)
