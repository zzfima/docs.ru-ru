---
title: "SQL Server Compact и LINQ to SQL"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 59022359-a5a2-4c42-9a6a-5c0259c3ad17
caps.latest.revision: "5"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 2717a94228dc1be8da0d84179201747d60c896a5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="sql-server-compact-and-linq-to-sql"></a>SQL Server Compact и LINQ to SQL
SQL Server Compact — база данных по умолчанию, устанавливается вместе с Visual Studio. Дополнительные сведения см. в разделе [PAVE по с помощью SQL Server Compact (Visual Studio)](http://msdn.microsoft.com/en-us/13320dd1-94e5-4077-bf76-8df253695ccc).  
  
 В этом разделе описаны основные отличия в использовании, конфигурации, наборы функций и области [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] поддержки.  
  
## <a name="characteristics-of-sql-server-compact-in-relation-to-linq-to-sql"></a>Характеристики SQL Server Compact относительно LINQ to SQL  
 По умолчанию SQL Server Compact устанавливаются для всех [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] выпуски и поэтому доступна на компьютере разработчика для использования с [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]. Однако развертывание приложения, использующего SQL Server Compact и [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] отличается от [!INCLUDE[ssNoVersion](../../../../../../includes/ssnoversion-md.md)] приложения. SQL Server Compact не является частью платформы .NET Framework. Этот компонент должен быть упакован в состав приложения или загружен отдельно с веб-сайта Майкрософт.  
  
 Обратите внимание на следующие характеристики.  
  
-   SQL Server Compact упаковывается в виде DLL-файла, который может использоваться непосредственно в файлах базы данных (расширение SDF).  
  
-   SQL Server Compact выполняется в том же процессе, что и клиентское приложение. Эффективность взаимодействия с SQL Server Compact, поэтому может быть значительно выше, чем с [!INCLUDE[ssNoVersion](../../../../../../includes/ssnoversion-md.md)]. С другой стороны SQL Server Compact требуется взаимодействие управляемого и неуправляемого кода с сопутствующими расходами.  
  
-   Устанавливается малый размер SQL Server Compact библиотеки DLL. Данная возможность сокращает общий размер приложения.  
  
-   Среда выполнения [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] и средство командной строки SQLMetal поддерживают SQL Server Compact.  
  
-   [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] не поддерживает SQL Server Compact.  
  
## <a name="feature-set"></a>Набор возможностей  
 Набор компонентов SQL Server Compact гораздо проще, чем набор функциональных возможностей [!INCLUDE[ssNoVersion](../../../../../../includes/ssnoversion-md.md)] одним из следующих способов, которые могут повлиять на [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] приложений:  
  
-   SQL Server Compact не поддерживает хранимые процедуры или представления.  
  
-   SQL Server Compact поддерживает только подмножество типов данных и функций SQL.  
  
-   SQL Server Compact поддерживает только подмножество конструкций SQL.  
  
-   SQL Server Compact предоставляет только минимальный оптимизатор. Это возможно, что некоторые запросы, время ожидания может истечь.  
  
-   SQL Server Compact не поддерживает частичное доверие.  
  
## <a name="see-also"></a>См. также  
 [Ссылки](../../../../../../docs/framework/data/adonet/sql/linq/reference.md)
