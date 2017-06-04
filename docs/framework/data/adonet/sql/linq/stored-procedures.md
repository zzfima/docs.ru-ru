---
title: "Хранимые процедуры | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 4d23dd7a-a85f-44ff-a717-af7d0950c0fc
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Хранимые процедуры
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] использует методы в объектной модели для представления хранимых процедур в базе данных.  Чтобы задать методы в качестве хранимых процедур, следует применить атрибут <xref:System.Data.Linq.Mapping.FunctionAttribute> и, где необходимо, атрибут <xref:System.Data.Linq.Mapping.ParameterAttribute>.  Дополнительные сведения см. в разделе [Модель объектов LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md).  
  
 Пользователи среды [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)], как правило, пользуются конструктором [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] для сопоставления хранимых процедур. В темах данного раздела показано формирование и вызов этих методов в приложении при самостоятельном написании кода.  
  
## В этом подразделе  
 [Как использовать хранимые процедуры для возвращения](../../../../../../docs/framework/data/adonet/sql/linq/how-to-return-rowsets.md)  
 Содержит сведения о возвращении строк данных и об использовании входного параметра.  
  
 [Как использовать хранимые процедуры, принимающие параметры](../../../../../../docs/framework/data/adonet/sql/linq/how-to-use-stored-procedures-that-take-parameters.md)  
 Содержит сведения об использовании входных и выходных параметров.  
  
 [Как использовать хранимые процедуры, сопоставленные с несколькими результирующими формами](../../../../../../docs/framework/data/adonet/sql/linq/how-to-use-stored-procedures-mapped-for-multiple-result-shapes.md)  
 Содержит сведения о предоставлении возвратов нескольких фигур в одной хранимой процедуре.  
  
 [Как использовать хранимые процедуры, сопоставленные с последовательными результирующими формами](../../../../../../docs/framework/data/adonet/sql/linq/how-to-use-stored-procedures-mapped-for-sequential-result-shapes.md)  
 Содержит сведения о предоставлении нескольких фигур при наличии известной возвращаемой последовательности.  
  
 [Настройка операций с помощью хранимых процедур](../../../../../../docs/framework/data/adonet/sql/linq/customizing-operations-by-using-stored-procedures.md)  
 Содержит описание использования хранимых процедур для выполнения операций вставки, обновления и удаления.  
  
 [Настройка операций с использованием только хранимых процедур](../../../../../../docs/framework/data/adonet/sql/linq/customizing-operations-by-using-stored-procedures-exclusively.md)  
 Содержит описание использования только хранимых процедур для выполнения операций вставки, обновления и удаления.  
  
## Связанные подразделы  
 [Руководство по программированию](../../../../../../docs/framework/data/adonet/sql/linq/programming-guide.md)  
 Содержит сведения о создании и использовании объектной модели [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].  
  
 [Пошаговое руководство. Применение только хранимых процедур \(Visual Basic\)](../../../../../../docs/framework/data/adonet/sql/linq/walkthrough-using-only-stored-procedures-visual-basic.md)  
 Содержит процедуры, в которых показано использование хранимых процедур в Visual Basic.  
  
 [Пошаговое руководство. Использование только хранимых процедур \(C\#\)](../../../../../../docs/framework/data/adonet/sql/linq/walkthrough-using-only-stored-procedures-csharp.md)  
 Содержит процедуры, в которых показано использование хранимых процедур в C\#.