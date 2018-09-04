---
title: SQL Server Compact и LINQ to SQL
ms.date: 03/30/2017
ms.assetid: 59022359-a5a2-4c42-9a6a-5c0259c3ad17
ms.openlocfilehash: 1229fcb285038875950776a924870c9be6bef13b
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43529992"
---
# <a name="sql-server-compact-and-linq-to-sql"></a>SQL Server Compact и LINQ to SQL
SQL Server Compact — это база данных по умолчанию, установленные с Visual Studio. Дополнительные сведения см. в разделе [PAVE по с помощью SQL Server Compact (Visual Studio)](https://msdn.microsoft.com/library/13320dd1-94e5-4077-bf76-8df253695ccc).  
  
 В этом разделе описаны основные отличия использования, конфигурации, наборы функций и рамки [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] поддержки.  
  
## <a name="characteristics-of-sql-server-compact-in-relation-to-linq-to-sql"></a>Характеристики SQL Server Compact относительно LINQ to SQL  
 По умолчанию SQL Server Compact установлена для всех выпусков Visual Studio и поэтому доступна на компьютере разработчика для использования с [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]. Однако развертывание приложения, использующего SQL Server Compact и [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] отличается от поведения для приложения SQL Server. SQL Server Compact не является частью платформы .NET Framework. Этот компонент должен быть упакован в состав приложения или загружен отдельно с веб-сайта Майкрософт.  
  
 Обратите внимание на следующие характеристики.  
  
-   SQL Server Compact упаковывается в виде DLL-файла, который может использоваться непосредственно в файлах базы данных (расширение SDF).  
  
-   SQL Server Compact выполняется в том же процессе, что и клиентское приложение. Эффективность взаимодействия с SQL Server Compact, поэтому может быть значительно выше, чем взаимодействие с SQL Server. С другой стороны SQL Server Compact требуется взаимодействие управляемого и неуправляемого кода с сопутствующими расходами.  
  
-   Размер SQL Server Compact библиотеки DLL, мал. Данная возможность сокращает общий размер приложения.  
  
-   Среда выполнения [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] и средство командной строки SQLMetal поддерживают SQL Server Compact.  
  
-   [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] не поддерживает SQL Server Compact.  
  
## <a name="feature-set"></a>Набор возможностей  
 Набор функций SQL Server Compact гораздо проще, чем набор функций SQL Server одним из следующих способов, которые могут повлиять на [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] приложений:  
  
-   SQL Server Compact не поддерживает хранимые процедуры или представления.  
  
-   SQL Server Compact поддерживает только подмножество типов данных и функций SQL.  
  
-   SQL Server Compact поддерживает только подмножество конструкций SQL.  
  
-   SQL Server Compact предоставляет только минимальный оптимизатор. Вполне возможно, что некоторые запросы, время ожидания может истечь.  
  
-   SQL Server Compact не поддерживает частичное доверие.  
  
## <a name="see-also"></a>См. также  
 [Ссылки](../../../../../../docs/framework/data/adonet/sql/linq/reference.md)
