---
title: "Создание таблицы данных"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: eecf9d78-60e3-4fdc-8de0-e56c13a89414
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 68f8272aa0f525c04120f129057e6151e42ffee1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="creating-a-datatable"></a><span data-ttu-id="a19d0-102">Создание таблицы данных</span><span class="sxs-lookup"><span data-stu-id="a19d0-102">Creating a DataTable</span></span>
<span data-ttu-id="a19d0-103">Объект <xref:System.Data.DataTable>, который представляет одну таблицу находящихся в памяти реляционных данных, может создаваться и использоваться независимо или использоваться другими объектами .NET Framework, чаще всего как член <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="a19d0-103">A <xref:System.Data.DataTable>, which represents one table of in-memory relational data, can be created and used independently, or can be used by other .NET Framework objects, most commonly as a member of a <xref:System.Data.DataSet>.</span></span>  
  
 <span data-ttu-id="a19d0-104">Можно создать **DataTable** объекта, используя соответствующую **DataTable** конструктор.</span><span class="sxs-lookup"><span data-stu-id="a19d0-104">You can create a **DataTable** object by using the appropriate **DataTable** constructor.</span></span> <span data-ttu-id="a19d0-105">Его можно добавить к **DataSet** с помощью **добавить** метод, чтобы добавить его в **DataTable** объекта **таблиц** коллекции.</span><span class="sxs-lookup"><span data-stu-id="a19d0-105">You can add it to the **DataSet** by using the **Add** method to add it to the **DataTable** object's **Tables** collection.</span></span>  
  
 <span data-ttu-id="a19d0-106">Можно также создать **DataTable** объекты в пределах **DataSet** с помощью **заполнения** или **FillSchema** методы  **DataAdapter** объекта, или из стандартных или выводимого схемы XML с помощью **ReadXml**, **ReadXmlSchema**, или **InferXmlSchema** методы **набора данных**.</span><span class="sxs-lookup"><span data-stu-id="a19d0-106">You can also create **DataTable** objects within a **DataSet** by using the **Fill** or **FillSchema** methods of the **DataAdapter** object, or from a predefined or inferred XML schema using the **ReadXml**, **ReadXmlSchema**, or **InferXmlSchema** methods of the **DataSet**.</span></span> <span data-ttu-id="a19d0-107">Обратите внимание, что после добавления **DataTable** членом **таблиц** набор из одного элемента **набора данных**, его нельзя добавить в коллекцию таблиц какого любые другие **Набора данных**.</span><span class="sxs-lookup"><span data-stu-id="a19d0-107">Note that after you have added a **DataTable** as a member of the **Tables** collection of one **DataSet**, you cannot add it to the collection of tables of any other **DataSet**.</span></span>  
  
 <span data-ttu-id="a19d0-108">При первом создании **DataTable**, не имеет схемы (то есть структуру).</span><span class="sxs-lookup"><span data-stu-id="a19d0-108">When you first create a **DataTable**, it does not have a schema (that is, a structure).</span></span> <span data-ttu-id="a19d0-109">Чтобы определить схему таблицы, необходимо создать и добавить <xref:System.Data.DataColumn> объектов **столбцы** таблицы.</span><span class="sxs-lookup"><span data-stu-id="a19d0-109">To define the schema of the table, you must create and add <xref:System.Data.DataColumn> objects to the **Columns** collection of the table.</span></span> <span data-ttu-id="a19d0-110">Можно также определить столбец первичного ключа для таблицы и создайте и добавьте **ограничение** объектов **ограничения** таблицы.</span><span class="sxs-lookup"><span data-stu-id="a19d0-110">You can also define a primary key column for the table, and create and add **Constraint** objects to the **Constraints** collection of the table.</span></span> <span data-ttu-id="a19d0-111">После определения схемы для **DataTable**, можно добавлять строки данных в таблицу, добавив **DataRow** объектов **строк** таблицы.</span><span class="sxs-lookup"><span data-stu-id="a19d0-111">After you have defined the schema for a **DataTable**, you can add rows of data to the table by adding **DataRow** objects to the **Rows** collection of the table.</span></span>  
  
 <span data-ttu-id="a19d0-112">Не требуется задать значение для <xref:System.Data.DataTable.TableName%2A> свойства при создании **DataTable**; можно указать свойства в другое время, или оставить его пустым.</span><span class="sxs-lookup"><span data-stu-id="a19d0-112">You are not required to supply a value for the <xref:System.Data.DataTable.TableName%2A> property when you create a **DataTable**; you can specify the property at another time, or you can leave it empty.</span></span> <span data-ttu-id="a19d0-113">Тем не менее, при добавлении таблицы без **TableName** значение **DataSet**, будет присвоено имя по умолчанию — таблице*N*, начиная с «Table» для Table0.</span><span class="sxs-lookup"><span data-stu-id="a19d0-113">However, when you add a table without a **TableName** value to a **DataSet**, the table will be given an incremental default name of Table*N*, starting with "Table" for Table0.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a19d0-114">Мы рекомендуем избегать» таблицы*N*«соглашение об именовании, при указании **TableName** значение, поскольку указывается имя может конфликтовать с существующим именем таблицы по умолчанию в **набора данных** .</span><span class="sxs-lookup"><span data-stu-id="a19d0-114">We recommend that you avoid the "Table*N*" naming convention when you supply a **TableName** value, because the name you supply may conflict with an existing default table name in the **DataSet**.</span></span> <span data-ttu-id="a19d0-115">Если указанное имя уже существует, вызывается исключение.</span><span class="sxs-lookup"><span data-stu-id="a19d0-115">If the supplied name already exists, an exception is thrown.</span></span>  
  
 <span data-ttu-id="a19d0-116">В следующем примере создается экземпляр **DataTable** объекта и присваивает ему имя «Customers».</span><span class="sxs-lookup"><span data-stu-id="a19d0-116">The following example creates an instance of a **DataTable** object and assigns it the name "Customers."</span></span>  
  
```vb  
Dim workTable as DataTable = New DataTable("Customers")  
```  
  
```csharp  
DataTable workTable = new DataTable("Customers");  
```  
  
 <span data-ttu-id="a19d0-117">В следующем примере создается экземпляр **DataTable** путем добавления его в **таблиц** коллекцию **набора данных**.</span><span class="sxs-lookup"><span data-stu-id="a19d0-117">The following example creates an instance of a **DataTable** by adding it to the **Tables** collection of a **DataSet**.</span></span>  
  
```vb  
Dim customers As DataSet = New DataSet  
Dim customersTable As DataTable = _  
   customers.Tables.Add("CustomersTable")  
```  
  
```csharp  
DataSet customers = new DataSet();  
DataTable customersTable = customers.Tables.Add("CustomersTable");  
```  
  
## <a name="see-also"></a><span data-ttu-id="a19d0-118">См. также</span><span class="sxs-lookup"><span data-stu-id="a19d0-118">See Also</span></span>  
 <xref:System.Data.DataTable>  
 <xref:System.Data.DataTableCollection>  
 [<span data-ttu-id="a19d0-119">DataTables</span><span class="sxs-lookup"><span data-stu-id="a19d0-119">DataTables</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)  
 [<span data-ttu-id="a19d0-120">Заполнение набора данных с помощью адаптера данных DataAdapter</span><span class="sxs-lookup"><span data-stu-id="a19d0-120">Populating a DataSet from a DataAdapter</span></span>](../../../../../docs/framework/data/adonet/populating-a-dataset-from-a-dataadapter.md)  
 [<span data-ttu-id="a19d0-121">Загрузка DataSet из XML</span><span class="sxs-lookup"><span data-stu-id="a19d0-121">Loading a DataSet from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)  
 [<span data-ttu-id="a19d0-122">Загрузка сведений о схеме DataSet из XML</span><span class="sxs-lookup"><span data-stu-id="a19d0-122">Loading DataSet Schema Information from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)  
 [<span data-ttu-id="a19d0-123">Центр разработчиков наборов данных и управляемых поставщиков ADO.NET</span><span class="sxs-lookup"><span data-stu-id="a19d0-123">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
