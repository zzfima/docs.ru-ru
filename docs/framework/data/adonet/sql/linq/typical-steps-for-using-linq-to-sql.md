---
title: Стандартная последовательность действий при использовании LINQ to SQL
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-ado
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9a88bd51-bd74-48f7-a9b1-f650e8d55a3e
caps.latest.revision: 4
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload:
- dotnet
ms.openlocfilehash: 31daf8ee10334327070cb5bfc4068bc80e1d7ea4
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="typical-steps-for-using-linq-to-sql"></a>Стандартная последовательность действий при использовании LINQ to SQL
Чтобы реализовать приложение [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], выполните действия, описанные в этом разделе. Обратите внимание, что многие их этих действий являются необязательными. В большинстве случаев можно использовать объектную модель в состоянии, установленном по умолчанию.  
  
 Чтобы ускорить начало работы, создайте объектную модель с помощью среды [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] и начните кодирование запросов.  
  
## <a name="creating-the-object-model"></a>Создание модели объектов  
 Первый шаг состоит в создании модели объектов на основе метаданных существующей реляционной базы данных. Объектная модель представляет базу данных в соответствии с языком программирования, выбранным разработчиком. Дополнительные сведения см. в разделе [LINQ to SQL модель объектов](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md).  
  
### <a name="1-select-a-tool-to-create-the-model"></a>1. Выбор средства для создания модели.  
 Для создания модели предусмотрено три средства.  
  
-   Конструктор [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)]  
  
     Этот конструктор предоставляет многофункциональный пользовательский интерфейс для создания объектной модели из существующей базы данных. Этот инструмент входит в состав интегрированной среды разработки Visual Studio и лучше всего подходит для баз данных небольшого или среднего размера.  
  
-   Средство создания кода SQLMetal  
  
     По своему набору параметров эта программа командной строки несколько отличается от конструктора [!INCLUDE[vs_ordesigner_short](../../../../../../includes/vs-ordesigner-short-md.md)]. Данное средство лучше всего подходит для моделирования больших баз данных. Дополнительные сведения см. в разделе [SQLMetal.exe (средство создания кода)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).  
  
-   Редактор кода  
  
     Можно написать собственный код с помощью редактора кода Visual Studio или другого редактора. Этот подход может привести к большому числу ошибок, поэтому при наличии существующей базы данных, которую можно использовать для создания модели с помощью [!INCLUDE[vs_ordesigner_short](../../../../../../includes/vs-ordesigner-short-md.md)] или программы SQLMetal, использовать его не рекомендуется. Однако редактор кода становится ценным инструментом, когда требуется уточнить или изменить код, уже созданный с помощью других средств. Дополнительные сведения см. в разделе [как: Настройка классов сущностей с помощью редактора кода](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md).  
  
### <a name="2-select-the-kind-of-code-you-want-to-generate"></a>2. Выбор типа кода, который требуется создать.  
  
-   C# или Visual Basic файл исходного кода для сопоставления на основе атрибутов.  
  
     Затем этот файл кода необходимо включить в проект Visual Studio. Дополнительные сведения см. в разделе [сопоставления на основе атрибутов](../../../../../../docs/framework/data/adonet/sql/linq/attribute-based-mapping.md).  
  
-   XML-файл для внешнего сопоставления.  
  
     С помощью этого метода метаданные для сопоставления можно хранить на пределами кода приложения. Дополнительные сведения см. в разделе [внешнего сопоставления](../../../../../../docs/framework/data/adonet/sql/linq/external-mapping.md).  
  
    > [!NOTE]
    >  [!INCLUDE[vs_ordesigner_short](../../../../../../includes/vs-ordesigner-short-md.md)] не поддерживает создание файлов для внешнего сопоставления. Для реализации этой возможности необходимо использовать программу SQLMetal.  
  
-   Файл DBML, который можно изменить перед созданием окончательного файла с исходным кодом.  
  
     Данная возможность является дополнительной.  
  
### <a name="3-refine-the-code-file-to-reflect-the-needs-of-your-application"></a>3. Уточнение файла с исходным кодом в соответствии с потребностями приложения.  
 Для этой цели можно использовать [!INCLUDE[vs_ordesigner_short](../../../../../../includes/vs-ordesigner-short-md.md)] или редактор кода.  
  
## <a name="using-the-object-model"></a>Использование модели объектов  
 На следующем рисунке показана связь между разработчиком и данными в двухуровневом сценарии. Другие сценарии см. в разделе [N-уровневые и удаленные приложения и LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/n-tier-and-remote-applications-with-linq-to-sql.md).  
  
 ![DLinqObjectModel](../../../../../../docs/framework/data/adonet/sql/linq/media/dlinqobjectmodel.png "DLinqObjectModel")  
  
 После создания объектной модели описание запросов на получение сведений и управление данными осуществляется в рамках этой модели. Все операции выполняются в терминах объектов и свойство объектной модели, а не в терминах строк и столбцов базы данных. Работа непосредственно с базой данных не осуществляется.  
  
 Если вы указываете [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] выполнить описанный запрос или вызов `SubmitChanges()` на данных, обработанных, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] взаимодействует с базой данных на языке базы данных.  
  
 Ниже представлены типичные действия, выполняемые при использовании созданной объектной модели.  
  
### <a name="1-create-queries-to-retrieve-information-from-the-database"></a>1. Создание запросов для извлечения сведений из базы данных.  
 Дополнительные сведения см. в разделе [основные принципы запросов](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md) и [примеры запросов](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md).  
  
### <a name="2-override-default-behaviors-for-insert-update-and-delete"></a>2. Переопределение поведения по умолчанию для операций "Insert", "Update" и "Delete".  
 Этот этап является необязательным. Дополнительные сведения см. в разделе [Настройка операций вставки, обновления и удалить](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md).  
  
### <a name="3-set-appropriate-options-to-detect-and-report-concurrency-conflicts"></a>3. Установка соответствующих параметров для обнаружения конфликтов параллелизма и сообщения о них.  
 Можно использовать параметры обработки конфликтов параллелизма, установленные в модели по умолчанию, или изменить их в соответствии с текущими потребностями. Дополнительные сведения см. в разделе [как: укажите каких элементов проверяются на наличие конфликтов параллелизма](../../../../../../docs/framework/data/adonet/sql/linq/how-to-specify-which-members-are-tested-for-concurrency-conflicts.md) и [как: указать, когда возникают исключения параллелизма](../../../../../../docs/framework/data/adonet/sql/linq/how-to-specify-when-concurrency-exceptions-are-thrown.md).  
  
### <a name="4-establish-an-inheritance-hierarchy"></a>4. Создание иерархии наследования.  
 Этот этап является необязательным. Дополнительные сведения см. в разделе [Поддержка наследования](../../../../../../docs/framework/data/adonet/sql/linq/inheritance-support.md).  
  
### <a name="5-provide-an-appropriate-user-interface"></a>5. Предоставление соответствующего пользовательского интерфейса.  
 Этот шаг необязателен. Его выполнение зависит от способа использования приложения.  
  
### <a name="6-debug-and-test-your-application"></a>6. Отладка и тестирование приложения  
 Дополнительные сведения см. в разделе [поддержка отладки](../../../../../../docs/framework/data/adonet/sql/linq/debugging-support.md).  
  
## <a name="see-also"></a>См. также  
 [Начало работы](../../../../../../docs/framework/data/adonet/sql/linq/getting-started.md)  
 [Создание модели объектов](../../../../../../docs/framework/data/adonet/sql/linq/creating-the-object-model.md)  
 [Хранимые процедуры](../../../../../../docs/framework/data/adonet/sql/linq/stored-procedures.md)
