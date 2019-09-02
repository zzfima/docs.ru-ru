---
title: Создание таблицы данных
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: eecf9d78-60e3-4fdc-8de0-e56c13a89414
ms.openlocfilehash: 64ba7a8e6bd6361e14d1f16576e377575b088bbe
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/31/2019
ms.locfileid: "70205144"
---
# <a name="creating-a-datatable"></a><span data-ttu-id="435b7-102">Создание таблицы данных</span><span class="sxs-lookup"><span data-stu-id="435b7-102">Creating a DataTable</span></span>
<span data-ttu-id="435b7-103">Объект <xref:System.Data.DataTable>, который представляет одну таблицу находящихся в памяти реляционных данных, может создаваться и использоваться независимо или использоваться другими объектами .NET Framework, чаще всего как член <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="435b7-103">A <xref:System.Data.DataTable>, which represents one table of in-memory relational data, can be created and used independently, or can be used by other .NET Framework objects, most commonly as a member of a <xref:System.Data.DataSet>.</span></span>  
  
 <span data-ttu-id="435b7-104">Объект **DataTable** можно создать с помощью соответствующего конструктора **DataTable** .</span><span class="sxs-lookup"><span data-stu-id="435b7-104">You can create a **DataTable** object by using the appropriate **DataTable** constructor.</span></span> <span data-ttu-id="435b7-105">Его можно добавить в **набор данных** с помощью метода **Add** , чтобы добавить его в коллекцию Tables объекта **DataTable** .</span><span class="sxs-lookup"><span data-stu-id="435b7-105">You can add it to the **DataSet** by using the **Add** method to add it to the **DataTable** object's **Tables** collection.</span></span>  
  
 <span data-ttu-id="435b7-106">Объекты **DataTable** также можно создавать в **наборе данных** с помощью методов **Fill** или **FillSchema** объекта **DataAdapter** или из предопределенной или выводимой XML-схемы с помощью метода **ReadXml**, **ReadXmlSchema** или **Инферксмлсчема** методы **набора данных**.</span><span class="sxs-lookup"><span data-stu-id="435b7-106">You can also create **DataTable** objects within a **DataSet** by using the **Fill** or **FillSchema** methods of the **DataAdapter** object, or from a predefined or inferred XML schema using the **ReadXml**, **ReadXmlSchema**, or **InferXmlSchema** methods of the **DataSet**.</span></span> <span data-ttu-id="435b7-107">Обратите внимание, что после добавления **DataTable** в качестве члена коллекции **таблиц** из одного **набора данных**нельзя добавить его в коллекцию таблиц любого другого **набора данных**.</span><span class="sxs-lookup"><span data-stu-id="435b7-107">Note that after you have added a **DataTable** as a member of the **Tables** collection of one **DataSet**, you cannot add it to the collection of tables of any other **DataSet**.</span></span>  
  
 <span data-ttu-id="435b7-108">При первом создании таблицы данных **Таблица**не имеет схемы (то есть структуры).</span><span class="sxs-lookup"><span data-stu-id="435b7-108">When you first create a **DataTable**, it does not have a schema (that is, a structure).</span></span> <span data-ttu-id="435b7-109">Чтобы определить схему таблицы, необходимо создать и добавить <xref:System.Data.DataColumn> объекты в коллекцию **Columns** таблицы.</span><span class="sxs-lookup"><span data-stu-id="435b7-109">To define the schema of the table, you must create and add <xref:System.Data.DataColumn> objects to the **Columns** collection of the table.</span></span> <span data-ttu-id="435b7-110">Кроме того, можно определить первичный ключевой столбец для таблицы, а также создать и добавить объекты **ограничений** в коллекцию **ограничений** таблицы.</span><span class="sxs-lookup"><span data-stu-id="435b7-110">You can also define a primary key column for the table, and create and add **Constraint** objects to the **Constraints** collection of the table.</span></span> <span data-ttu-id="435b7-111">Определив схему для **DataTable**, можно добавить строки данных в таблицу, добавив объекты **DataRow** в коллекцию **Rows** таблицы.</span><span class="sxs-lookup"><span data-stu-id="435b7-111">After you have defined the schema for a **DataTable**, you can add rows of data to the table by adding **DataRow** objects to the **Rows** collection of the table.</span></span>  
  
 <span data-ttu-id="435b7-112">При создании <xref:System.Data.DataTable.TableName%2A> **таблицы**данных значение свойства указывать не обязательно; свойство можно указать в другое время, либо оставить его пустым.</span><span class="sxs-lookup"><span data-stu-id="435b7-112">You are not required to supply a value for the <xref:System.Data.DataTable.TableName%2A> property when you create a **DataTable**; you can specify the property at another time, or you can leave it empty.</span></span> <span data-ttu-id="435b7-113">Однако при добавлении таблицы без значения **TableName** в **набор данных**этой таблице будет присвоено добавочное имя по умолчанию таблицы*N*, начинающееся с «Table» для Table0.</span><span class="sxs-lookup"><span data-stu-id="435b7-113">However, when you add a table without a **TableName** value to a **DataSet**, the table will be given an incremental default name of Table*N*, starting with "Table" for Table0.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="435b7-114">Рекомендуется избегать соглашения об именовании "Table*N*" при указании значения **TableName** , так как указываемое имя может конфликтовать с существующим именем таблицы по умолчанию в наборе **данных**.</span><span class="sxs-lookup"><span data-stu-id="435b7-114">We recommend that you avoid the "Table*N*" naming convention when you supply a **TableName** value, because the name you supply may conflict with an existing default table name in the **DataSet**.</span></span> <span data-ttu-id="435b7-115">Если указанное имя уже существует, вызывается исключение.</span><span class="sxs-lookup"><span data-stu-id="435b7-115">If the supplied name already exists, an exception is thrown.</span></span>  
  
 <span data-ttu-id="435b7-116">В следующем примере создается экземпляр объекта **DataTable** и присваивается имя Customers.</span><span class="sxs-lookup"><span data-stu-id="435b7-116">The following example creates an instance of a **DataTable** object and assigns it the name "Customers."</span></span>  
  
```vb  
Dim workTable as DataTable = New DataTable("Customers")  
```  
  
```csharp  
DataTable workTable = new DataTable("Customers");  
```  
  
 <span data-ttu-id="435b7-117">В следующем примере создается экземпляр **DataTable** путем его добавления в коллекцию **Tables** **набора данных**.</span><span class="sxs-lookup"><span data-stu-id="435b7-117">The following example creates an instance of a **DataTable** by adding it to the **Tables** collection of a **DataSet**.</span></span>  
  
```vb  
Dim customers As DataSet = New DataSet  
Dim customersTable As DataTable = _  
   customers.Tables.Add("CustomersTable")  
```  
  
```csharp  
DataSet customers = new DataSet();  
DataTable customersTable = customers.Tables.Add("CustomersTable");  
```  
  
## <a name="see-also"></a><span data-ttu-id="435b7-118">См. также</span><span class="sxs-lookup"><span data-stu-id="435b7-118">See also</span></span>

- <xref:System.Data.DataTable>
- <xref:System.Data.DataTableCollection>
- [<span data-ttu-id="435b7-119">DataTables</span><span class="sxs-lookup"><span data-stu-id="435b7-119">DataTables</span></span>](datatables.md)
- [<span data-ttu-id="435b7-120">Заполнение набора данных с помощью адаптера данных DataAdapter</span><span class="sxs-lookup"><span data-stu-id="435b7-120">Populating a DataSet from a DataAdapter</span></span>](../populating-a-dataset-from-a-dataadapter.md)
- [<span data-ttu-id="435b7-121">Загрузка DataSet из XML</span><span class="sxs-lookup"><span data-stu-id="435b7-121">Loading a DataSet from XML</span></span>](loading-a-dataset-from-xml.md)
- [<span data-ttu-id="435b7-122">Загрузка сведений о схеме DataSet из XML</span><span class="sxs-lookup"><span data-stu-id="435b7-122">Loading DataSet Schema Information from XML</span></span>](loading-dataset-schema-information-from-xml.md)
- [<span data-ttu-id="435b7-123">Центр разработчиков наборов данных и управляемых поставщиков ADO.NET</span><span class="sxs-lookup"><span data-stu-id="435b7-123">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
