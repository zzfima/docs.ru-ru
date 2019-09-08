---
title: REF CURSOR в Oracle
ms.date: 03/30/2017
ms.assetid: c6b25b8b-0bdd-41b2-9c7c-661f070c2247
ms.openlocfilehash: 7cd29a6a20015c7ce4475b0211cb07f7ee78b530
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70794873"
---
# <a name="oracle-ref-cursors"></a><span data-ttu-id="8587d-102">REF CURSOR в Oracle</span><span class="sxs-lookup"><span data-stu-id="8587d-102">Oracle REF CURSORs</span></span>
<span data-ttu-id="8587d-103">Поставщик данных .NET Framework для Oracle поддерживает тип данных Oracle **ref Cursor** .</span><span class="sxs-lookup"><span data-stu-id="8587d-103">The .NET Framework Data Provider for Oracle supports the Oracle **REF CURSOR** data type.</span></span> <span data-ttu-id="8587d-104">При использовании поставщика данных для работы с данными типа REF CURSOR Oracle необходимо учитывать следующие особенности его функционирования.</span><span class="sxs-lookup"><span data-stu-id="8587d-104">When using the data provider to work with Oracle REF CURSORs, you should consider the following behaviors.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8587d-105">По некоторым особенностям функционирования он отличается от поставщика Microsoft OLE DB для Oracle (MSDAORA).</span><span class="sxs-lookup"><span data-stu-id="8587d-105">Some behaviors differ from those of the Microsoft OLE DB Provider for Oracle (MSDAORA).</span></span>  
  
- <span data-ttu-id="8587d-106">По соображениям производительности поставщик данных для Oracle не привязывает типы данных **ссылочных курсоров** автоматически, как если бы они явно не заданы.</span><span class="sxs-lookup"><span data-stu-id="8587d-106">For performance reasons, the Data Provider for Oracle does not automatically bind **REF CURSOR** data types, as MSDAORA does, unless you explicitly specify them.</span></span>  
  
- <span data-ttu-id="8587d-107">Указанный поставщик данных не поддерживает никаких escape-последовательностей ODBC, включая escape-последовательность {resultset}, используемую для задания параметров REF CURSOR.</span><span class="sxs-lookup"><span data-stu-id="8587d-107">The data provider does not support any ODBC escape sequences, including the {resultset} escape used to specify REF CURSOR parameters.</span></span>  
  
- <span data-ttu-id="8587d-108">Для выполнения хранимой процедуры, возвращающей ссылки REF CURSOR, <xref:System.Data.OracleClient.OracleParameterCollection> необходимо определить параметры в <xref:System.Data.OracleClient.OracleType> с помощью **курсора** и <xref:System.Data.OracleClient.OracleParameter.Direction%2A> **выходных данных**.</span><span class="sxs-lookup"><span data-stu-id="8587d-108">To execute a stored procedure that returns REF CURSORs, you must define the parameters in the <xref:System.Data.OracleClient.OracleParameterCollection> with an <xref:System.Data.OracleClient.OracleType> of **Cursor** and a <xref:System.Data.OracleClient.OracleParameter.Direction%2A> of **Output**.</span></span> <span data-ttu-id="8587d-109">Этот поставщик данных поддерживает привязку данных типа REF CURSOR только в качестве выходных параметров.</span><span class="sxs-lookup"><span data-stu-id="8587d-109">The data provider supports binding REF CURSORs as output parameters only.</span></span> <span data-ttu-id="8587d-110">Этот поставщик не поддерживает данные типа REF CURSOR как входные параметры.</span><span class="sxs-lookup"><span data-stu-id="8587d-110">The provider does not support REF CURSORs as input parameters.</span></span>  
  
- <span data-ttu-id="8587d-111">Получение модуля <xref:System.Data.OracleClient.OracleDataReader> из значения параметра не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="8587d-111">Obtaining an <xref:System.Data.OracleClient.OracleDataReader> from the parameter value is not supported.</span></span> <span data-ttu-id="8587d-112">Значения имеют тип <xref:System.DBNull> после выполнения команды.</span><span class="sxs-lookup"><span data-stu-id="8587d-112">The values are of type <xref:System.DBNull> after command execution.</span></span>  
  
- <span data-ttu-id="8587d-113">Единственным значением перечисления **CommandBehavior** , которое работает с ключевыми курсорами (например, при вызове <xref:System.Data.OracleClient.OracleCommand.ExecuteReader%2A>), является **клосеконнектион**; все остальные игнорируются.</span><span class="sxs-lookup"><span data-stu-id="8587d-113">The only **CommandBehavior** enumeration value that works with REF CURSORs (for example, when calling <xref:System.Data.OracleClient.OracleCommand.ExecuteReader%2A>) is **CloseConnection**; all others are ignored.</span></span>  
  
- <span data-ttu-id="8587d-114">Порядок ССЫЛОЧных КУРСОРов в **OracleDataReader** зависит от порядка параметров в **OracleParameterCollection**.</span><span class="sxs-lookup"><span data-stu-id="8587d-114">The order of REF CURSORs in the **OracleDataReader** depends on the order of the parameters in the **OracleParameterCollection**.</span></span> <span data-ttu-id="8587d-115">Свойство <xref:System.Data.OracleClient.OracleParameter.ParameterName%2A> не учитывается.</span><span class="sxs-lookup"><span data-stu-id="8587d-115">The <xref:System.Data.OracleClient.OracleParameter.ParameterName%2A> property is ignored.</span></span>  
  
- <span data-ttu-id="8587d-116">**Табличный** тип данных PL/SQL не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="8587d-116">The PL/SQL **TABLE** data type is not supported.</span></span> <span data-ttu-id="8587d-117">Но данные типа REF CURSOR являются более эффективными.</span><span class="sxs-lookup"><span data-stu-id="8587d-117">However, REF CURSORs are more efficient.</span></span> <span data-ttu-id="8587d-118">Если необходимо использовать **табличный** тип данных, используйте поставщик данных OLE DB .NET с MSDAORA.</span><span class="sxs-lookup"><span data-stu-id="8587d-118">If you must use a **TABLE** data type, use the OLE DB .NET Data Provider with MSDAORA.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8587d-119">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="8587d-119">In This Section</span></span>  
 [<span data-ttu-id="8587d-120">Примеры REF CURSOR</span><span class="sxs-lookup"><span data-stu-id="8587d-120">REF CURSOR Examples</span></span>](ref-cursor-examples.md)  
 <span data-ttu-id="8587d-121">Содержит три примера, которые демонстрируют использование данных типа REF CURSOR.</span><span class="sxs-lookup"><span data-stu-id="8587d-121">Contains three examples that demonstrate using REF CURSORs.</span></span>  
  
 [<span data-ttu-id="8587d-122">Параметры REF CURSOR в объекте OracleDataReader</span><span class="sxs-lookup"><span data-stu-id="8587d-122">REF CURSOR Parameters in an OracleDataReader</span></span>](ref-cursor-parameters-in-an-oracledatareader.md)  
 <span data-ttu-id="8587d-123">Демонстрирует выполнение хранимой процедуры PL/SQL, возвращающей параметр REF CURSOR, и считывание значения в виде **OracleDataReader**.</span><span class="sxs-lookup"><span data-stu-id="8587d-123">Demonstrates how to execute a PL/SQL stored procedure that returns a REF CURSOR parameter, and reads the value as an **OracleDataReader**.</span></span>  
  
 [<span data-ttu-id="8587d-124">Извлечение данных из нескольких REF CURSOR с использованием OracleDataReader</span><span class="sxs-lookup"><span data-stu-id="8587d-124">Retrieving Data from Multiple REF CURSORs Using an OracleDataReader</span></span>](retrieving-data-from-multiple-ref-cursors.md)  
 <span data-ttu-id="8587d-125">Демонстрирует выполнение хранимой процедуры PL/SQL, возвращающей два параметра REF CURSOR, и считывание значений с помощью **OracleDataReader**.</span><span class="sxs-lookup"><span data-stu-id="8587d-125">Demonstrates how to execute a PL/SQL stored procedure that returns two REF CURSOR parameters, and reads the values using an **OracleDataReader**.</span></span>  
  
 [<span data-ttu-id="8587d-126">Заполнение DataSet с помощью одного или нескольких параметров REF CURSOR</span><span class="sxs-lookup"><span data-stu-id="8587d-126">Filling a DataSet Using One or More REF CURSORs</span></span>](filling-a-dataset-using-one-or-more-ref-cursors.md)  
 <span data-ttu-id="8587d-127">Показывает, как выполнить хранимую процедуру PL/SQL, которая возвращает два параметра REF CURSOR и заполняет <xref:System.Data.DataSet> возвращаемыми строками.</span><span class="sxs-lookup"><span data-stu-id="8587d-127">Demonstrates how to execute a PL/SQL stored procedure that returns two REF CURSOR parameters, and fills a <xref:System.Data.DataSet> with the rows that are returned.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8587d-128">См. также</span><span class="sxs-lookup"><span data-stu-id="8587d-128">See also</span></span>

- [<span data-ttu-id="8587d-129">Oracle и ADO.NET</span><span class="sxs-lookup"><span data-stu-id="8587d-129">Oracle and ADO.NET</span></span>](oracle-and-adonet.md)
- [<span data-ttu-id="8587d-130">Общие сведения об ADO.NET</span><span class="sxs-lookup"><span data-stu-id="8587d-130">ADO.NET Overview</span></span>](ado-net-overview.md)
