---
title: Пошаговое руководство. Управление данными (Visual Basic)
ms.date: 03/30/2017
dev_langs:
- vb
ms.assetid: 1f6a54f6-ec33-452a-a37d-48122207bf14
ms.openlocfilehash: e0bf8b32595f656d3bff424610f193bd84d0f5bd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="walkthrough-manipulating-data-visual-basic"></a>Пошаговое руководство. Управление данными (Visual Basic)
В данном руководстве представлен основной и полный сценарий [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] по добавлению, изменению и удалению данных в базе данных. Для добавления клиента, изменения его имени и удаления заказа следует использовать копию учебной базы данных Northwind.  
  
 [!INCLUDE[note_settings_general](../../../../../../includes/note-settings-general-md.md)]  
  
 Это пошаговое руководство было написано с помощью параметров разработки Visual Basic.  
  
## <a name="prerequisites"></a>Предварительные требования  
 Необходимо выполнить следующие требования.  
  
-   Для хранения файлов используется выделенная папка ("c:\linqtest2"). Прежде чем приступить к выполнению задач, создайте такую папку.  
  
-   Наличие учебной базы данных Northwind.  
  
     Если база данных не установлена на компьютере разработчика, загрузите ее с веб-узла Центра загрузки Майкрософт. Инструкции см. в разделе [Загрузка примеров баз данных](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md). После загрузки базы данных скопируйте файл northwnd.mdf в папку c:\linqtest2.  
  
-   Наличие файла кода Visual Basic, созданного из базы данных "Борей".  
  
     Его можно создать либо помощью оператора [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)], либо с помощью средства SQLMetal. Данное пошаговое руководство было написано с использованием средства SQLMetal со следующей командной строкой:  
  
     **SQLMetal /code:"c:\linqtest2\northwind.vb» / Language: VB «C:\linqtest2\northwnd.mdf» / pluralize**  
  
     Дополнительные сведения см. в разделе [SQLMetal.exe (средство создания кода)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).  
  
## <a name="overview"></a>Обзор  
 Данное пошаговое руководство состоит из шести основных задач.  
  
-   Создание [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] решения в Visual Studio.  
  
-   Добавление файла кода базы данных в проект.  
  
-   Создание нового объекта клиента.  
  
-   Изменение контактного имени клиента.  
  
-   Удаление заказа.  
  
-   Отправка внесенных изменений в базу данных Northwind.  
  
## <a name="creating-a-linq-to-sql-solution"></a>Создание решения LINQ to SQL  
 В первой задаче создается решение Visual Studio, который содержит ссылки, необходимые для построения и запуска [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] проекта.  
  
#### <a name="to-create-a-linq-to-sql-solution"></a>Создание решения LINQ to SQL  
  
1.  В меню **Файл** Visual Studio выберите команду **Создать проект**.  
  
2.  В **типов проектов** в области **новый проект** диалоговое окно, нажмите кнопку **Visual Basic**.  
  
3.  В области **Шаблоны** щелкните **Консольное приложение**.  
  
4.  В **имя** введите **LinqDataManipulationApp**.  
  
5.  Нажмите кнопку **ОК**.  
  
## <a name="adding-linq-references-and-directives"></a>Добавление ссылок и директив LINQ  
 В этом пошаговом руководстве используются сборки, которые могут быть не установлены по умолчанию в проект. Если `System.Data.Linq` не указан в качестве ссылки в проекте (щелкните **Показать все файлы** в **обозревателе решений** и разверните **ссылки** узла), добавьте ее, как описано в следующие шаги.  
  
#### <a name="to-add-systemdatalinq"></a>Добавление сборки System.Data.Linq  
  
1.  В **обозревателе решений**, щелкните правой кнопкой мыши **ссылки**, а затем нажмите кнопку **добавить ссылку**.  
  
2.  В **добавить ссылку** диалоговое окно, нажмите кнопку **.NET**, выберите сборку System.Data.Linq и нажмите кнопку **ОК**.  
  
     Сборка будет добавлена в проект.  
  
3.  В редакторе кода добавьте следующую директиву перед **Module1**:  
  
     [!code-vb[DLinqWalk3VB#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk3VB/vb/Module1.vb#1)]  
  
## <a name="adding-the-northwind-code-file-to-the-project"></a>Добавление файла кода Northwind в проект  
 При выполнении этих действий подразумевается, что для создания файла кода из учебной базы данных Northwind использовалось средство SQLMetal. Дополнительные сведения см. в разделе "Предварительные требования" ранее в этом руководстве.  
  
#### <a name="to-add-the-northwind-code-file-to-the-project"></a>Добавление файла кода northwind в проект  
  
1.  На **проекта** меню, нажмите кнопку **Добавление существующего элемента**.  
  
2.  В **Добавление существующего элемента** диалоговое окно, перейдите к c:\linqtest2\northwind.vb и нажмите кнопку **добавить**.  
  
     Файл northwind.vb будет добавлен в проект.  
  
## <a name="setting-up-the-database-connection"></a>Настройка подключения к базе данных  
 Сначала проверьте подключение к базе данных. Обратите особое внимание, что в имени базы данных - Northwnd - отсутствует буква "i". Если при выполнении следующих действий возникают ошибки, просмотрите файл northwind.vb, чтобы определить написание разделяемого класса Northwind.  
  
#### <a name="to-set-up-and-test-the-database-connection"></a>Настройка и проверка подключения к базе данных  
  
1.  Введите или вставьте следующий код в `Sub Main`.  
  
     [!code-vb[DLinqWalk3VB#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk3VB/vb/Module1.vb#2)]  
  
2.  Чтобы проверить приложение на этом этапе, нажмите клавишу F5.  
  
     Объект **консоли** открывается окно.  
  
     Закройте приложение, нажав клавишу ВВОД в **консоли** окна, или нажав **остановить отладку** в Visual Studio **отладки** меню.  
  
## <a name="creating-a-new-entity"></a>Создание новой сущности  
 Создание новой сущности не представляет особых проблем. Для создания объектов (например, `Customer`) можно использовать ключевое слово `New`.  
  
 В этом и следующих разделах выполняются изменения только локального кэша. Изменения не будут отправлены в базу данных до тех пор, пока ближе к концу данного руководства не будет вызван <xref:System.Data.Linq.DataContext.SubmitChanges%2A>.  
  
#### <a name="to-add-a-new-customer-entity-object"></a>Добавление нового объекта сущностей Customer  
  
1.  Создайте новый `Customer`, добавив перед `Console.ReadLine` в `Sub Main` следующий код.  
  
     [!code-vb[DLinqWalk3VB#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk3VB/vb/Module1.vb#3)]  
  
2.  Нажмите клавишу F5 для отладки решения.  
  
     В окне консоли отображаются следующие результаты.  
  
     `Customers matching CA before insert:`  
  
     `Customer ID: CACTU`  
  
     `Customer ID: RICAR`  
  
     Обратите внимание, что в выходных данных новая строка не отображается. Новые данные еще не были переданы в базу данных.  
  
3.  Нажмите клавишу ВВОД в **консоли** окна, чтобы остановить отладку.  
  
## <a name="updating-an-entity"></a>Обновление сущности  
 При выполнении следующих действий будет извлечен объект `Customer` и изменено одно из его свойств.  
  
#### <a name="to-change-the-name-of-a-customer"></a>Изменение имени клиента  
  
-   Добавьте следующий код перед `Console.ReadLine()`:  
  
     [!code-vb[DLinqWalk3VB#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk3VB/vb/Module1.vb#4)]  
  
## <a name="deleting-an-entity"></a>Удаление сущности  
 Используя тот же самый объект клиента, можно удалить первый заказ.  
  
 В следующем коде показано, как разорвать связь между строками и удалить строку из базы данных.  
  
#### <a name="to-delete-a-row"></a>Удаление строки  
  
-   Добавьте следующий код перед `Console.ReadLine()`.  
  
     [!code-vb[DLinqWalk3VB#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk3VB/vb/Module1.vb#5)]  
  
## <a name="submitting-changes-to-the-database"></a>Отправка изменений в базу данных  
 Последнее действие, необходимое для создания, обновления и удаления объектов, заключается в фактической отправке изменений в базу данных. Без него изменения останутся на локальном уровне и не появятся в результатах запроса.  
  
#### <a name="to-submit-changes-to-the-database"></a>Отправка изменений в базу данных  
  
1.  Вставьте следующий код перед `Console.ReadLine`.  
  
     [!code-vb[DLinqWalk3VB#6](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk3VB/vb/Module1.vb#6)]  
  
2.  Вставьте следующий код (после `SubmitChanges`), чтобы показать результаты до и после отправки изменений.  
  
     [!code-vb[DLinqWalk3VB#7](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk3VB/vb/Module1.vb#7)]  
  
3.  Нажмите клавишу F5 для отладки решения.  
  
     Появится окно консоли со следующими данными.  
  
    ```  
    Customers matching CA before update:  
    Customer ID: CACTU  
    Customer ID: RICAR  
  
    The Order Detail to be deleted is: OrderID = 10643  
  
    Customers matching CA after update:  
    Customer ID: A3VCA  
    Customer ID: CACTU  
    Customer ID: RICAR  
    ```  
  
4.  Нажмите клавишу ВВОД в **консоли** окна, чтобы остановить отладку.  
  
> [!NOTE]
>  После добавления нового клиента путем отправки изменений это решение нельзя повторно выполнить в исходном виде, поскольку этот же клиент не может быть добавлен без изменений. Для повторного выполнения решения измените значение идентификатора добавляемого клиента.  
  
## <a name="see-also"></a>См. также  
 [Обучение с использованием пошаговых руководств](../../../../../../docs/framework/data/adonet/sql/linq/learning-by-walkthroughs.md)
