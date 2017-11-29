---
title: "Строки подключения в ADO.NET"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 745c5f95-2f02-4674-b378-6d51a7ec2490
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: bd787373b869c31727cfc0d027b6b98774b0d630
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="connection-strings-in-adonet"></a><span data-ttu-id="b02fd-102">Строки подключения в ADO.NET</span><span class="sxs-lookup"><span data-stu-id="b02fd-102">Connection Strings in ADO.NET</span></span>
<span data-ttu-id="b02fd-103">Платформа .NET Framework 2.0 предоставляет новые возможности для работы со строками подключения, включая представление новых ключевых слов для классов построителей строк подключения, упрощающих создание допустимых строк подключения во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="b02fd-103">The .NET Framework 2.0 introduced new capabilities for working with connection strings, including the introduction of new keywords to the connection string builder classes, which facilitate creating valid connection strings at run time.</span></span>  
  
 <span data-ttu-id="b02fd-104">Строка подключения содержит сведения для инициализации, передаваемые в виде параметра от поставщика данных в источник данных.</span><span class="sxs-lookup"><span data-stu-id="b02fd-104">A connection string contains initialization information that is passed as a parameter from a data provider to a data source.</span></span> <span data-ttu-id="b02fd-105">Синтаксис зависит от поставщика данных, и при попытке открыть соединение строка соединения анализируется.</span><span class="sxs-lookup"><span data-stu-id="b02fd-105">The syntax depends on the data provider, and the connection string is parsed during the attempt to open a connection.</span></span> <span data-ttu-id="b02fd-106">Синтаксические ошибки формируют исключение во время выполнения, а другие ошибки происходят после получения источником данных сведений о соединении.</span><span class="sxs-lookup"><span data-stu-id="b02fd-106">Syntax errors generate a run-time exception, but other errors occur only after the data source receives connection information.</span></span> <span data-ttu-id="b02fd-107">После проверки источник данных применяет параметры, указанные в строке соединения, и открывает соединение.</span><span class="sxs-lookup"><span data-stu-id="b02fd-107">Once validated, the data source applies the options specified in the connection string and opens the connection.</span></span>  
  
 <span data-ttu-id="b02fd-108">Формат строки соединения является списком разделенных точкой с запятой пар параметров «ключ-значение»:</span><span class="sxs-lookup"><span data-stu-id="b02fd-108">The format of a connection string is a semicolon-delimited list of key/value parameter pairs:</span></span>  
  
 `keyword1=value; keyword2=value;`  
  
 <span data-ttu-id="b02fd-109">Ключевые слова не учитывают регистр, и пробелы между парами «ключ-значение» не учитываются.</span><span class="sxs-lookup"><span data-stu-id="b02fd-109">Keywords are not case sensitive, and spaces between key/value pairs are ignored.</span></span> <span data-ttu-id="b02fd-110">Однако значения могут учитывать регистр в зависимости от источника данных.</span><span class="sxs-lookup"><span data-stu-id="b02fd-110">However, values may be case sensitive, depending on the data source.</span></span> <span data-ttu-id="b02fd-111">Значения, содержащие точку с запятой, одиночные кавычки или двойные кавычки, должны быть заключены в двойные кавычки.</span><span class="sxs-lookup"><span data-stu-id="b02fd-111">Any values containing a semicolon, single quotation marks, or double quotation marks must be enclosed in double quotation marks.</span></span>  
  
 <span data-ttu-id="b02fd-112">Синтаксис допустимой строки соединения зависит от поставщика и развивается со временем от ранних API-интерфейсов, таких как ODBC.</span><span class="sxs-lookup"><span data-stu-id="b02fd-112">Valid connection string syntax depends on the provider, and has evolved over the years from earlier APIs like ODBC.</span></span> <span data-ttu-id="b02fd-113">Поставщик данных .NET Framework для SQL Server (SqlClient) содержит многие элементы старого синтаксиса и, как правило, более гибок с основным синтаксисом строки соединения.</span><span class="sxs-lookup"><span data-stu-id="b02fd-113">The .NET Framework Data Provider for SQL Server (SqlClient) incorporates many elements from older syntax and is generally more flexible with common connection string syntax.</span></span> <span data-ttu-id="b02fd-114">Для элементов синтаксиса строки соединения существуют допустимые синонимы, но некоторые ошибки синтаксиса и написания могут вызвать проблемы.</span><span class="sxs-lookup"><span data-stu-id="b02fd-114">There are frequently equally valid synonyms for connection string syntax elements, but some syntax and spelling errors can cause problems.</span></span> <span data-ttu-id="b02fd-115">Например, «`Integrated Security=true`» - достоверно, в то время как «`IntegratedSecurity=true`» вызывает ошибку.</span><span class="sxs-lookup"><span data-stu-id="b02fd-115">For example, "`Integrated Security=true`" is valid, whereas "`IntegratedSecurity=true`" causes an error.</span></span> <span data-ttu-id="b02fd-116">Кроме того, строки соединения, создаваемые из непроверенных пользовательских входных данных во время выполнения, могут привести к атакам путем внедрения данных в строку, подвергающим риску безопасность источника данных.</span><span class="sxs-lookup"><span data-stu-id="b02fd-116">In addition, connection strings constructed at run time from unvalidated user input can lead to string injection attacks, jeopardizing security at the data source.</span></span>  
  
 <span data-ttu-id="b02fd-117">Для решения этих проблем ADO.NET версии 2.0 предоставляет новые построители строк подключений для каждого поставщика данных .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b02fd-117">To address these problems, ADO.NET 2.0 introduced new connection string builders for each .NET Framework data provider.</span></span> <span data-ttu-id="b02fd-118">Ключевые слова представляются в виде свойств, позволяя проверять синтаксис строки соединения перед передачей источника данных.</span><span class="sxs-lookup"><span data-stu-id="b02fd-118">Keywords are exposed as properties, enabling connection string syntax to be validated before submission to the data source.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b02fd-119">Содержание</span><span class="sxs-lookup"><span data-stu-id="b02fd-119">In This Section</span></span>  
 [<span data-ttu-id="b02fd-120">Построители строк подключения</span><span class="sxs-lookup"><span data-stu-id="b02fd-120">Connection String Builders</span></span>](../../../../docs/framework/data/adonet/connection-string-builders.md)  
 <span data-ttu-id="b02fd-121">Демонстрирует использование классов `ConnectionStringBuilder` для создания достоверных строк соединения во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="b02fd-121">Demonstrates how to use the `ConnectionStringBuilder` classes to construct valid connection strings at run time.</span></span>  
  
 [<span data-ttu-id="b02fd-122">Строки соединения и файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="b02fd-122">Connection Strings and Configuration Files</span></span>](../../../../docs/framework/data/adonet/connection-strings-and-configuration-files.md)  
 <span data-ttu-id="b02fd-123">Демонстрирует хранение и получение строк соединения в файлах конфигурации.</span><span class="sxs-lookup"><span data-stu-id="b02fd-123">Demonstrates how to store and retrieve connection strings in configuration files.</span></span>  
  
 [<span data-ttu-id="b02fd-124">Синтаксис строки соединения</span><span class="sxs-lookup"><span data-stu-id="b02fd-124">Connection String Syntax</span></span>](../../../../docs/framework/data/adonet/connection-string-syntax.md)  
 <span data-ttu-id="b02fd-125">Описывает настройку строк соединения, зависящих от поставщика, для `SqlClient`, `OracleClient`, `OleDb` и `Odbc`.</span><span class="sxs-lookup"><span data-stu-id="b02fd-125">Describes how to configure provider-specific connection strings for `SqlClient`, `OracleClient`, `OleDb`, and `Odbc`.</span></span>  
  
 [<span data-ttu-id="b02fd-126">Защита сведений о подключении</span><span class="sxs-lookup"><span data-stu-id="b02fd-126">Protecting Connection Information</span></span>](../../../../docs/framework/data/adonet/protecting-connection-information.md)  
 <span data-ttu-id="b02fd-127">Демонстрирует методы защиты сведений, используемых для подключения к источнику данных.</span><span class="sxs-lookup"><span data-stu-id="b02fd-127">Demonstrates techniques for protecting information used to connect to a data source.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b02fd-128">См. также</span><span class="sxs-lookup"><span data-stu-id="b02fd-128">See Also</span></span>  
 [<span data-ttu-id="b02fd-129">Подключение к источнику данных</span><span class="sxs-lookup"><span data-stu-id="b02fd-129">Connecting to a Data Source</span></span>](/cpp/data/odbc/connecting-to-a-data-source)  
 [<span data-ttu-id="b02fd-130">Центр разработчиков наборов данных и управляемых поставщиков ADO.NET</span><span class="sxs-lookup"><span data-stu-id="b02fd-130">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
