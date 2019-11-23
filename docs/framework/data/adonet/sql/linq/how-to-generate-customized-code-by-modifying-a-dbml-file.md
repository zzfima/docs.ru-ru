---
title: Практическое руководство. Создание настраиваемого кода за счет изменения файла DBML
ms.date: 03/30/2017
ms.assetid: 50ad597a-8598-42d3-82dd-fc7d702ebc37
ms.openlocfilehash: 6619f4b8c0a47b36a0b84fa21bab4109d26ef895
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/07/2019
ms.locfileid: "72002952"
---
# <a name="how-to-generate-customized-code-by-modifying-a-dbml-file"></a>Практическое руководство. Создание настраиваемого кода за счет изменения файла DBML
Visual Basic или C# исходный код можно создать из файла метаданных на языке разметки базы данных (. DBML). Этот способ предоставляет возможность настройки заданного по умолчанию DBML-файла до создания кода сопоставления приложений. Данная возможность является дополнительной.  
  
 Ниже указаны действия, необходимые для выполнения данного процесса.  
  
1. Создайте DBML-файл.  
  
2. Для изменения DBML-файла используйте редактор. Обратите внимание, что DBML-файл должен проверяться на соответствие файлу определения схемы (XSD) для файлов [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]. dbml. Дополнительные сведения см. [в разделе Создание кода в LINQ to SQL](code-generation-in-linq-to-sql.md).  
  
3. Создание Visual Basic или C# исходного кода.  
  
 В следующих примерах используется средства командной строки SQLMetal. Дополнительные сведения см. в разделе [SQLMetal.exe (средство создания кода)](../../../../tools/sqlmetal-exe-code-generation-tool.md).  
  
## <a name="example"></a>Пример  
 В следующем коде DBML-файл создается из учебной базы данных "Northwind". В качестве источника метаданных база данных можно использовать либо имя базы данных, либо имя MDF-файла.  
  
```console  
sqlmetal /server:myserver /database:northwind /dbml:mymeta.dbml  
sqlmetal /dbml:mymeta.dbml mydbfile.mdf  
```  
  
## <a name="example"></a>Пример  
 Следующий код создает Visual Basic или C# файл исходного кода из DBML-файла.  
  
```console
sqlmetal /namespace:nwind /code:nwind.vb /language:vb DBMLFile.dbml  
sqlmetal /namespace:nwind /code:nwind.cs /language:csharp DBMLFile.dbml  
```  
  
## <a name="see-also"></a>См. также:

- [Создание кода в LINQ to SQL](code-generation-in-linq-to-sql.md)
- [SqlMetal.exe (средство создания кода)](../../../../tools/sqlmetal-exe-code-generation-tool.md)
- [Создание модели объектов](creating-the-object-model.md)
