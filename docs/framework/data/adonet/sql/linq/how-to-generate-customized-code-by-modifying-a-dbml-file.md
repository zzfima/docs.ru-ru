---
title: "Практическое руководство. Создание настраиваемого кода за счет изменения файла DBML"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 50ad597a-8598-42d3-82dd-fc7d702ebc37
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 743e938df0b9c7f12a9c3a11a4b5558137add529
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-generate-customized-code-by-modifying-a-dbml-file"></a>Практическое руководство. Создание настраиваемого кода за счет изменения файла DBML
Можно создать [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] или исходного кода C# из файла метаданных DBML-разметки базы данных. Этот способ предоставляет возможность настройки заданного по умолчанию DBML-файла до создания кода сопоставления приложений. Данная возможность является дополнительной.  
  
 Ниже указаны действия, необходимые для выполнения данного процесса.  
  
1.  Создайте DBML-файл.  
  
2.  Для изменения DBML-файла используйте редактор. Обратите внимание, что DBML-файла необходимо проверить соответствие файлу определения (.xsd) схемы для [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] DBML-файлы. Дополнительные сведения см. в разделе [создание кода в LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/code-generation-in-linq-to-sql.md).  
  
3.  Создайте исходный код [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] или C#.  
  
 В следующих примерах используется средства командной строки SQLMetal. Дополнительные сведения см. в разделе [SQLMetal.exe (средство создания кода)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).  
  
## <a name="example"></a>Пример  
 В следующем коде DBML-файл создается из учебной базы данных "Northwind". В качестве источника метаданных база данных можно использовать либо имя базы данных, либо имя MDF-файла.  
  
```  
sqlmetal /server:myserver /database:northwind /dbml:mymeta.dbml  
sqlmetal /dbml:mymeta.dbml mydbfile.mdf  
```  
  
## <a name="example"></a>Пример  
 В следующем коде исходный код [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] или C# создается из DBML-файла.  
  
```  
sqlmetal /namespace:nwind /code:nwind.vb /language:vb DBMLFile.dbml  
sqlmetal /namespace:nwind /code:nwind.cs /language:csharp DBMLFile.dbml  
```  
  
## <a name="see-also"></a>См. также  
 [Создание кода в LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/code-generation-in-linq-to-sql.md)  
 [SqlMetal.exe (средство создания кода)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md)  
 [Создание модели объектов](../../../../../../docs/framework/data/adonet/sql/linq/creating-the-object-model.md)
