---
title: Collation
ms.date: 12/13/2019
description: Узнайте, как создать настраиваемую последовательность сортировки.
ms.openlocfilehash: 0942ad4523a149ad74321cbe0f63021f53303579
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450288"
---
# <a name="collation"></a><span data-ttu-id="eae61-103">Collation</span><span class="sxs-lookup"><span data-stu-id="eae61-103">Collation</span></span>

<span data-ttu-id="eae61-104">При сравнении текстовых значений с целью определения порядка и равенства в SQLite используются последовательности сортировки.</span><span class="sxs-lookup"><span data-stu-id="eae61-104">Collating sequences are used by SQLite when comparing TEXT values to determine order and equality.</span></span> <span data-ttu-id="eae61-105">Можно указать, какие параметры сортировки следует использовать при создании столбцов или по операциям в SQL-запросах.</span><span class="sxs-lookup"><span data-stu-id="eae61-105">You can specify which collation to use when creating columns or per-operation in SQL queries.</span></span> <span data-ttu-id="eae61-106">По умолчанию SQLite содержит три последовательности сортировки.</span><span class="sxs-lookup"><span data-stu-id="eae61-106">SQLite includes three collating sequences by default.</span></span>

| <span data-ttu-id="eae61-107">Collation</span><span class="sxs-lookup"><span data-stu-id="eae61-107">Collation</span></span> | <span data-ttu-id="eae61-108">Описание</span><span class="sxs-lookup"><span data-stu-id="eae61-108">Description</span></span>                               |
| --------- | ----------------------------------------- |
| <span data-ttu-id="eae61-109">RTRIM</span><span class="sxs-lookup"><span data-stu-id="eae61-109">RTRIM</span></span>     | <span data-ttu-id="eae61-110">Игнорирует конечные пробелы</span><span class="sxs-lookup"><span data-stu-id="eae61-110">Ignores trailing whitespace</span></span>               |
| <span data-ttu-id="eae61-111">CASE</span><span class="sxs-lookup"><span data-stu-id="eae61-111">NOCASE</span></span>    | <span data-ttu-id="eae61-112">Без учета регистра для символов ASCII A – Z</span><span class="sxs-lookup"><span data-stu-id="eae61-112">Case-insensitive for ASCII characters A-Z</span></span> |
| <span data-ttu-id="eae61-113">BINARY</span><span class="sxs-lookup"><span data-stu-id="eae61-113">BINARY</span></span>    | <span data-ttu-id="eae61-114">С учетом регистра.</span><span class="sxs-lookup"><span data-stu-id="eae61-114">Case-sensitive.</span></span> <span data-ttu-id="eae61-115">Сравнивает байты напрямую</span><span class="sxs-lookup"><span data-stu-id="eae61-115">Compares bytes directly</span></span>   |

## <a name="custom-collation"></a><span data-ttu-id="eae61-116">Пользовательские параметры сортировки</span><span class="sxs-lookup"><span data-stu-id="eae61-116">Custom collation</span></span>

<span data-ttu-id="eae61-117">Можно также определить собственные последовательности сортировки или переопределить встроенные, используя <xref:Microsoft.Data.Sqlite.SqliteConnection.CreateCollation%2A>.</span><span class="sxs-lookup"><span data-stu-id="eae61-117">You can also define your own collating sequences or override the built-in ones using <xref:Microsoft.Data.Sqlite.SqliteConnection.CreateCollation%2A>.</span></span> <span data-ttu-id="eae61-118">В следующем примере показано переопределение параметров сортировки в параметре CASE для поддержки символов Юникода.</span><span class="sxs-lookup"><span data-stu-id="eae61-118">The following example shows overriding the NOCASE collation to support Unicode characters.</span></span> <span data-ttu-id="eae61-119">[Полный пример кода](https://github.com/dotnet/samples/blob/master/samples/snippets/standard/data/sqlite/CollationSample/Program.cs) доступен на сайте GitHub.</span><span class="sxs-lookup"><span data-stu-id="eae61-119">The [full sample code](https://github.com/dotnet/samples/blob/master/samples/snippets/standard/data/sqlite/CollationSample/Program.cs) is available on GitHub.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/CollationSample/Program.cs?name=snippet_Collation)]

## <a name="like-operator"></a><span data-ttu-id="eae61-120">Like - оператор</span><span class="sxs-lookup"><span data-stu-id="eae61-120">Like operator</span></span>

<span data-ttu-id="eae61-121">Оператор LIKE в SQLite не учитывает параметры сортировки.</span><span class="sxs-lookup"><span data-stu-id="eae61-121">The LIKE operator in SQLite doesn't honor collations.</span></span> <span data-ttu-id="eae61-122">Реализация по умолчанию имеет ту же семантику, что и параметры сортировки в параметре CASE.</span><span class="sxs-lookup"><span data-stu-id="eae61-122">The default implementation has the same semantics as the NOCASE collation.</span></span> <span data-ttu-id="eae61-123">Символы ASCII от A до Z не учитывают регистр.</span><span class="sxs-lookup"><span data-stu-id="eae61-123">It's only case-insensitive for the ASCII characters A through Z.</span></span>

<span data-ttu-id="eae61-124">Можно легко сделать оператор LIKE с учетом регистра с помощью следующей инструкции pragma:</span><span class="sxs-lookup"><span data-stu-id="eae61-124">You can easily make the LIKE operator case-sensitive by using the following pragma statement:</span></span>

```sql
PRAGMA case_sensitive_like = 0
```

<span data-ttu-id="eae61-125">Дополнительные сведения о переопределении реализации оператора LIKE см. в разделе [определяемые пользователем функции](user-defined-functions.md) .</span><span class="sxs-lookup"><span data-stu-id="eae61-125">See [User-defined functions](user-defined-functions.md) for details on overriding the implementation of the LIKE operator.</span></span>

## <a name="see-also"></a><span data-ttu-id="eae61-126">См. также:</span><span class="sxs-lookup"><span data-stu-id="eae61-126">See also</span></span>

* [<span data-ttu-id="eae61-127">Определяемые пользователем функции</span><span class="sxs-lookup"><span data-stu-id="eae61-127">User-defined functions</span></span>](user-defined-functions.md)
* [<span data-ttu-id="eae61-128">Синтаксис SQL</span><span class="sxs-lookup"><span data-stu-id="eae61-128">SQL Syntax</span></span>](https://www.sqlite.org/lang.html)
