---
title: "SQL Server Compact и LINQ to SQL | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 59022359-a5a2-4c42-9a6a-5c0259c3ad17
caps.latest.revision: 5
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 5
---
# SQL Server Compact и LINQ to SQL
SQL Server Compact \- база данных по умолчанию, устанавливаемая вместе с Visual Studio. Дополнительные сведения см. в разделе [PAVE OVER Using SQL Server Compact \(Visual Studio\)](http://msdn.microsoft.com/ru-ru/13320dd1-94e5-4077-bf76-8df253695ccc).  
  
 В этом разделе описаны основные отличия в использовании, настройке, наборе функций и области применения поддержки [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].  
  
## Характеристики SQL Server Compact относительно LINQ to SQL  
 По умолчанию SQL Server Compact установлена для всех выпусков [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] и поэтому доступна для использования c [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] на компьютере разработчика.  Однако развертывание приложения, использующего SQL Server Compact и [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], отличается от развертывания приложения [!INCLUDE[ssNoVersion](../../../../../../includes/ssnoversion-md.md)].  SQL Server Compact не является частью платформы .NET Framework. Этот компонент должен быть упакован в состав приложения или загружен отдельно с веб\-сайта Майкрософт.  
  
 Обратите внимание на следующие характеристики.  
  
-   SQL Server Compact упаковывается в виде DLL\-файла, который может использоваться непосредственно в файлах базы данных \(расширение SDF\).  
  
-   SQL Server Compact выполняется в тех же процессах, что и клиентское приложение.  Следовательно, эффективность взаимодействия с SQL Server Compact может быть значительно выше, чем с [!INCLUDE[ssNoVersion](../../../../../../includes/ssnoversion-md.md)].  С другой стороны, для SQL Server Compact не требуется взаимодействие управляемого и неуправляемого кода с сопутствующими расходами.  
  
-   Размер DLL\-библиотеки SQL Server Compact невелик.  Данная функция сокращает общий размер приложения.  
  
-   Среда выполнения [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] и средство командной строки SQLMetal поддерживают SQL Server Compact.  
  
-   [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] не поддерживает SQL Server Compact.  
  
## Набор функций  
 Набор функций SQL Server Compact гораздо проще набора [!INCLUDE[ssNoVersion](../../../../../../includes/ssnoversion-md.md)] в отношении способов, которые могут повлиять на приложения [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].  
  
-   SQL Server Compact не поддерживает хранимые процедуры или представления.  
  
-   SQL Server Compact поддерживает только подмножество типов данных и функций SQL.  
  
-   SQL Server Compact поддерживает только подмножество конструкций SQL.  
  
-   SQL Server Compact предоставляет только минимальный оптимизатор.  Существует возможность истечения времени ожидания некоторых запросов.  
  
-   SQL Server Compact не поддерживает частичное доверие.  
  
## См. также  
 [Ссылки](../../../../../../docs/framework/data/adonet/sql/linq/reference.md)