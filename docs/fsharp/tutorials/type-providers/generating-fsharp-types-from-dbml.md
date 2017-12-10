---
title: "Пошаговое руководство. Создание типов F# из файла схемы DBML (F#)"
description: "Узнайте, как создание типов F # для данных из базы данных в F # 3.0 при наличии сведений о схеме, закодированные в DBML-файла."
keywords: "visual f#, f#, функциональное программирование"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 6fbb6ccc-248f-4226-95e9-f6f99541dbe4
ms.openlocfilehash: a919c2acb2b5b8c2ce93124f2f541bd092d15c35
ms.sourcegitcommit: 685143b62385500f59bc36274b8adb191f573a16
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/09/2017
---
# <a name="walkthrough-generating-f-types-from-a-dbml-file"></a>Пошаговое руководство. Создание типов F# из файла схемы DBML

> [!NOTE]
В этом руководстве, была написана для F # 3.0 и будут обновлены.  Актуальные сведения о кроссплатформенных поставщиках типов см. в описании [FSharp.Data](http://fsharp.github.io/FSharp.Data/).

> [!NOTE]
Справочные ссылки API, вы перейдете MSDN.  Работа над справочником по API docs.microsoft.com не завершена.

В этом пошаговом руководстве для F # 3.0 описывается создание типов для данных из базы данных, при наличии сведений о схеме, закодированные в DBML-файла. LINQ to SQL используется этот формат для представления схемы базы данных. LINQ to SQL-файл схемы в Visual Studio можно создать с помощью конструктора реляционных объектов (O/R). Дополнительные сведения см. в разделе [Общие сведения о конструкторе O/R](https://msdn.microsoft.com/library/bb384511.aspx) и [создание кода в LINQ to SQL](../../../../docs/framework/data/adonet/sql/linq/index.md).

Поставщик типов языка разметки баз данных (DBML) можно написать код, который использует типы в зависимости от схемы базы данных без необходимости указания статической строки соединения во время компиляции. Который может быть полезным, если требуется возможность того, что конечного приложения будет использовать другую базу данных, другие учетные данные или другую строку соединения чем тот, который используется для разработки приложения. При наличии подключения прямых базы данных, можно использовать во время компиляции, и это же базы данных и учетные данные, которые будут занимать построения приложения, также можно использовать поставщика типов SQLDataConnection. Дополнительные сведения см. в разделе [Пошаговое руководство: доступ к базе данных SQL с помощью поставщиков типов](accessing-a-sql-database.md).

В данном пошаговом руководстве рассмотрены следующие задачи. Они должны выполнить в указанном порядке для данного пошагового руководства для успешного выполнения:


- Создание DBML-файла
<br />

- Создание и настройка проекта F #
<br />

- Настройка поставщика типов и Создание типов
<br />

- Запрос к базе данных
<br />


## <a name="prerequisites"></a>Предварительные требования

## <a name="creating-a-dbml-file"></a>Создание DBML-файла
Если базы данных для проверки на нет, создайте его в соответствии с инструкциями в нижней части [Пошаговое руководство: доступ к базе данных SQL с помощью поставщиков типов](accessing-a-sql-database.md). Если вы выполните следующие действия, вы создадите базу данных с именем MyDatabase, который содержит несколько простых таблиц и хранимых процедур в SQL Server.

Если уже имеется DBML-файла, можно перейти к разделе **создать и установить копию проекта F #**. В противном случае можно создать DBML-файла, заданному существующей базы данных SQL и с помощью командной строки программу SqlMetal.exe.


#### <a name="to-create-a-dbml-file-by-using-sqlmetalexe"></a>Создание DBML-файла с помощью SqlMetal.exe

1. Откройте **Командная строка разработчика**.
<br />

2. Убедитесь, что доступ к SqlMetal.exe, введя `SqlMetal.exe /?` в командной строке. SqlMetal.exe обычно устанавливается в **пакеты SDK** папки в **Program Files** или **Program Files (x86)**.
<br />

3. Запустите SqlMetal.exe со следующими параметрами командной строки. Подставьте вместо правильный путь `c:\destpath` создать DBML-файла и вставить соответствующие значения для сервера базы данных, имя экземпляра и имя базы данных.
<br />

```
  SqlMetal.exe /sprocs /dbml:C:\destpath\MyDatabase.dbml /server:SERVER\INSTANCE /database:MyDatabase
```

>[!NOTE]
Если SqlMetal.exe проблемы при создании файла из-за проблем с разрешениями, сменить текущий каталог, в папку, которая имеет доступ на запись к.


4. Вы также можете изучить другие доступные параметры командной строки. Например существуют параметры, которые можно использовать, если требуется, представления и функции SQL, включенные в создаваемых типов. Дополнительные сведения см. в разделе [SqlMetal.exe &#40; Средство создания кода &#41; ](https://msdn.microsoft.com/library/bb386987).
<br />


## <a name="creating-and-setting-up-an-f-project"></a>Создание и настройка проекта F #
На этом шаге создайте проект и добавляются необходимые ссылки на использование поставщика типов DBML.


#### <a name="to-create-and-set-up-an-f-project"></a>Действия для создания и настройки проекта F#

1. Добавьте новый проект консольного приложения F # в решение.
<br />

2. В **обозревателе решений**, откройте контекстное меню для **ссылки**и нажмите кнопку **добавить ссылку**.
<br />

3. В **сборки** области, выберите **Framework** узел и выберите в списке доступных сборок **System.Data** и **System.Data.Linq**  сборки.
<br />

4. В **сборки** области, выберите **расширения**и выберите в списке доступных сборок **FSharp.Data.TypeProviders**.
<br />

5. Выберите **ОК** кнопку, чтобы добавить ссылки на следующие сборки в проект.
<br />

6. (Необязательно). Скопируйте DBML-файл, созданный на предыдущем шаге и вставьте файл в главной папке проекта. Эта папка содержит файл проекта (.fsproj) и файлы кода. В строке меню выберите **проекта**, **Добавление существующего элемента**, а затем укажите DBML-файл, чтобы добавить его в проект. Если вы выполните следующие действия, можно опустить параметр static ResolutionFolder на следующем шаге.
<br />

## <a name="configuring-the-type-provider"></a>Настройка поставщика типов
В этом разделе вы создать поставщик типов и Создание типов в схеме, описанной в DBML-файл.


#### <a name="to-configure-the-type-provider-and-generate-the-types"></a>Настройка поставщика типов и Создание типов

- Добавьте код, который открывает **TypeProviders** пространства имен и создает экземпляр поставщика типов для DBML-файла, который вы хотите использовать. Если вы добавили DBML-файл в проект, можно опустить параметр static ResolutionFolder.
<br />

```fsharp
open Microsoft.FSharp.Data.TypeProviders


type dbml = DbmlFile<"MyDatabase.dbml", ResolutionFolder = @"<path-to-folder-that-contains-.dbml-file>">

// This connection string can be specified at run time.
let connectionString = "Data Source=MYSERVER\INSTANCE;Initial Catalog=MyDatabase;Integrated Security=SSPI;"
let dataContext = new dbml.Mydatabase(connectionString)
```

Предоставляет доступ к созданным типам тип DataContext и наследует от `System.Data.Linq.DataContext`. Поставщик типов DbmlFile имеет различные статических параметров, задаваемых пользователем. Например, можно использовать другое имя для типа DataContext, указав `DataContext=MyDataContext`. В этом случае ваш код напоминает приведенный ниже:
<br />

```fsharp
open Microsoft.FSharp.Data.TypeProviders


type dbml = DbmlFile<"MyDatabase.dbml", ContextTypeName = "MyDataContext">

// This connection string can be specified at run time.
let connectionString = "Data Source=MYSERVER\INSTANCE;Initial Catalog=MyDatabase;Integrated Security=SSPI;"
let db = new dbml.MyDataContext(connectionString)
```

## <a name="querying-the-database"></a>Запрос к базе данных
В этом разделе используются выражения запросов F # запросов к базе данных.


#### <a name="to-query-the-data"></a>Действия для запроса данных

- Добавьте код для запроса к базе данных.
<br />

```fsharp
  query {
    for row in db.Table1 do
    where (row.TestData1 > 2)
    select row
  } |> Seq.iter (fun row -> printfn "%d %s" row.TestData1 row.Name)
```

## <a name="next-steps"></a>Дальнейшие действия
Можно продолжить использовать другие выражения запроса, или получить из контекста данных подключения к базе данных и выполнения обычных операций с данными ADO.NET. Для выполнения дополнительных действий см. в разделах после «Запроса данных» в [Пошаговое руководство: доступ к базе данных SQL с помощью поставщиков типов](accessing-a-sql-database.md).


## <a name="see-also"></a>См. также
[Поставщик типов DbmlFile](https://msdn.microsoft.com/visualfsharpdocs/conceptual/dbmlfile-type-provider-%5bfsharp%5d)

[Поставщики типов](index.md)

[Пошаговое руководство. Доступ к базе данных SQL с помощью поставщиков типов](accessing-a-sql-database.md)

[SqlMetal.exe &#40; Средство создания кода &#41;](https://msdn.microsoft.com/library/bb386987)

[Выражения запросов](../../language-reference/query-expressions.md)
