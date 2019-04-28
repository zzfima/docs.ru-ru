---
title: Практическое руководство. Как генерировать настраиваемый код путем изменения DBML-файла
ms.date: 03/30/2017
ms.assetid: 50ad597a-8598-42d3-82dd-fc7d702ebc37
ms.openlocfilehash: c3fa4d9db4076309ab7d6066cc7072797eaead54
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61877348"
---
# <a name="how-to-generate-customized-code-by-modifying-a-dbml-file"></a>Практическое руководство. Как генерировать настраиваемый код путем изменения DBML-файла
Вы можете создать Visual Basic или C# исходный код из файла метаданных DBML-разметки базы данных. Этот способ предоставляет возможность настройки заданного по умолчанию DBML-файла до создания кода сопоставления приложений. Данная возможность является дополнительной.  
  
 Ниже указаны действия, необходимые для выполнения данного процесса.  
  
1. Создайте DBML-файл.  
  
2. Для изменения DBML-файла используйте редактор. Обратите внимание, что DBML-файл проверен на соответствие файлу определения схемы (XSD) для [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] DBML-файлы. Дополнительные сведения см. в разделе [создание кода в LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/code-generation-in-linq-to-sql.md).  
  
3. Создать в Visual Basic или C# исходный код.  
  
 В следующих примерах используется средства командной строки SQLMetal. Дополнительные сведения см. в разделе [SQLMetal.exe (средство создания кода)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).  
  
## <a name="example"></a>Пример  
 В следующем коде DBML-файл создается из учебной базы данных "Northwind". В качестве источника метаданных база данных можно использовать либо имя базы данных, либо имя MDF-файла.  
  
```  
sqlmetal /server:myserver /database:northwind /dbml:mymeta.dbml  
sqlmetal /dbml:mymeta.dbml mydbfile.mdf  
```  
  
## <a name="example"></a>Пример  
 Следующий код приводит к возникновению ошибки Visual Basic или C# файл исходного кода из DBML-файла.  
  
```  
sqlmetal /namespace:nwind /code:nwind.vb /language:vb DBMLFile.dbml  
sqlmetal /namespace:nwind /code:nwind.cs /language:csharp DBMLFile.dbml  
```  
  
## <a name="see-also"></a>См. также

- [Создание кода в LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/code-generation-in-linq-to-sql.md)
- [SqlMetal.exe (средство создания кода)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md)
- [Создание модели объектов](../../../../../../docs/framework/data/adonet/sql/linq/creating-the-object-model.md)
