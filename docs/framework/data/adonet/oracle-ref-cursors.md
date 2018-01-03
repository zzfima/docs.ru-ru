---
title: "REF CURSOR в Oracle"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c6b25b8b-0bdd-41b2-9c7c-661f070c2247
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 27351c1d47d4ad40940e5b64f257e6a59fc7403a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="oracle-ref-cursors"></a><span data-ttu-id="afd97-102">REF CURSOR в Oracle</span><span class="sxs-lookup"><span data-stu-id="afd97-102">Oracle REF CURSORs</span></span>
<span data-ttu-id="afd97-103">Поставщик данных .NET Framework для Oracle поддерживает Oracle **REF CURSOR** тип данных.</span><span class="sxs-lookup"><span data-stu-id="afd97-103">The .NET Framework Data Provider for Oracle supports the Oracle **REF CURSOR** data type.</span></span> <span data-ttu-id="afd97-104">При использовании поставщика данных для работы с данными типа REF CURSOR Oracle необходимо учитывать следующие особенности его функционирования.</span><span class="sxs-lookup"><span data-stu-id="afd97-104">When using the data provider to work with Oracle REF CURSORs, you should consider the following behaviors.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="afd97-105">По некоторым особенностям функционирования он отличается от поставщика Microsoft OLE DB для Oracle (MSDAORA).</span><span class="sxs-lookup"><span data-stu-id="afd97-105">Some behaviors differ from those of the Microsoft OLE DB Provider for Oracle (MSDAORA).</span></span>  
  
-   <span data-ttu-id="afd97-106">Для повышения производительности поставщик данных для Oracle автоматически привязку **REF CURSOR** , типы данных как MSDAORA, если вы явно не указана.</span><span class="sxs-lookup"><span data-stu-id="afd97-106">For performance reasons, the Data Provider for Oracle does not automatically bind **REF CURSOR** data types, as MSDAORA does, unless you explicitly specify them.</span></span>  
  
-   <span data-ttu-id="afd97-107">Указанный поставщик данных не поддерживает никаких escape-последовательностей ODBC, включая escape-последовательность {resultset}, используемую для задания параметров REF CURSOR.</span><span class="sxs-lookup"><span data-stu-id="afd97-107">The data provider does not support any ODBC escape sequences, including the {resultset} escape used to specify REF CURSOR parameters.</span></span>  
  
-   <span data-ttu-id="afd97-108">Чтобы выполнить хранимую процедуру, которая возвращает параметры REF CURSOR, необходимо определить параметры в <xref:System.Data.OracleClient.OracleParameterCollection> с <xref:System.Data.OracleClient.OracleType> из **курсор** и <xref:System.Data.OracleClient.OracleParameter.Direction%2A> из **вывода**.</span><span class="sxs-lookup"><span data-stu-id="afd97-108">To execute a stored procedure that returns REF CURSORs, you must define the parameters in the <xref:System.Data.OracleClient.OracleParameterCollection> with an <xref:System.Data.OracleClient.OracleType> of **Cursor** and a <xref:System.Data.OracleClient.OracleParameter.Direction%2A> of **Output**.</span></span> <span data-ttu-id="afd97-109">Этот поставщик данных поддерживает привязку данных типа REF CURSOR только в качестве выходных параметров.</span><span class="sxs-lookup"><span data-stu-id="afd97-109">The data provider supports binding REF CURSORs as output parameters only.</span></span> <span data-ttu-id="afd97-110">Этот поставщик не поддерживает данные типа REF CURSOR как входные параметры.</span><span class="sxs-lookup"><span data-stu-id="afd97-110">The provider does not support REF CURSORs as input parameters.</span></span>  
  
-   <span data-ttu-id="afd97-111">Получение модуля <xref:System.Data.OracleClient.OracleDataReader> из значения параметра не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="afd97-111">Obtaining an <xref:System.Data.OracleClient.OracleDataReader> from the parameter value is not supported.</span></span> <span data-ttu-id="afd97-112">Значения имеют тип <xref:System.DBNull> после выполнения команды.</span><span class="sxs-lookup"><span data-stu-id="afd97-112">The values are of type <xref:System.DBNull> after command execution.</span></span>  
  
-   <span data-ttu-id="afd97-113">Единственным **CommandBehavior** значение перечисления, которое работает с данными типа REF CURSOR (например, при вызове <xref:System.Data.OracleClient.OracleCommand.ExecuteReader%2A>) является **CloseConnection**; все остальные игнорируются.</span><span class="sxs-lookup"><span data-stu-id="afd97-113">The only **CommandBehavior** enumeration value that works with REF CURSORs (for example, when calling <xref:System.Data.OracleClient.OracleCommand.ExecuteReader%2A>) is **CloseConnection**; all others are ignored.</span></span>  
  
-   <span data-ttu-id="afd97-114">Порядок параметров REF CURSOR в **OracleDataReader** зависит от порядка параметров в **OracleParameterCollection**.</span><span class="sxs-lookup"><span data-stu-id="afd97-114">The order of REF CURSORs in the **OracleDataReader** depends on the order of the parameters in the **OracleParameterCollection**.</span></span> <span data-ttu-id="afd97-115">Свойство <xref:System.Data.OracleClient.OracleParameter.ParameterName%2A> не учитывается.</span><span class="sxs-lookup"><span data-stu-id="afd97-115">The <xref:System.Data.OracleClient.OracleParameter.ParameterName%2A> property is ignored.</span></span>  
  
-   <span data-ttu-id="afd97-116">PL/SQL **таблицы** тип данных не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="afd97-116">The PL/SQL **TABLE** data type is not supported.</span></span> <span data-ttu-id="afd97-117">Но данные типа REF CURSOR являются более эффективными.</span><span class="sxs-lookup"><span data-stu-id="afd97-117">However, REF CURSORs are more efficient.</span></span> <span data-ttu-id="afd97-118">Если необходимо использовать **таблицы** тип данных, используйте OLE DB поставщик данных .NET с MSDAORA.</span><span class="sxs-lookup"><span data-stu-id="afd97-118">If you must use a **TABLE** data type, use the OLE DB .NET Data Provider with MSDAORA.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="afd97-119">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="afd97-119">In This Section</span></span>  
 [<span data-ttu-id="afd97-120">Примеры REF CURSOR</span><span class="sxs-lookup"><span data-stu-id="afd97-120">REF CURSOR Examples</span></span>](../../../../docs/framework/data/adonet/ref-cursor-examples.md)  
 <span data-ttu-id="afd97-121">Содержит три примера, которые демонстрируют использование данных типа REF CURSOR.</span><span class="sxs-lookup"><span data-stu-id="afd97-121">Contains three examples that demonstrate using REF CURSORs.</span></span>  
  
 [<span data-ttu-id="afd97-122">Параметры REF CURSOR в объекте OracleDataReader</span><span class="sxs-lookup"><span data-stu-id="afd97-122">REF CURSOR Parameters in an OracleDataReader</span></span>](../../../../docs/framework/data/adonet/ref-cursor-parameters-in-an-oracledatareader.md)  
 <span data-ttu-id="afd97-123">Показано, как выполнить процедуру хранимых PL/SQL, которая возвращает параметр REF CURSOR и считывает значение как **OracleDataReader**.</span><span class="sxs-lookup"><span data-stu-id="afd97-123">Demonstrates how to execute a PL/SQL stored procedure that returns a REF CURSOR parameter, and reads the value as an **OracleDataReader**.</span></span>  
  
 [<span data-ttu-id="afd97-124">Извлечение данных из нескольких REF CURSOR с использованием OracleDataReader</span><span class="sxs-lookup"><span data-stu-id="afd97-124">Retrieving Data from Multiple REF CURSORs Using an OracleDataReader</span></span>](../../../../docs/framework/data/adonet/retrieving-data-from-multiple-ref-cursors.md)  
 <span data-ttu-id="afd97-125">Показано, как выполнить процедуру хранимых PL/SQL, которая возвращает два параметра REF CURSOR и считывает значения с использованием **OracleDataReader**.</span><span class="sxs-lookup"><span data-stu-id="afd97-125">Demonstrates how to execute a PL/SQL stored procedure that returns two REF CURSOR parameters, and reads the values using an **OracleDataReader**.</span></span>  
  
 [<span data-ttu-id="afd97-126">Заполнение DataSet с помощью одного или нескольких параметров REF CURSOR</span><span class="sxs-lookup"><span data-stu-id="afd97-126">Filling a DataSet Using One or More REF CURSORs</span></span>](../../../../docs/framework/data/adonet/filling-a-dataset-using-one-or-more-ref-cursors.md)  
 <span data-ttu-id="afd97-127">Показывает, как выполнить хранимую процедуру PL/SQL, которая возвращает два параметра REF CURSOR и заполняет <xref:System.Data.DataSet> возвращаемыми строками.</span><span class="sxs-lookup"><span data-stu-id="afd97-127">Demonstrates how to execute a PL/SQL stored procedure that returns two REF CURSOR parameters, and fills a <xref:System.Data.DataSet> with the rows that are returned.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="afd97-128">См. также</span><span class="sxs-lookup"><span data-stu-id="afd97-128">See Also</span></span>  
 [<span data-ttu-id="afd97-129">Oracle и ADO.NET</span><span class="sxs-lookup"><span data-stu-id="afd97-129">Oracle and ADO.NET</span></span>](../../../../docs/framework/data/adonet/oracle-and-adonet.md)  
 [<span data-ttu-id="afd97-130">Центр разработчиков наборов данных и управляемых поставщиков ADO.NET</span><span class="sxs-lookup"><span data-stu-id="afd97-130">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
