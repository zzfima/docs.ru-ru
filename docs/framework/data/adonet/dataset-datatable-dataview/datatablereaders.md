---
title: Объекты DataTableReader
ms.date: 03/30/2017
ms.assetid: 97546ae2-0e42-4d26-961d-e0b244d81ded
ms.openlocfilehash: 1ff7868b59c6fdc4e6c443be1b831accc84f36a6
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/31/2019
ms.locfileid: "70203817"
---
# <a name="datatablereaders"></a><span data-ttu-id="502c4-102">Объекты DataTableReader</span><span class="sxs-lookup"><span data-stu-id="502c4-102">DataTableReaders</span></span>
<span data-ttu-id="502c4-103"><xref:System.Data.DataTableReader> представляет содержимое объекта <xref:System.Data.DataTable> или <xref:System.Data.DataSet> в виде одного или нескольких результирующих наборов, предназначенных только для чтения и только для перенаправления.</span><span class="sxs-lookup"><span data-stu-id="502c4-103">The <xref:System.Data.DataTableReader> presents the contents of a <xref:System.Data.DataTable> or a <xref:System.Data.DataSet> in the form of one or more read-only, forward-only result sets.</span></span>  
  
 <span data-ttu-id="502c4-104">При создании объекта **DataTableReader** из **таблицы**данных результирующий объект **DataTableReader** содержит один результирующий набор с теми же данными, что и у **таблицы DataTable** , из которой он был создан, за исключением строк, помеченных как удаленной.</span><span class="sxs-lookup"><span data-stu-id="502c4-104">When you create a **DataTableReader** from a **DataTable**, the resulting **DataTableReader** object contains one result set with the same data as the **DataTable** from which it was created, except for any rows that have been marked as deleted.</span></span> <span data-ttu-id="502c4-105">Столбцы отображаются в том же порядке, что и в исходной **таблице**данных.</span><span class="sxs-lookup"><span data-stu-id="502c4-105">The columns appear in the same order as in the original **DataTable**.</span></span>  
  
 <span data-ttu-id="502c4-106">Объект **DataTableReader** может содержать несколько результирующих наборов, если он был создан <xref:System.Data.DataSet.CreateDataReader%2A>путем вызова метода.</span><span class="sxs-lookup"><span data-stu-id="502c4-106">A **DataTableReader** may contain multiple result sets if it was created by calling <xref:System.Data.DataSet.CreateDataReader%2A>.</span></span> <span data-ttu-id="502c4-107">Результаты находятся в том же порядке, что <xref:System.Data.DataSet.Tables%2A> и **DataTables** в коллекции объекта **DataSet** .</span><span class="sxs-lookup"><span data-stu-id="502c4-107">The results are in the same order as the **DataTables** in the **DataSet** object's <xref:System.Data.DataSet.Tables%2A> collection.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="502c4-108">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="502c4-108">In This Section</span></span>  
 [<span data-ttu-id="502c4-109">Создание объекта DataReader</span><span class="sxs-lookup"><span data-stu-id="502c4-109">Creating a DataReader</span></span>](creating-a-datareader.md)  
 <span data-ttu-id="502c4-110">Описывает, как создать объект **DataTableReader** .</span><span class="sxs-lookup"><span data-stu-id="502c4-110">Discusses how to create a **DataTableReader** object.</span></span>  
  
 [<span data-ttu-id="502c4-111">Навигация в объектах DataTable</span><span class="sxs-lookup"><span data-stu-id="502c4-111">Navigating DataTables</span></span>](navigating-datatables.md)  
 <span data-ttu-id="502c4-112">Описывает использование метода **Read** для перемещения по содержимому объекта **DataTableReader**.</span><span class="sxs-lookup"><span data-stu-id="502c4-112">Describes the use of the **Read** method to move through the contents of a **DataTableReader**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="502c4-113">См. также</span><span class="sxs-lookup"><span data-stu-id="502c4-113">See also</span></span>

- [<span data-ttu-id="502c4-114">Извлечение и изменение данных в ADO.NET</span><span class="sxs-lookup"><span data-stu-id="502c4-114">Retrieving and Modifying Data in ADO.NET</span></span>](../retrieving-and-modifying-data.md)
- [<span data-ttu-id="502c4-115">Центр разработчиков наборов данных и управляемых поставщиков ADO.NET</span><span class="sxs-lookup"><span data-stu-id="502c4-115">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
