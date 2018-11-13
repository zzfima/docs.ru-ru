---
title: Строки подключения в ADO.NET
ms.date: 10/10/2018
ms.assetid: 745c5f95-2f02-4674-b378-6d51a7ec2490
ms.openlocfilehash: 078fdab257115296f9ff00330265cb14ff8674c8
ms.sourcegitcommit: 5fd80619c760fa8c25d33a6f5661247cb65da465
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50409461"
---
# <a name="connection-strings-in-adonet"></a><span data-ttu-id="a1fa2-102">Строки подключения в ADO.NET</span><span class="sxs-lookup"><span data-stu-id="a1fa2-102">Connection Strings in ADO.NET</span></span>

<span data-ttu-id="a1fa2-103">Строка подключения содержит сведения для инициализации, передаваемые в виде параметра от поставщика данных в источник данных.</span><span class="sxs-lookup"><span data-stu-id="a1fa2-103">A connection string contains initialization information that is passed as a parameter from a data provider to a data source.</span></span> <span data-ttu-id="a1fa2-104">Поставщик данных получает строку подключения для параметра <xref:System.Data.Common.DbConnection.ConnectionString?displayProperty=nameWithType> свойство.</span><span class="sxs-lookup"><span data-stu-id="a1fa2-104">The data provider receives the connection string as the value of the <xref:System.Data.Common.DbConnection.ConnectionString?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="a1fa2-105">Поставщик выполняет синтаксический анализ строки подключения и гарантирует, что синтаксис указано правильно и что он поддерживает ключевые слова.</span><span class="sxs-lookup"><span data-stu-id="a1fa2-105">The provider parses the connection string and ensures that the syntax is correct and that the keywords are supported.</span></span> <span data-ttu-id="a1fa2-106">Затем <xref:System.Data.Common.DbConnection.Open?displayProperty=nameWithType> метод передает параметры проанализированный подключения к источнику данных.</span><span class="sxs-lookup"><span data-stu-id="a1fa2-106">Then the <xref:System.Data.Common.DbConnection.Open?displayProperty=nameWithType> method passes the parsed connection parameters to the data source.</span></span> <span data-ttu-id="a1fa2-107">Источник данных выполняет дальнейшие проверки и устанавливает соединение.</span><span class="sxs-lookup"><span data-stu-id="a1fa2-107">The data source performs further validation and establishes a connection.</span></span>

## <a name="connection-string-syntax"></a><span data-ttu-id="a1fa2-108">Синтаксис строки соединения</span><span class="sxs-lookup"><span data-stu-id="a1fa2-108">Connection string syntax</span></span>

<span data-ttu-id="a1fa2-109">Строка подключения — список разделенных точкой с запятой пар ключ/значение параметра:</span><span class="sxs-lookup"><span data-stu-id="a1fa2-109">A connection string is a semicolon-delimited list of key/value parameter pairs:</span></span>
  
    keyword1=value; keyword2=value;
  
<span data-ttu-id="a1fa2-110">Ключевые слова не учитывают регистр.</span><span class="sxs-lookup"><span data-stu-id="a1fa2-110">Keywords are not case-sensitive.</span></span> <span data-ttu-id="a1fa2-111">Значения, тем не менее, могут быть с учетом регистра, в зависимости от источника данных.</span><span class="sxs-lookup"><span data-stu-id="a1fa2-111">Values, however, may be case-sensitive, depending on the data source.</span></span> <span data-ttu-id="a1fa2-112">Ключевые слова и значения могут содержать [пробельных символов](https://en.wikipedia.org/wiki/Whitespace_character#Unicode).</span><span class="sxs-lookup"><span data-stu-id="a1fa2-112">Both keywords and values may contain [whitespace characters](https://en.wikipedia.org/wiki/Whitespace_character#Unicode).</span></span> <span data-ttu-id="a1fa2-113">Начальные и конечные пробелы пропускается в ключевые слова и не заключаться в кавычки значения.</span><span class="sxs-lookup"><span data-stu-id="a1fa2-113">Leading and trailing white space is ignored in keywords and unquoted values.</span></span>

<span data-ttu-id="a1fa2-114">Если значение содержит точку с запятой, [управляющие символы Юникода](https://en.wikipedia.org/wiki/Unicode_control_characters), или начальные или конечные пробелы, то он должен быть заключен в одинарные или двойные кавычки.</span><span class="sxs-lookup"><span data-stu-id="a1fa2-114">If a value contains the semicolon, [Unicode control characters](https://en.wikipedia.org/wiki/Unicode_control_characters), or leading or trailing white space, it must be enclosed in single or double quotation marks.</span></span> <span data-ttu-id="a1fa2-115">Пример:</span><span class="sxs-lookup"><span data-stu-id="a1fa2-115">For example:</span></span>

    Keyword=" whitespace  ";
    Keyword='special;character';

<span data-ttu-id="a1fa2-116">Внешний символ может не произойти в значении, он помещает.</span><span class="sxs-lookup"><span data-stu-id="a1fa2-116">The enclosing character may not occur within the value it encloses.</span></span> <span data-ttu-id="a1fa2-117">Таким образом значение, содержащее одинарные кавычки могут быть заключены только в двойные кавычки и наоборот:</span><span class="sxs-lookup"><span data-stu-id="a1fa2-117">Therefore, a value containing single quotation marks can be enclosed only in double quotation marks, and vice versa:</span></span>

    Keyword='double"quotation;mark';
    Keyword="single'quotation;mark";

<span data-ttu-id="a1fa2-118">Сами кавычки, а также знак равенства не требуют escape-преобразование, поэтому в следующей строке подключения являются допустимыми:</span><span class="sxs-lookup"><span data-stu-id="a1fa2-118">The quotation marks themselves, as well as the equals sign, do not require escaping, so the following connection strings are valid:</span></span>

    Keyword=no "escaping" 'required';
    Keyword=a=b=c

<span data-ttu-id="a1fa2-119">Так как каждое значение считывается до следующей точки с запятой или конца строки, в последнем примере значение `a=b=c`, и окончательный точка с запятой является необязательным.</span><span class="sxs-lookup"><span data-stu-id="a1fa2-119">Since each value is read till the next semicolon or the end of string, the value in the latter example is `a=b=c`, and the final semicolon is optional.</span></span>

<span data-ttu-id="a1fa2-120">Все строки подключения совместно использовать тот же базовый синтаксис, описанных выше.</span><span class="sxs-lookup"><span data-stu-id="a1fa2-120">All connection strings share the same basic syntax described above.</span></span> <span data-ttu-id="a1fa2-121">Набор ключевых слов, распознаваемым зависит от поставщика, однако и развивалась со временем от ранних API-интерфейсов, таких как *ODBC*.</span><span class="sxs-lookup"><span data-stu-id="a1fa2-121">The set of recognized keywords depends on the provider, however, and has evolved over the years from earlier APIs such as *ODBC*.</span></span> <span data-ttu-id="a1fa2-122">*.NET Framework* поставщик данных для *SQL Server* (`SqlClient`) поддерживает многие ключевые слова из старых API хостинга, но, как правило, более гибок и принимает синонимы для многих распространенных строки подключения ключевые слова.</span><span class="sxs-lookup"><span data-stu-id="a1fa2-122">The *.NET Framework* data provider for *SQL Server* (`SqlClient`) supports many keywords from older APIs, but is generally more flexible and accepts synonyms for many of the common connection string keywords.</span></span>

<span data-ttu-id="a1fa2-123">Опечатки может привести к ошибкам.</span><span class="sxs-lookup"><span data-stu-id="a1fa2-123">Typing mistakes can cause errors.</span></span> <span data-ttu-id="a1fa2-124">Например `Integrated Security=true` является допустимым, но `IntegratedSecurity=true` приводит к ошибке.</span><span class="sxs-lookup"><span data-stu-id="a1fa2-124">For example, `Integrated Security=true` is valid, but `IntegratedSecurity=true` causes an error.</span></span>

<span data-ttu-id="a1fa2-125">Строки соединения вручную из непроверенных пользовательских входных данных во время выполнения уязвимы для атак внедрения в строку и подвергнуть риску безопасность источника данных.</span><span class="sxs-lookup"><span data-stu-id="a1fa2-125">Connection strings constructed manually at run time from unvalidated user input are vulnerable to string-injection attacks and jeopardize security at the data source.</span></span> <span data-ttu-id="a1fa2-126">Для решения этих проблем *ADO.NET* 2.0 введена [построители строк подключения](../../../../docs/framework/data/adonet/connection-string-builders.md) для каждого *.NET Framework* поставщика данных.</span><span class="sxs-lookup"><span data-stu-id="a1fa2-126">To address these problems, *ADO.NET* 2.0 introduced [connection string builders](../../../../docs/framework/data/adonet/connection-string-builders.md) for each *.NET Framework* data provider.</span></span> <span data-ttu-id="a1fa2-127">Эти построители строк подключения предоставлять параметры в качестве строго типизированных свойств и сделать его можно проверить строку подключения, перед их отправкой к источнику данных.</span><span class="sxs-lookup"><span data-stu-id="a1fa2-127">These connection string builders expose parameters as strongly-typed properties, and make it possible to validate the connection string before it's sent to the data source.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="a1fa2-128">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="a1fa2-128">In This Section</span></span>  
 [<span data-ttu-id="a1fa2-129">Построители строк подключения</span><span class="sxs-lookup"><span data-stu-id="a1fa2-129">Connection String Builders</span></span>](../../../../docs/framework/data/adonet/connection-string-builders.md)  
 <span data-ttu-id="a1fa2-130">Демонстрирует использование классов `ConnectionStringBuilder` для создания достоверных строк соединения во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="a1fa2-130">Demonstrates how to use the `ConnectionStringBuilder` classes to construct valid connection strings at run time.</span></span>
  
 [<span data-ttu-id="a1fa2-131">Строки подключения и файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="a1fa2-131">Connection Strings and Configuration Files</span></span>](../../../../docs/framework/data/adonet/connection-strings-and-configuration-files.md)  
 <span data-ttu-id="a1fa2-132">Демонстрирует хранение и получение строк соединения в файлах конфигурации.</span><span class="sxs-lookup"><span data-stu-id="a1fa2-132">Demonstrates how to store and retrieve connection strings in configuration files.</span></span>
  
 [<span data-ttu-id="a1fa2-133">Синтаксис строки подключения</span><span class="sxs-lookup"><span data-stu-id="a1fa2-133">Connection String Syntax</span></span>](../../../../docs/framework/data/adonet/connection-string-syntax.md)  
 <span data-ttu-id="a1fa2-134">Описывает настройку строк соединения, зависящих от поставщика, для `SqlClient`, `OracleClient`, `OleDb` и `Odbc`.</span><span class="sxs-lookup"><span data-stu-id="a1fa2-134">Describes how to configure provider-specific connection strings for `SqlClient`, `OracleClient`, `OleDb`, and `Odbc`.</span></span>
  
 [<span data-ttu-id="a1fa2-135">Защита сведений о подключении</span><span class="sxs-lookup"><span data-stu-id="a1fa2-135">Protecting Connection Information</span></span>](../../../../docs/framework/data/adonet/protecting-connection-information.md)  
 <span data-ttu-id="a1fa2-136">Демонстрирует методы защиты сведений, используемых для подключения к источнику данных.</span><span class="sxs-lookup"><span data-stu-id="a1fa2-136">Demonstrates techniques for protecting information used to connect to a data source.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="a1fa2-137">См. также</span><span class="sxs-lookup"><span data-stu-id="a1fa2-137">See Also</span></span>  
 [<span data-ttu-id="a1fa2-138">Подключение к источнику данных</span><span class="sxs-lookup"><span data-stu-id="a1fa2-138">Connecting to a Data Source</span></span>](/cpp/data/odbc/connecting-to-a-data-source)  
 [<span data-ttu-id="a1fa2-139">Центр разработчиков наборов данных и управляемых поставщиков ADO.NET</span><span class="sxs-lookup"><span data-stu-id="a1fa2-139">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
