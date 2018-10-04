---
title: Строки подключения в ADO.NET
ms.date: 03/30/2017
ms.assetid: 745c5f95-2f02-4674-b378-6d51a7ec2490
ms.openlocfilehash: 1e6e2b6870195c99279639e1f4576a30b7126d4d
ms.sourcegitcommit: 69229651598b427c550223d3c58aba82e47b3f82
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/04/2018
ms.locfileid: "48583699"
---
# <a name="connection-strings-in-adonet"></a><span data-ttu-id="323dc-102">Строки подключения в ADO.NET</span><span class="sxs-lookup"><span data-stu-id="323dc-102">Connection Strings in ADO.NET</span></span>
<span data-ttu-id="323dc-103">Платформа .NET Framework 2.0 предоставляет новые возможности для работы со строками подключения, включая представление новых ключевых слов для классов построителей строк подключения, упрощающих создание допустимых строк подключения во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="323dc-103">The .NET Framework 2.0 introduced new capabilities for working with connection strings, including the introduction of new keywords to the connection string builder classes, which facilitate creating valid connection strings at run time.</span></span>  
  
<span data-ttu-id="323dc-104">Строка подключения содержит сведения для инициализации, передаваемые в виде параметра от поставщика данных в источник данных.</span><span class="sxs-lookup"><span data-stu-id="323dc-104">A connection string contains initialization information that is passed as a parameter from a data provider to a data source.</span></span> <span data-ttu-id="323dc-105">Синтаксис зависит от поставщика данных, и при попытке открыть соединение строка соединения анализируется.</span><span class="sxs-lookup"><span data-stu-id="323dc-105">The syntax depends on the data provider, and the connection string is parsed during the attempt to open a connection.</span></span> <span data-ttu-id="323dc-106">Синтаксические ошибки формируют исключение во время выполнения, а другие ошибки происходят после получения источником данных сведений о соединении.</span><span class="sxs-lookup"><span data-stu-id="323dc-106">Syntax errors generate a run-time exception, but other errors occur only after the data source receives connection information.</span></span> <span data-ttu-id="323dc-107">После проверки источник данных применяет параметры, указанные в строке соединения, и открывает соединение.</span><span class="sxs-lookup"><span data-stu-id="323dc-107">Once validated, the data source applies the options specified in the connection string and opens the connection.</span></span>
  
<span data-ttu-id="323dc-108">Формат строки соединения является списком разделенных точкой с запятой пар параметров «ключ-значение»:</span><span class="sxs-lookup"><span data-stu-id="323dc-108">The format of a connection string is a semicolon-delimited list of key/value parameter pairs:</span></span>
  
    keyword1=value; keyword2=value;
  
<span data-ttu-id="323dc-109">Ключевые слова не учитывают регистр.</span><span class="sxs-lookup"><span data-stu-id="323dc-109">Keywords are not case-sensitive.</span></span> <span data-ttu-id="323dc-110">Значения, тем не менее, могут быть с учетом регистра, в зависимости от источника данных.</span><span class="sxs-lookup"><span data-stu-id="323dc-110">Values, however, may be case-sensitive, depending on the data source.</span></span> <span data-ttu-id="323dc-111">Ключевые слова и значения могут содержать [пробельных символов](https://en.wikipedia.org/wiki/Whitespace_character#Unicode), несмотря на то, что начальные и конечные пробелы игнорируются в ключевые слова и не заключаться в кавычки значения.</span><span class="sxs-lookup"><span data-stu-id="323dc-111">Both keywords and values may contain [whitespace characters](https://en.wikipedia.org/wiki/Whitespace_character#Unicode), although leading and trailing whitespace is ignored in keywords and unquoted values.</span></span>

<span data-ttu-id="323dc-112">Если значение содержит точку с запятой, [управляющие символы Юникода](https://en.wikipedia.org/wiki/Unicode_control_characters), начальные или конечные пробелы, он должен быть заключен в одинарные или двойные кавычки, например:</span><span class="sxs-lookup"><span data-stu-id="323dc-112">If a value contains the semicolon, [Unicode control characters](https://en.wikipedia.org/wiki/Unicode_control_characters), leading or trailing whitespace it must be enclosed in single or double quotation marks, e.g.:</span></span>

    Keyword=" whitespace  ";
    Keyword='special;character';

<span data-ttu-id="323dc-113">Внешний символ может не произойти в значении, он помещает.</span><span class="sxs-lookup"><span data-stu-id="323dc-113">The enclosing character may not occur within the value it encloses.</span></span> <span data-ttu-id="323dc-114">Таким образом значение, содержащее одинарные кавычки могут быть заключены только в двойные кавычки и наоборот:</span><span class="sxs-lookup"><span data-stu-id="323dc-114">Therefore, a value containing single quotation marks can be enclosed only in double quotation marks and vice versa:</span></span>

    Keyword='double"quotation;mark';
    Keyword="single'quotation;mark";

<span data-ttu-id="323dc-115">Сами кавычки, а также знак равенства не требуют escape-преобразование, поэтому в следующей строке подключения являются допустимыми:</span><span class="sxs-lookup"><span data-stu-id="323dc-115">The quotation marks themselves, as well as the equals sign, do not require escaping, so the following connection strings are valid:</span></span>

    Keyword=no "escaping" 'required';
    Keyword=a=b=c

<span data-ttu-id="323dc-116">Так как каждое значение считывается до следующей точки с запятой или конца строки, в последнем примере значение `a=b=c`, и окончательный точка с запятой является необязательным.</span><span class="sxs-lookup"><span data-stu-id="323dc-116">Since each value is read till the next semicolon or the end of string, the value in the latter example is `a=b=c`, and the final semicolon is optional.</span></span>

<span data-ttu-id="323dc-117">Синтаксис допустимой строки соединения зависит от поставщика и развивается со временем от ранних API-интерфейсов, таких как ODBC.</span><span class="sxs-lookup"><span data-stu-id="323dc-117">Valid connection string syntax depends on the provider, and has evolved over the years from earlier APIs like ODBC.</span></span> <span data-ttu-id="323dc-118">Поставщик данных .NET Framework для SQL Server (SqlClient) содержит многие элементы старого синтаксиса и, как правило, более гибок с основным синтаксисом строки соединения.</span><span class="sxs-lookup"><span data-stu-id="323dc-118">The .NET Framework Data Provider for SQL Server (SqlClient) incorporates many elements from older syntax and is generally more flexible with common connection string syntax.</span></span> <span data-ttu-id="323dc-119">Для элементов синтаксиса строки соединения существуют допустимые синонимы, но некоторые ошибки синтаксиса и написания могут вызвать проблемы.</span><span class="sxs-lookup"><span data-stu-id="323dc-119">There are frequently equally valid synonyms for connection string syntax elements, but some syntax and spelling errors can cause problems.</span></span> <span data-ttu-id="323dc-120">Например, «`Integrated Security=true`» - достоверно, в то время как «`IntegratedSecurity=true`» вызывает ошибку.</span><span class="sxs-lookup"><span data-stu-id="323dc-120">For example, "`Integrated Security=true`" is valid, whereas "`IntegratedSecurity=true`" causes an error.</span></span> <span data-ttu-id="323dc-121">Кроме того, строки соединения, создаваемые из непроверенных пользовательских входных данных во время выполнения, могут привести к атакам путем внедрения данных в строку, подвергающим риску безопасность источника данных.</span><span class="sxs-lookup"><span data-stu-id="323dc-121">In addition, connection strings constructed at run time from unvalidated user input can lead to string injection attacks, jeopardizing security at the data source.</span></span>
  
<span data-ttu-id="323dc-122">Для решения этих проблем ADO.NET версии 2.0 предоставляет новые построители строк подключений для каждого поставщика данных .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="323dc-122">To address these problems, ADO.NET 2.0 introduced new connection string builders for each .NET Framework data provider.</span></span> <span data-ttu-id="323dc-123">Ключевые слова представляются в виде свойств, позволяя проверять синтаксис строки соединения перед передачей источника данных.</span><span class="sxs-lookup"><span data-stu-id="323dc-123">Keywords are exposed as properties, enabling connection string syntax to be validated before submission to the data source.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="323dc-124">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="323dc-124">In This Section</span></span>  
 [<span data-ttu-id="323dc-125">Построители строк подключения</span><span class="sxs-lookup"><span data-stu-id="323dc-125">Connection String Builders</span></span>](../../../../docs/framework/data/adonet/connection-string-builders.md)  
 <span data-ttu-id="323dc-126">Демонстрирует использование классов `ConnectionStringBuilder` для создания достоверных строк соединения во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="323dc-126">Demonstrates how to use the `ConnectionStringBuilder` classes to construct valid connection strings at run time.</span></span>
  
 [<span data-ttu-id="323dc-127">Строки подключения и файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="323dc-127">Connection Strings and Configuration Files</span></span>](../../../../docs/framework/data/adonet/connection-strings-and-configuration-files.md)  
 <span data-ttu-id="323dc-128">Демонстрирует хранение и получение строк соединения в файлах конфигурации.</span><span class="sxs-lookup"><span data-stu-id="323dc-128">Demonstrates how to store and retrieve connection strings in configuration files.</span></span>
  
 [<span data-ttu-id="323dc-129">Синтаксис строки подключения</span><span class="sxs-lookup"><span data-stu-id="323dc-129">Connection String Syntax</span></span>](../../../../docs/framework/data/adonet/connection-string-syntax.md)  
 <span data-ttu-id="323dc-130">Описывает настройку строк соединения, зависящих от поставщика, для `SqlClient`, `OracleClient`, `OleDb` и `Odbc`.</span><span class="sxs-lookup"><span data-stu-id="323dc-130">Describes how to configure provider-specific connection strings for `SqlClient`, `OracleClient`, `OleDb`, and `Odbc`.</span></span>
  
 [<span data-ttu-id="323dc-131">Защита сведений о подключении</span><span class="sxs-lookup"><span data-stu-id="323dc-131">Protecting Connection Information</span></span>](../../../../docs/framework/data/adonet/protecting-connection-information.md)  
 <span data-ttu-id="323dc-132">Демонстрирует методы защиты сведений, используемых для подключения к источнику данных.</span><span class="sxs-lookup"><span data-stu-id="323dc-132">Demonstrates techniques for protecting information used to connect to a data source.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="323dc-133">См. также</span><span class="sxs-lookup"><span data-stu-id="323dc-133">See Also</span></span>  
 [<span data-ttu-id="323dc-134">Подключение к источнику данных</span><span class="sxs-lookup"><span data-stu-id="323dc-134">Connecting to a Data Source</span></span>](/cpp/data/odbc/connecting-to-a-data-source)  
 [<span data-ttu-id="323dc-135">Центр разработчиков наборов данных и управляемых поставщиков ADO.NET</span><span class="sxs-lookup"><span data-stu-id="323dc-135">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
