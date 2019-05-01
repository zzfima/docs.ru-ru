---
title: Создание таблицы данных
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: eecf9d78-60e3-4fdc-8de0-e56c13a89414
ms.openlocfilehash: 272976d3c581d3e8a5860ba5cf3f9695ca370d8c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62034415"
---
# <a name="creating-a-datatable"></a><span data-ttu-id="0adc7-102">Создание таблицы данных</span><span class="sxs-lookup"><span data-stu-id="0adc7-102">Creating a DataTable</span></span>
<span data-ttu-id="0adc7-103">Объект <xref:System.Data.DataTable>, который представляет одну таблицу находящихся в памяти реляционных данных, может создаваться и использоваться независимо или использоваться другими объектами .NET Framework, чаще всего как член <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="0adc7-103">A <xref:System.Data.DataTable>, which represents one table of in-memory relational data, can be created and used independently, or can be used by other .NET Framework objects, most commonly as a member of a <xref:System.Data.DataSet>.</span></span>  
  
 <span data-ttu-id="0adc7-104">Можно создать **DataTable** объекта, используя соответствующую **DataTable** конструктор.</span><span class="sxs-lookup"><span data-stu-id="0adc7-104">You can create a **DataTable** object by using the appropriate **DataTable** constructor.</span></span> <span data-ttu-id="0adc7-105">Вы можете добавить его **набора данных** с помощью **добавить** метод, чтобы добавить его **DataTable** объекта **таблиц** коллекции.</span><span class="sxs-lookup"><span data-stu-id="0adc7-105">You can add it to the **DataSet** by using the **Add** method to add it to the **DataTable** object's **Tables** collection.</span></span>  
  
 <span data-ttu-id="0adc7-106">Вы также можете создать **DataTable** объектов в рамках **набора данных** с помощью **заполнения** или **FillSchema** методы  **DataAdapter** объекта, или из предварительно определенных или выводимым XML-схемы с помощью **ReadXml**, **ReadXmlSchema**, или **InferXmlSchema** методы **набора данных**.</span><span class="sxs-lookup"><span data-stu-id="0adc7-106">You can also create **DataTable** objects within a **DataSet** by using the **Fill** or **FillSchema** methods of the **DataAdapter** object, or from a predefined or inferred XML schema using the **ReadXml**, **ReadXmlSchema**, or **InferXmlSchema** methods of the **DataSet**.</span></span> <span data-ttu-id="0adc7-107">Обратите внимание, что после добавления **DataTable** членом **таблиц** коллекцию из одного **набора данных**, не может добавить его в коллекцию таблиц любые другие **Набора данных**.</span><span class="sxs-lookup"><span data-stu-id="0adc7-107">Note that after you have added a **DataTable** as a member of the **Tables** collection of one **DataSet**, you cannot add it to the collection of tables of any other **DataSet**.</span></span>  
  
 <span data-ttu-id="0adc7-108">При первом создании **DataTable**, он не имеет схемы (т. е. структуры).</span><span class="sxs-lookup"><span data-stu-id="0adc7-108">When you first create a **DataTable**, it does not have a schema (that is, a structure).</span></span> <span data-ttu-id="0adc7-109">Чтобы определить схему таблицы, необходимо создать и добавить <xref:System.Data.DataColumn> объектов **столбцы** коллекции таблицы.</span><span class="sxs-lookup"><span data-stu-id="0adc7-109">To define the schema of the table, you must create and add <xref:System.Data.DataColumn> objects to the **Columns** collection of the table.</span></span> <span data-ttu-id="0adc7-110">Можно также определить столбец первичного ключа для таблицы и создать и добавить **ограничение** объектов **ограничения** коллекции таблицы.</span><span class="sxs-lookup"><span data-stu-id="0adc7-110">You can also define a primary key column for the table, and create and add **Constraint** objects to the **Constraints** collection of the table.</span></span> <span data-ttu-id="0adc7-111">После определения схемы для **DataTable**, можно добавлять строки данных в таблицу, добавив **DataRow** объектов **строк** коллекции таблицы.</span><span class="sxs-lookup"><span data-stu-id="0adc7-111">After you have defined the schema for a **DataTable**, you can add rows of data to the table by adding **DataRow** objects to the **Rows** collection of the table.</span></span>  
  
 <span data-ttu-id="0adc7-112">Вы не обязаны предоставить значение для <xref:System.Data.DataTable.TableName%2A> свойства при создании **DataTable**; можно указать свойство в другое время, или оставить его пустым.</span><span class="sxs-lookup"><span data-stu-id="0adc7-112">You are not required to supply a value for the <xref:System.Data.DataTable.TableName%2A> property when you create a **DataTable**; you can specify the property at another time, or you can leave it empty.</span></span> <span data-ttu-id="0adc7-113">Тем не менее, при добавлении таблицы без **TableName** значение **набора данных**, будет присвоено имя по умолчанию — таблица*N*, начиная с «Table» для Table0.</span><span class="sxs-lookup"><span data-stu-id="0adc7-113">However, when you add a table without a **TableName** value to a **DataSet**, the table will be given an incremental default name of Table*N*, starting with "Table" for Table0.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0adc7-114">Мы рекомендуем избегать» таблицы*N*"соглашение об именовании, при указании **TableName** , поскольку к. предоставляемое имя может конфликтовать с существующим именем таблицы по умолчанию в значение **набора данных** .</span><span class="sxs-lookup"><span data-stu-id="0adc7-114">We recommend that you avoid the "Table*N*" naming convention when you supply a **TableName** value, because the name you supply may conflict with an existing default table name in the **DataSet**.</span></span> <span data-ttu-id="0adc7-115">Если указанное имя уже существует, вызывается исключение.</span><span class="sxs-lookup"><span data-stu-id="0adc7-115">If the supplied name already exists, an exception is thrown.</span></span>  
  
 <span data-ttu-id="0adc7-116">В следующем примере создается экземпляр **DataTable** , которому присваивается имя «Customers».</span><span class="sxs-lookup"><span data-stu-id="0adc7-116">The following example creates an instance of a **DataTable** object and assigns it the name "Customers."</span></span>  
  
```vb  
Dim workTable as DataTable = New DataTable("Customers")  
```  
  
```csharp  
DataTable workTable = new DataTable("Customers");  
```  
  
 <span data-ttu-id="0adc7-117">В следующем примере создается экземпляр **DataTable** путем добавления его в **таблиц** коллекцию **набора данных**.</span><span class="sxs-lookup"><span data-stu-id="0adc7-117">The following example creates an instance of a **DataTable** by adding it to the **Tables** collection of a **DataSet**.</span></span>  
  
```vb  
Dim customers As DataSet = New DataSet  
Dim customersTable As DataTable = _  
   customers.Tables.Add("CustomersTable")  
```  
  
```csharp  
DataSet customers = new DataSet();  
DataTable customersTable = customers.Tables.Add("CustomersTable");  
```  
  
## <a name="see-also"></a><span data-ttu-id="0adc7-118">См. также</span><span class="sxs-lookup"><span data-stu-id="0adc7-118">See also</span></span>

- <xref:System.Data.DataTable>
- <xref:System.Data.DataTableCollection>
- [<span data-ttu-id="0adc7-119">DataTables</span><span class="sxs-lookup"><span data-stu-id="0adc7-119">DataTables</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)
- [<span data-ttu-id="0adc7-120">Заполнение набора данных с помощью адаптера данных DataAdapter</span><span class="sxs-lookup"><span data-stu-id="0adc7-120">Populating a DataSet from a DataAdapter</span></span>](../../../../../docs/framework/data/adonet/populating-a-dataset-from-a-dataadapter.md)
- [<span data-ttu-id="0adc7-121">Загрузка DataSet из XML</span><span class="sxs-lookup"><span data-stu-id="0adc7-121">Loading a DataSet from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)
- [<span data-ttu-id="0adc7-122">Загрузка сведений о схеме DataSet из XML</span><span class="sxs-lookup"><span data-stu-id="0adc7-122">Loading DataSet Schema Information from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)
- [<span data-ttu-id="0adc7-123">Центр разработчиков наборов данных и управляемых поставщиков ADO.NET</span><span class="sxs-lookup"><span data-stu-id="0adc7-123">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
