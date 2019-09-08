---
title: Практическое руководство. Как генерировать настраиваемый код путем изменения DBML-файла
ms.date: 03/30/2017
ms.assetid: 50ad597a-8598-42d3-82dd-fc7d702ebc37
ms.openlocfilehash: 01890e6b899db6b70049e2d6b8193e5b0f4095fb
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70781979"
---
# <a name="how-to-generate-customized-code-by-modifying-a-dbml-file"></a>Практическое руководство. Как генерировать настраиваемый код путем изменения DBML-файла
Visual Basic или C# исходный код можно создать из файла метаданных на языке разметки базы данных (. DBML). Этот способ предоставляет возможность настройки заданного по умолчанию DBML-файла до создания кода сопоставления приложений. Данная возможность является дополнительной.  
  
 Ниже указаны действия, необходимые для выполнения данного процесса.  
  
1. Создайте DBML-файл.  
  
2. Для изменения DBML-файла используйте редактор. Обратите внимание, что DBML-файл должен проверяться на соответствие файлу [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] определения схемы (XSD) файлам. dbml. Дополнительные сведения см. [в разделе Создание кода в LINQ to SQL](code-generation-in-linq-to-sql.md).  
  
3. Создание Visual Basic или C# исходного кода.  
  
 В следующих примерах используется средства командной строки SQLMetal. Дополнительные сведения см. в разделе [SQLMetal.exe (средство создания кода)](../../../../tools/sqlmetal-exe-code-generation-tool.md).  
  
## <a name="example"></a>Пример  
 В следующем коде DBML-файл создается из учебной базы данных "Northwind". В качестве источника метаданных база данных можно использовать либо имя базы данных, либо имя MDF-файла.  
  
```  
sqlmetal /server:myserver /database:northwind /dbml:mymeta.dbml  
sqlmetal /dbml:mymeta.dbml mydbfile.mdf  
```  
  
## <a name="example"></a>Пример  
 Следующий код создает Visual Basic или C# файл исходного кода из DBML-файла.  
  
```  
sqlmetal /namespace:nwind /code:nwind.vb /language:vb DBMLFile.dbml  
sqlmetal /namespace:nwind /code:nwind.cs /language:csharp DBMLFile.dbml  
```  
  
## <a name="see-also"></a>См. также

- [Создание кода в LINQ to SQL](code-generation-in-linq-to-sql.md)
- [SqlMetal.exe (средство создания кода)](../../../../tools/sqlmetal-exe-code-generation-tool.md)
- [Создание модели объектов](creating-the-object-model.md)
