---
title: Объекты DataTableReader
ms.date: 03/30/2017
ms.assetid: 97546ae2-0e42-4d26-961d-e0b244d81ded
ms.openlocfilehash: 1559cde9cb786ccb2baf920347064b8b28d472c3
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70785342"
---
# <a name="datatablereaders"></a><span data-ttu-id="f967b-102">Объекты DataTableReader</span><span class="sxs-lookup"><span data-stu-id="f967b-102">DataTableReaders</span></span>
<span data-ttu-id="f967b-103"><xref:System.Data.DataTableReader> представляет содержимое объекта <xref:System.Data.DataTable> или <xref:System.Data.DataSet> в виде одного или нескольких результирующих наборов, предназначенных только для чтения и только для перенаправления.</span><span class="sxs-lookup"><span data-stu-id="f967b-103">The <xref:System.Data.DataTableReader> presents the contents of a <xref:System.Data.DataTable> or a <xref:System.Data.DataSet> in the form of one or more read-only, forward-only result sets.</span></span>  
  
 <span data-ttu-id="f967b-104">При создании объекта **DataTableReader** из **таблицы**данных результирующий объект **DataTableReader** содержит один результирующий набор с теми же данными, что и у **таблицы DataTable** , из которой он был создан, за исключением строк, помеченных как удаленной.</span><span class="sxs-lookup"><span data-stu-id="f967b-104">When you create a **DataTableReader** from a **DataTable**, the resulting **DataTableReader** object contains one result set with the same data as the **DataTable** from which it was created, except for any rows that have been marked as deleted.</span></span> <span data-ttu-id="f967b-105">Столбцы отображаются в том же порядке, что и в исходной **таблице**данных.</span><span class="sxs-lookup"><span data-stu-id="f967b-105">The columns appear in the same order as in the original **DataTable**.</span></span>  
  
 <span data-ttu-id="f967b-106">Объект **DataTableReader** может содержать несколько результирующих наборов, если он был создан <xref:System.Data.DataSet.CreateDataReader%2A>путем вызова метода.</span><span class="sxs-lookup"><span data-stu-id="f967b-106">A **DataTableReader** may contain multiple result sets if it was created by calling <xref:System.Data.DataSet.CreateDataReader%2A>.</span></span> <span data-ttu-id="f967b-107">Результаты находятся в том же порядке, что и **DataTables** в <xref:System.Data.DataSet.Tables%2A> коллекции объекта **DataSet** .</span><span class="sxs-lookup"><span data-stu-id="f967b-107">The results are in the same order as the **DataTables** in the **DataSet** object's <xref:System.Data.DataSet.Tables%2A> collection.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f967b-108">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="f967b-108">In This Section</span></span>  
 [<span data-ttu-id="f967b-109">Создание объекта DataReader</span><span class="sxs-lookup"><span data-stu-id="f967b-109">Creating a DataReader</span></span>](creating-a-datareader.md)  
 <span data-ttu-id="f967b-110">Описывает, как создать объект **DataTableReader** .</span><span class="sxs-lookup"><span data-stu-id="f967b-110">Discusses how to create a **DataTableReader** object.</span></span>  
  
 [<span data-ttu-id="f967b-111">Навигация в объектах DataTable</span><span class="sxs-lookup"><span data-stu-id="f967b-111">Navigating DataTables</span></span>](navigating-datatables.md)  
 <span data-ttu-id="f967b-112">Описывает использование метода **Read** для перемещения по содержимому объекта **DataTableReader**.</span><span class="sxs-lookup"><span data-stu-id="f967b-112">Describes the use of the **Read** method to move through the contents of a **DataTableReader**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f967b-113">См. также</span><span class="sxs-lookup"><span data-stu-id="f967b-113">See also</span></span>

- [<span data-ttu-id="f967b-114">Извлечение и изменение данных в ADO.NET</span><span class="sxs-lookup"><span data-stu-id="f967b-114">Retrieving and Modifying Data in ADO.NET</span></span>](../retrieving-and-modifying-data.md)
- [<span data-ttu-id="f967b-115">Общие сведения об ADO.NET</span><span class="sxs-lookup"><span data-stu-id="f967b-115">ADO.NET Overview</span></span>](../ado-net-overview.md)
