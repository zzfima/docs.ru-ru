---
title: Строки подключения в ADO.NET
ms.date: 10/10/2018
ms.assetid: 745c5f95-2f02-4674-b378-6d51a7ec2490
ms.openlocfilehash: 02fe8d984f1287673477bb142b3f9626e248898e
ms.sourcegitcommit: 30a83efb57c468da74e9e218de26cf88d3254597
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/20/2019
ms.locfileid: "68363745"
---
# <a name="connection-strings-in-adonet"></a><span data-ttu-id="9ad9c-102">Строки подключения в ADO.NET</span><span class="sxs-lookup"><span data-stu-id="9ad9c-102">Connection Strings in ADO.NET</span></span>

<span data-ttu-id="9ad9c-103">Строка подключения содержит сведения для инициализации, передаваемые в виде параметра от поставщика данных в источник данных.</span><span class="sxs-lookup"><span data-stu-id="9ad9c-103">A connection string contains initialization information that is passed as a parameter from a data provider to a data source.</span></span> <span data-ttu-id="9ad9c-104">Поставщик данных получает строку подключения в качестве значения <xref:System.Data.Common.DbConnection.ConnectionString?displayProperty=nameWithType> свойства.</span><span class="sxs-lookup"><span data-stu-id="9ad9c-104">The data provider receives the connection string as the value of the <xref:System.Data.Common.DbConnection.ConnectionString?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="9ad9c-105">Поставщик анализирует строку подключения и проверяет правильность синтаксиса и наличие ключевых слов.</span><span class="sxs-lookup"><span data-stu-id="9ad9c-105">The provider parses the connection string and ensures that the syntax is correct and that the keywords are supported.</span></span> <span data-ttu-id="9ad9c-106"><xref:System.Data.Common.DbConnection.Open?displayProperty=nameWithType> Затем метод передает проанализированные параметры соединения в источник данных.</span><span class="sxs-lookup"><span data-stu-id="9ad9c-106">Then the <xref:System.Data.Common.DbConnection.Open?displayProperty=nameWithType> method passes the parsed connection parameters to the data source.</span></span> <span data-ttu-id="9ad9c-107">Источник данных выполняет дальнейшую проверку и устанавливает соединение.</span><span class="sxs-lookup"><span data-stu-id="9ad9c-107">The data source performs further validation and establishes a connection.</span></span>

## <a name="connection-string-syntax"></a><span data-ttu-id="9ad9c-108">Синтаксис строки подключения</span><span class="sxs-lookup"><span data-stu-id="9ad9c-108">Connection string syntax</span></span>

<span data-ttu-id="9ad9c-109">Строка подключения представляет собой разделенный точками с запятой список пар параметров "ключ-значение":</span><span class="sxs-lookup"><span data-stu-id="9ad9c-109">A connection string is a semicolon-delimited list of key/value parameter pairs:</span></span>

```
keyword1=value; keyword2=value;
```

<span data-ttu-id="9ad9c-110">В ключевых словах регистр не учитывается.</span><span class="sxs-lookup"><span data-stu-id="9ad9c-110">Keywords are not case-sensitive.</span></span> <span data-ttu-id="9ad9c-111">При этом значения в зависимости от источника данных могут быть чувствительны к регистру.</span><span class="sxs-lookup"><span data-stu-id="9ad9c-111">Values, however, may be case-sensitive, depending on the data source.</span></span> <span data-ttu-id="9ad9c-112">Ключевые слова и значения могут содержать [символы пробела](https://en.wikipedia.org/wiki/Whitespace_character#Unicode).</span><span class="sxs-lookup"><span data-stu-id="9ad9c-112">Both keywords and values may contain [whitespace characters](https://en.wikipedia.org/wiki/Whitespace_character#Unicode).</span></span> <span data-ttu-id="9ad9c-113">Начальные и конечные пробелы игнорируются в ключевых словах и в значениях, не заключенных в кавычки.</span><span class="sxs-lookup"><span data-stu-id="9ad9c-113">Leading and trailing white space is ignored in keywords and unquoted values.</span></span>

<span data-ttu-id="9ad9c-114">Если значение содержит точку с запятой, [управляющие символы Юникода](https://en.wikipedia.org/wiki/Unicode_control_characters)или начальные или конечные пробелы, их необходимо заключить в одинарные или двойные кавычки.</span><span class="sxs-lookup"><span data-stu-id="9ad9c-114">If a value contains the semicolon, [Unicode control characters](https://en.wikipedia.org/wiki/Unicode_control_characters), or leading or trailing white space, it must be enclosed in single or double quotation marks.</span></span> <span data-ttu-id="9ad9c-115">Например:</span><span class="sxs-lookup"><span data-stu-id="9ad9c-115">For example:</span></span>

```
Keyword=" whitespace  ";
Keyword='special;character';
```

<span data-ttu-id="9ad9c-116">Окружающий символ может не находиться в заключенном в нем значении.</span><span class="sxs-lookup"><span data-stu-id="9ad9c-116">The enclosing character may not occur within the value it encloses.</span></span> <span data-ttu-id="9ad9c-117">Таким образом, значение, содержащее одинарные кавычки, может быть заключено только в двойные кавычки и наоборот:</span><span class="sxs-lookup"><span data-stu-id="9ad9c-117">Therefore, a value containing single quotation marks can be enclosed only in double quotation marks, and vice versa:</span></span>

```
Keyword='double"quotation;mark';
Keyword="single'quotation;mark";
```

<span data-ttu-id="9ad9c-118">Можно также поэкранировать окружающий символ, используя два из них:</span><span class="sxs-lookup"><span data-stu-id="9ad9c-118">You can also escape the enclosing character by using two of them together:</span></span>

```
Keyword="double""quotation";
Keyword='single''quotation';
```

<span data-ttu-id="9ad9c-119">Кавычки, а также знак равенства не требуются для экранирования, поэтому следующие строки соединения являются допустимыми:</span><span class="sxs-lookup"><span data-stu-id="9ad9c-119">The quotation marks themselves, as well as the equals sign, do not require escaping, so the following connection strings are valid:</span></span>

```
Keyword=no "escaping" 'required';
Keyword=a=b=c
```

<span data-ttu-id="9ad9c-120">Так как каждое значение считывается до следующей точки с запятой или конца строки, значение в последнем примере равно `a=b=c`, а конечная точка с запятой является необязательной.</span><span class="sxs-lookup"><span data-stu-id="9ad9c-120">Since each value is read till the next semicolon or the end of string, the value in the latter example is `a=b=c`, and the final semicolon is optional.</span></span>

<span data-ttu-id="9ad9c-121">Все строки подключения имеют один и тот же базовый синтаксис, описанный выше.</span><span class="sxs-lookup"><span data-stu-id="9ad9c-121">All connection strings share the same basic syntax described above.</span></span> <span data-ttu-id="9ad9c-122">Набор распознаваемых ключевых слов зависит от поставщика, но в течение многих лет он превратился в предыдущие API-интерфейсы, такие как *ODBC*.</span><span class="sxs-lookup"><span data-stu-id="9ad9c-122">The set of recognized keywords depends on the provider, however, and has evolved over the years from earlier APIs such as *ODBC*.</span></span> <span data-ttu-id="9ad9c-123">Поставщик данных *.NET Framework* для *SQL Server* (`SqlClient`) поддерживает много ключевых слов из старых API-интерфейсов, но обычно является более гибким и принимает синонимы для многих общих ключевых слов строки подключения.</span><span class="sxs-lookup"><span data-stu-id="9ad9c-123">The *.NET Framework* data provider for *SQL Server* (`SqlClient`) supports many keywords from older APIs, but is generally more flexible and accepts synonyms for many of the common connection string keywords.</span></span>

<span data-ttu-id="9ad9c-124">При вводе ошибок могут возникать ошибки.</span><span class="sxs-lookup"><span data-stu-id="9ad9c-124">Typing mistakes can cause errors.</span></span> <span data-ttu-id="9ad9c-125">Например, `Integrated Security=true` является допустимым, но `IntegratedSecurity=true` вызывает ошибку.</span><span class="sxs-lookup"><span data-stu-id="9ad9c-125">For example, `Integrated Security=true` is valid, but `IntegratedSecurity=true` causes an error.</span></span>

<span data-ttu-id="9ad9c-126">Строки подключения, созданные вручную во время выполнения из непроверенных входных данных, уязвимы для атак путем внедрения строк и поддают риску безопасность в источнике данных.</span><span class="sxs-lookup"><span data-stu-id="9ad9c-126">Connection strings constructed manually at run time from unvalidated user input are vulnerable to string-injection attacks and jeopardize security at the data source.</span></span> <span data-ttu-id="9ad9c-127">Для решения этих проблем в *ADO.NET* 2,0 появились [построители строк подключения](../../../../docs/framework/data/adonet/connection-string-builders.md) для каждого *.NET Framework* поставщика данных.</span><span class="sxs-lookup"><span data-stu-id="9ad9c-127">To address these problems, *ADO.NET* 2.0 introduced [connection string builders](../../../../docs/framework/data/adonet/connection-string-builders.md) for each *.NET Framework* data provider.</span></span> <span data-ttu-id="9ad9c-128">Эти построители строк подключения предоставляют параметры в виде строго типизированных свойств и позволяют проверить строку подключения перед отправкой в источник данных.</span><span class="sxs-lookup"><span data-stu-id="9ad9c-128">These connection string builders expose parameters as strongly-typed properties, and make it possible to validate the connection string before it's sent to the data source.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="9ad9c-129">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="9ad9c-129">In This Section</span></span>

<span data-ttu-id="9ad9c-130">[Построители строк подключения](../../../../docs/framework/data/adonet/connection-string-builders.md)</span><span class="sxs-lookup"><span data-stu-id="9ad9c-130">[Connection String Builders](../../../../docs/framework/data/adonet/connection-string-builders.md)</span></span>\
<span data-ttu-id="9ad9c-131">Демонстрирует использование классов `ConnectionStringBuilder` для создания достоверных строк соединения во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="9ad9c-131">Demonstrates how to use the `ConnectionStringBuilder` classes to construct valid connection strings at run time.</span></span>

<span data-ttu-id="9ad9c-132">[Строки подключения и файлы конфигурации](../../../../docs/framework/data/adonet/connection-strings-and-configuration-files.md)</span><span class="sxs-lookup"><span data-stu-id="9ad9c-132">[Connection Strings and Configuration Files](../../../../docs/framework/data/adonet/connection-strings-and-configuration-files.md)</span></span>\
<span data-ttu-id="9ad9c-133">Демонстрирует хранение и получение строк соединения в файлах конфигурации.</span><span class="sxs-lookup"><span data-stu-id="9ad9c-133">Demonstrates how to store and retrieve connection strings in configuration files.</span></span>

<span data-ttu-id="9ad9c-134">[Синтаксис строки подключения](../../../../docs/framework/data/adonet/connection-string-syntax.md)</span><span class="sxs-lookup"><span data-stu-id="9ad9c-134">[Connection String Syntax](../../../../docs/framework/data/adonet/connection-string-syntax.md)</span></span>\
<span data-ttu-id="9ad9c-135">Описывает настройку строк соединения, зависящих от поставщика, для `SqlClient`, `OracleClient`, `OleDb` и `Odbc`.</span><span class="sxs-lookup"><span data-stu-id="9ad9c-135">Describes how to configure provider-specific connection strings for `SqlClient`, `OracleClient`, `OleDb`, and `Odbc`.</span></span>

<span data-ttu-id="9ad9c-136">[Защита сведений о соединении](../../../../docs/framework/data/adonet/protecting-connection-information.md)</span><span class="sxs-lookup"><span data-stu-id="9ad9c-136">[Protecting Connection Information](../../../../docs/framework/data/adonet/protecting-connection-information.md)</span></span>\
<span data-ttu-id="9ad9c-137">Демонстрирует методы защиты сведений, используемых для подключения к источнику данных.</span><span class="sxs-lookup"><span data-stu-id="9ad9c-137">Demonstrates techniques for protecting information used to connect to a data source.</span></span>

## <a name="see-also"></a><span data-ttu-id="9ad9c-138">См. также</span><span class="sxs-lookup"><span data-stu-id="9ad9c-138">See also</span></span>

- [<span data-ttu-id="9ad9c-139">Подключение к источнику данных</span><span class="sxs-lookup"><span data-stu-id="9ad9c-139">Connecting to a Data Source</span></span>](/cpp/data/odbc/connecting-to-a-data-source)
- [<span data-ttu-id="9ad9c-140">Центр разработчиков наборов данных и управляемых поставщиков ADO.NET</span><span class="sxs-lookup"><span data-stu-id="9ad9c-140">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
