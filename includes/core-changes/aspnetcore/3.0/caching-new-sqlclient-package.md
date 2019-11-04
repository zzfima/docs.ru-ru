---
ms.openlocfilehash: 771238c53dc97f4cf4068968f3c68500ba9f87da
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2019
ms.locfileid: "73198551"
---
### <a name="caching-microsoftextensionscachingsqlserver-uses-new-sqlclient-package"></a><span data-ttu-id="1409a-101">Кэширование. Microsoft.Extensions.Caching.SqlServer использует новый пакет SqlClient</span><span class="sxs-lookup"><span data-stu-id="1409a-101">Caching: Microsoft.Extensions.Caching.SqlServer uses new SqlClient package</span></span>

<span data-ttu-id="1409a-102">Пакет `Microsoft.Extensions.Caching.SqlServer` будет использовать новый пакет `Microsoft.Data.SqlClient` вместо пакета `System.Data.SqlClient`.</span><span class="sxs-lookup"><span data-stu-id="1409a-102">The `Microsoft.Extensions.Caching.SqlServer` package will use the new `Microsoft.Data.SqlClient` package instead of `System.Data.SqlClient` package.</span></span> <span data-ttu-id="1409a-103">Это изменение может привести к незначительным критическим изменениям в поведении.</span><span class="sxs-lookup"><span data-stu-id="1409a-103">This change could cause slight behavioral breaking changes.</span></span> <span data-ttu-id="1409a-104">См. [обзор Microsoft.Data.SqlClient](https://devblogs.microsoft.com/dotnet/introducing-the-new-microsoftdatasqlclient/).</span><span class="sxs-lookup"><span data-stu-id="1409a-104">For more information, see [Introducing the new Microsoft.Data.SqlClient](https://devblogs.microsoft.com/dotnet/introducing-the-new-microsoftdatasqlclient/).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="1409a-105">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="1409a-105">Version introduced</span></span>

<span data-ttu-id="1409a-106">3.0</span><span class="sxs-lookup"><span data-stu-id="1409a-106">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="1409a-107">Старое поведение</span><span class="sxs-lookup"><span data-stu-id="1409a-107">Old behavior</span></span>

<span data-ttu-id="1409a-108">Пакет `Microsoft.Extensions.Caching.SqlServer` использовал пакет `System.Data.SqlClient`.</span><span class="sxs-lookup"><span data-stu-id="1409a-108">The `Microsoft.Extensions.Caching.SqlServer` package used the `System.Data.SqlClient` package.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="1409a-109">Новое поведение</span><span class="sxs-lookup"><span data-stu-id="1409a-109">New behavior</span></span>

<span data-ttu-id="1409a-110">`Microsoft.Extensions.Caching.SqlServer` теперь использует пакет `Microsoft.Data.SqlClient`.</span><span class="sxs-lookup"><span data-stu-id="1409a-110">`Microsoft.Extensions.Caching.SqlServer` is now using the `Microsoft.Data.SqlClient` package.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="1409a-111">Причина изменения</span><span class="sxs-lookup"><span data-stu-id="1409a-111">Reason for change</span></span>

<span data-ttu-id="1409a-112">`Microsoft.Data.SqlClient` — это новый пакет, созданный на основе `System.Data.SqlClient`.</span><span class="sxs-lookup"><span data-stu-id="1409a-112">`Microsoft.Data.SqlClient` is a new package that is built off of `System.Data.SqlClient`.</span></span> <span data-ttu-id="1409a-113">С этого момента в нем будут поддерживаться все новые функции.</span><span class="sxs-lookup"><span data-stu-id="1409a-113">It's where all new feature work will be done from now on.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="1409a-114">Рекомендуемое действие</span><span class="sxs-lookup"><span data-stu-id="1409a-114">Recommended action</span></span>

<span data-ttu-id="1409a-115">Клиентам не нужно беспокоиться об этом критическом изменении, если только они не использовали типы, возвращаемые пакетом `Microsoft.Extensions.Caching.SqlServer` и приводимые к типам `System.Data.SqlClient`.</span><span class="sxs-lookup"><span data-stu-id="1409a-115">Customers shouldn't need to worry about this breaking change unless they were using types returned by the `Microsoft.Extensions.Caching.SqlServer` package and casting them to `System.Data.SqlClient` types.</span></span> <span data-ttu-id="1409a-116">Например, при приведении `DbConnection` к [старому типу SqlConnection](xref:System.Data.SqlClient.SqlConnection), нужно будет изменить приведение на новый тип `Microsoft.Data.SqlClient.SqlConnection`.</span><span class="sxs-lookup"><span data-stu-id="1409a-116">For example, if someone was casting a `DbConnection` to the [old SqlConnection type](xref:System.Data.SqlClient.SqlConnection), they would need to change the cast to the new `Microsoft.Data.SqlClient.SqlConnection` type.</span></span>

#### <a name="category"></a><span data-ttu-id="1409a-117">Категория</span><span class="sxs-lookup"><span data-stu-id="1409a-117">Category</span></span>

<span data-ttu-id="1409a-118">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="1409a-118">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="1409a-119">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="1409a-119">Affected APIs</span></span>

<span data-ttu-id="1409a-120">Нет</span><span class="sxs-lookup"><span data-stu-id="1409a-120">None</span></span>

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
