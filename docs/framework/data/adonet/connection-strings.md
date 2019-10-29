---
title: Строки подключения в ADO.NET
ms.date: 10/10/2018
ms.assetid: 745c5f95-2f02-4674-b378-6d51a7ec2490
ms.openlocfilehash: bf053c7c26435bea5b2368c81c89b73e8949b74a
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2019
ms.locfileid: "73040135"
---
# <a name="connection-strings-in-adonet"></a><span data-ttu-id="a8ae0-102">Строки подключения в ADO.NET</span><span class="sxs-lookup"><span data-stu-id="a8ae0-102">Connection Strings in ADO.NET</span></span>

<span data-ttu-id="a8ae0-103">Строка подключения содержит сведения для инициализации, передаваемые в виде параметра от поставщика данных в источник данных.</span><span class="sxs-lookup"><span data-stu-id="a8ae0-103">A connection string contains initialization information that is passed as a parameter from a data provider to a data source.</span></span> <span data-ttu-id="a8ae0-104">Поставщик данных получает строку подключения в качестве значения свойства <xref:System.Data.Common.DbConnection.ConnectionString?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="a8ae0-104">The data provider receives the connection string as the value of the <xref:System.Data.Common.DbConnection.ConnectionString?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="a8ae0-105">Поставщик анализирует строку подключения и проверяет правильность синтаксиса и наличие ключевых слов.</span><span class="sxs-lookup"><span data-stu-id="a8ae0-105">The provider parses the connection string and ensures that the syntax is correct and that the keywords are supported.</span></span> <span data-ttu-id="a8ae0-106">Затем метод <xref:System.Data.Common.DbConnection.Open?displayProperty=nameWithType> передает проанализированные параметры соединения в источник данных.</span><span class="sxs-lookup"><span data-stu-id="a8ae0-106">Then the <xref:System.Data.Common.DbConnection.Open?displayProperty=nameWithType> method passes the parsed connection parameters to the data source.</span></span> <span data-ttu-id="a8ae0-107">Источник данных выполняет дальнейшую проверку и устанавливает соединение.</span><span class="sxs-lookup"><span data-stu-id="a8ae0-107">The data source performs further validation and establishes a connection.</span></span>

## <a name="connection-string-syntax"></a><span data-ttu-id="a8ae0-108">Синтаксис строки подключения</span><span class="sxs-lookup"><span data-stu-id="a8ae0-108">Connection string syntax</span></span>

<span data-ttu-id="a8ae0-109">Строка подключения представляет собой разделенный точками с запятой список пар параметров "ключ-значение":</span><span class="sxs-lookup"><span data-stu-id="a8ae0-109">A connection string is a semicolon-delimited list of key/value parameter pairs:</span></span>

```csharp
keyword1=value; keyword2=value;
```

<span data-ttu-id="a8ae0-110">В ключевых словах регистр не учитывается.</span><span class="sxs-lookup"><span data-stu-id="a8ae0-110">Keywords are not case-sensitive.</span></span> <span data-ttu-id="a8ae0-111">При этом значения в зависимости от источника данных могут быть чувствительны к регистру.</span><span class="sxs-lookup"><span data-stu-id="a8ae0-111">Values, however, may be case-sensitive, depending on the data source.</span></span> <span data-ttu-id="a8ae0-112">Ключевые слова и значения могут содержать [символы пробела](https://en.wikipedia.org/wiki/Whitespace_character#Unicode).</span><span class="sxs-lookup"><span data-stu-id="a8ae0-112">Both keywords and values may contain [whitespace characters](https://en.wikipedia.org/wiki/Whitespace_character#Unicode).</span></span> <span data-ttu-id="a8ae0-113">Начальные и конечные пробелы игнорируются в ключевых словах и в значениях, не заключенных в кавычки.</span><span class="sxs-lookup"><span data-stu-id="a8ae0-113">Leading and trailing white space is ignored in keywords and unquoted values.</span></span>

<span data-ttu-id="a8ae0-114">Если значение содержит точку с запятой, [управляющие символы Юникода](https://en.wikipedia.org/wiki/Unicode_control_characters)или начальные или конечные пробелы, их необходимо заключить в одинарные или двойные кавычки.</span><span class="sxs-lookup"><span data-stu-id="a8ae0-114">If a value contains the semicolon, [Unicode control characters](https://en.wikipedia.org/wiki/Unicode_control_characters), or leading or trailing white space, it must be enclosed in single or double quotation marks.</span></span> <span data-ttu-id="a8ae0-115">Пример:</span><span class="sxs-lookup"><span data-stu-id="a8ae0-115">For example:</span></span>

```csharp
Keyword=" whitespace  ";
Keyword='special;character';
```

<span data-ttu-id="a8ae0-116">Окружающий символ может не находиться в заключенном в нем значении.</span><span class="sxs-lookup"><span data-stu-id="a8ae0-116">The enclosing character may not occur within the value it encloses.</span></span> <span data-ttu-id="a8ae0-117">Таким образом, значение, содержащее одинарные кавычки, может быть заключено только в двойные кавычки и наоборот:</span><span class="sxs-lookup"><span data-stu-id="a8ae0-117">Therefore, a value containing single quotation marks can be enclosed only in double quotation marks, and vice versa:</span></span>

```csharp
Keyword='double"quotation;mark';
Keyword="single'quotation;mark";
```

<span data-ttu-id="a8ae0-118">Можно также поэкранировать окружающий символ, используя два из них:</span><span class="sxs-lookup"><span data-stu-id="a8ae0-118">You can also escape the enclosing character by using two of them together:</span></span>

```csharp
Keyword="double""quotation";
Keyword='single''quotation';
```

<span data-ttu-id="a8ae0-119">Кавычки, а также знак равенства не требуются для экранирования, поэтому следующие строки соединения являются допустимыми:</span><span class="sxs-lookup"><span data-stu-id="a8ae0-119">The quotation marks themselves, as well as the equals sign, do not require escaping, so the following connection strings are valid:</span></span>

```csharp
Keyword=no "escaping" 'required';
Keyword=a=b=c
```

<span data-ttu-id="a8ae0-120">Так как каждое значение считывается до следующей точки с запятой или конца строки, значение в последнем примере — `a=b=c`, а конечная точка с запятой является необязательной.</span><span class="sxs-lookup"><span data-stu-id="a8ae0-120">Since each value is read till the next semicolon or the end of string, the value in the latter example is `a=b=c`, and the final semicolon is optional.</span></span>

<span data-ttu-id="a8ae0-121">Все строки подключения имеют один и тот же базовый синтаксис, описанный выше.</span><span class="sxs-lookup"><span data-stu-id="a8ae0-121">All connection strings share the same basic syntax described above.</span></span> <span data-ttu-id="a8ae0-122">Набор распознаваемых ключевых слов зависит от поставщика, но в течение многих лет он превратился в предыдущие API-интерфейсы, такие как *ODBC*.</span><span class="sxs-lookup"><span data-stu-id="a8ae0-122">The set of recognized keywords depends on the provider, however, and has evolved over the years from earlier APIs such as *ODBC*.</span></span> <span data-ttu-id="a8ae0-123">Поставщик данных *.NET Framework* для *SQL Server* (`SqlClient`) поддерживает много ключевых слов из старых API-интерфейсов, но обычно является более гибким и принимает синонимы для многих общих ключевых слов строки подключения.</span><span class="sxs-lookup"><span data-stu-id="a8ae0-123">The *.NET Framework* data provider for *SQL Server* (`SqlClient`) supports many keywords from older APIs, but is generally more flexible and accepts synonyms for many of the common connection string keywords.</span></span>

<span data-ttu-id="a8ae0-124">При вводе ошибок могут возникать ошибки.</span><span class="sxs-lookup"><span data-stu-id="a8ae0-124">Typing mistakes can cause errors.</span></span> <span data-ttu-id="a8ae0-125">Например, `Integrated Security=true` является допустимым, но `IntegratedSecurity=true` вызывает ошибку.</span><span class="sxs-lookup"><span data-stu-id="a8ae0-125">For example, `Integrated Security=true` is valid, but `IntegratedSecurity=true` causes an error.</span></span>

<span data-ttu-id="a8ae0-126">Строки подключения, созданные вручную во время выполнения из непроверенных входных данных, уязвимы для атак путем внедрения строк и поддают риску безопасность в источнике данных.</span><span class="sxs-lookup"><span data-stu-id="a8ae0-126">Connection strings constructed manually at run time from unvalidated user input are vulnerable to string-injection attacks and jeopardize security at the data source.</span></span> <span data-ttu-id="a8ae0-127">Для решения этих проблем в *ADO.NET* 2,0 появились [построители строк подключения](connection-string-builders.md) для каждого *.NET Framework* поставщика данных.</span><span class="sxs-lookup"><span data-stu-id="a8ae0-127">To address these problems, *ADO.NET* 2.0 introduced [connection string builders](connection-string-builders.md) for each *.NET Framework* data provider.</span></span> <span data-ttu-id="a8ae0-128">Эти построители строк подключения предоставляют параметры в виде строго типизированных свойств и позволяют проверить строку подключения перед отправкой в источник данных.</span><span class="sxs-lookup"><span data-stu-id="a8ae0-128">These connection string builders expose parameters as strongly-typed properties, and make it possible to validate the connection string before it's sent to the data source.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="a8ae0-129">Содержание</span><span class="sxs-lookup"><span data-stu-id="a8ae0-129">In This Section</span></span>

<span data-ttu-id="a8ae0-130">[Построители строк подключения](connection-string-builders.md)</span><span class="sxs-lookup"><span data-stu-id="a8ae0-130">[Connection String Builders](connection-string-builders.md)</span></span>\
<span data-ttu-id="a8ae0-131">Демонстрирует использование классов `ConnectionStringBuilder` для создания достоверных строк соединения во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="a8ae0-131">Demonstrates how to use the `ConnectionStringBuilder` classes to construct valid connection strings at run time.</span></span>

<span data-ttu-id="a8ae0-132">[Строки подключения и файлы конфигурации](connection-strings-and-configuration-files.md)</span><span class="sxs-lookup"><span data-stu-id="a8ae0-132">[Connection Strings and Configuration Files](connection-strings-and-configuration-files.md)</span></span>\
<span data-ttu-id="a8ae0-133">Демонстрирует хранение и получение строк соединения в файлах конфигурации.</span><span class="sxs-lookup"><span data-stu-id="a8ae0-133">Demonstrates how to store and retrieve connection strings in configuration files.</span></span>

<span data-ttu-id="a8ae0-134">[Синтаксис строки подключения](connection-string-syntax.md)</span><span class="sxs-lookup"><span data-stu-id="a8ae0-134">[Connection String Syntax](connection-string-syntax.md)</span></span>\
<span data-ttu-id="a8ae0-135">Описывает настройку строк соединения, зависящих от поставщика, для `SqlClient`, `OracleClient`, `OleDb` и `Odbc`.</span><span class="sxs-lookup"><span data-stu-id="a8ae0-135">Describes how to configure provider-specific connection strings for `SqlClient`, `OracleClient`, `OleDb`, and `Odbc`.</span></span>

<span data-ttu-id="a8ae0-136">[Защита сведений о соединении](protecting-connection-information.md)</span><span class="sxs-lookup"><span data-stu-id="a8ae0-136">[Protecting Connection Information](protecting-connection-information.md)</span></span>\
<span data-ttu-id="a8ae0-137">Демонстрирует методы защиты сведений, используемых для подключения к источнику данных.</span><span class="sxs-lookup"><span data-stu-id="a8ae0-137">Demonstrates techniques for protecting information used to connect to a data source.</span></span>

## <a name="see-also"></a><span data-ttu-id="a8ae0-138">См. также</span><span class="sxs-lookup"><span data-stu-id="a8ae0-138">See also</span></span>

- [<span data-ttu-id="a8ae0-139">Подключение к источнику данных</span><span class="sxs-lookup"><span data-stu-id="a8ae0-139">Connecting to a Data Source</span></span>](/cpp/data/odbc/connecting-to-a-data-source)
- [<span data-ttu-id="a8ae0-140">Общие сведения об ADO.NET</span><span class="sxs-lookup"><span data-stu-id="a8ae0-140">ADO.NET Overview</span></span>](ado-net-overview.md)
