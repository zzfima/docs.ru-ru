---
title: Методы System.String
ms.date: 03/30/2017
ms.assetid: ce307f14-87e6-4816-8694-8a4147f6b784
ms.openlocfilehash: 583c0d58562c1605f24b61489d481e19248ebed4
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70792492"
---
# <a name="systemstring-methods"></a><span data-ttu-id="20e5e-102">Методы System.String</span><span class="sxs-lookup"><span data-stu-id="20e5e-102">System.String Methods</span></span>
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="20e5e-103">не поддерживает следующие методы <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="20e5e-103">does not support the following <xref:System.String> methods.</span></span>  
  
## <a name="unsupported-systemstring-methods-in-general"></a><span data-ttu-id="20e5e-104">Неподдерживаемые методы System.String в целом</span><span class="sxs-lookup"><span data-stu-id="20e5e-104">Unsupported System.String Methods in General</span></span>  
 <span data-ttu-id="20e5e-105">Далее представлены общие сведения о неподдерживаемых методах <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="20e5e-105">Unsupported <xref:System.String> methods in general:</span></span>  
  
- <span data-ttu-id="20e5e-106">Перегрузки с учетом языка и региональных параметров ( `CultureInfo`методы, принимающие  /   /  `StringComparison` `IFormatProvider`).</span><span class="sxs-lookup"><span data-stu-id="20e5e-106">Culture-aware overloads (methods that take a `CultureInfo` / `StringComparison` / `IFormatProvider`).</span></span>  
  
- <span data-ttu-id="20e5e-107">Методы, которые принимают или создают массивы значений типа `char`.</span><span class="sxs-lookup"><span data-stu-id="20e5e-107">Methods that take or produce a `char` array.</span></span>  
  
## <a name="unsupported-systemstring-static-methods"></a><span data-ttu-id="20e5e-108">Неподдерживаемые статические методы System.String</span><span class="sxs-lookup"><span data-stu-id="20e5e-108">Unsupported System.String Static Methods</span></span>  
  
|<span data-ttu-id="20e5e-109">Неподдерживаемые статические методы System.String</span><span class="sxs-lookup"><span data-stu-id="20e5e-109">Unsupported System.String Static Methods</span></span>|  
|----------------------------------------------|  
|<xref:System.String.Copy%28System.String%29?displayProperty=nameWithType>|  
|<xref:System.String.Compare%28System.String%2CSystem.String%2CSystem.Boolean%29?displayProperty=nameWithType>|  
|<xref:System.String.Compare%28System.String%2CSystem.String%2CSystem.Boolean%2CSystem.Globalization.CultureInfo%29?displayProperty=nameWithType>|  
|<xref:System.String.Compare%28System.String%2CSystem.Int32%2CSystem.String%2CSystem.Int32%2CSystem.Int32%29?displayProperty=nameWithType>|  
|<xref:System.String.Compare%28System.String%2CSystem.Int32%2CSystem.String%2CSystem.Int32%2CSystem.Int32%2CSystem.Boolean%29?displayProperty=nameWithType>|  
|<xref:System.String.Compare%28System.String%2CSystem.Int32%2CSystem.String%2CSystem.Int32%2CSystem.Int32%2CSystem.Boolean%2CSystem.Globalization.CultureInfo%29?displayProperty=nameWithType>|  
|<xref:System.String.CompareOrdinal%28System.String%2CSystem.String%29?displayProperty=nameWithType>|  
|<xref:System.String.CompareOrdinal%28System.String%2CSystem.Int32%2CSystem.String%2CSystem.Int32%2CSystem.Int32%29?displayProperty=nameWithType>|  
|<xref:System.String.Format%2A?displayProperty=nameWithType>|  
|<xref:System.String.Join%2A?displayProperty=nameWithType>|  
  
## <a name="unsupported-systemstring-non-static-methods"></a><span data-ttu-id="20e5e-110">Неподдерживаемые методы System.String, не являющиеся статическими</span><span class="sxs-lookup"><span data-stu-id="20e5e-110">Unsupported System.String Non-static Methods</span></span>  
  
|<span data-ttu-id="20e5e-111">Неподдерживаемые методы System.String, не являющиеся статическими</span><span class="sxs-lookup"><span data-stu-id="20e5e-111">Unsupported System.String Non-static Methods</span></span>|  
|---------------------------------------------------|  
|<xref:System.String.IndexOfAny%28System.Char%5B%5D%29?displayProperty=nameWithType>|  
|<xref:System.String.Split%2A?displayProperty=nameWithType>|  
|<xref:System.String.ToCharArray?displayProperty=nameWithType>|  
|<xref:System.String.ToUpper%28System.Globalization.CultureInfo%29?displayProperty=nameWithType>|  
|<xref:System.String.TrimEnd%28System.Char%5B%5D%29?displayProperty=nameWithType>|  
|<xref:System.String.TrimStart%28System.Char%5B%5D%29?displayProperty=nameWithType>|  
  
## <a name="differences-from-net"></a><span data-ttu-id="20e5e-112">Отличия от платформы .NET</span><span class="sxs-lookup"><span data-stu-id="20e5e-112">Differences from .NET</span></span>  
  
- <span data-ttu-id="20e5e-113">Запросы не учитывают параметры сортировки SQL Server, которые могут применяться на сервере, и поэтому по умолчанию выполняют сравнения, зависящие от языка и региональных параметров и не зависящие от регистра.</span><span class="sxs-lookup"><span data-stu-id="20e5e-113">Queries do not account for SQL Server collations that might be in effect on the server, and therefore will provide culture-sensitive, case-insensitive comparisons by default.</span></span> <span data-ttu-id="20e5e-114">Это поведение отличается от семантики платформы .NET Framework, по умолчанию учитывающей регистр.</span><span class="sxs-lookup"><span data-stu-id="20e5e-114">This behavior differs from the default, case-sensitive semantics of the .NET Framework.</span></span>  
  
- <span data-ttu-id="20e5e-115">Если `LastIndexOf` функция возвращает значение 0, то либо `NULL` строка имеет значение, либо найденная позицией имеет значение 0.</span><span class="sxs-lookup"><span data-stu-id="20e5e-115">When `LastIndexOf` returns 0, either the string is `NULL` or the found position is 0.</span></span>  
  
- <span data-ttu-id="20e5e-116">При объединении строк фиксированной длины (`CHAR`, `NCHAR`) или выполнении других операций над этими строками могут возвращаться непредвиденные результаты, поскольку к этим типам применяется автоматическое заполнение в базе данных.</span><span class="sxs-lookup"><span data-stu-id="20e5e-116">Unexpected results might be returned from concatenation or other operations on fixed-length strings (`CHAR`, `NCHAR`), because these types automatically have padding applied in the database.</span></span>  
  
- <span data-ttu-id="20e5e-117">Для многих методов, таких как `Replace`, `ToLower`, `ToUpper` и индексатор знаков, не предусмотрено допустимого предобразования столбцов или кода XML типа `TEXT` или `NTEXT`, поэтому при их преобразовании, как правило, вызываются исключения `SqlExceptions`.</span><span class="sxs-lookup"><span data-stu-id="20e5e-117">Because many methods, such as `Replace`, `ToLower`, `ToUpper`, and the character indexer, have no valid translation for `TEXT` or `NTEXT` columns and XML, `SqlExceptions` occur if translated normally.</span></span> <span data-ttu-id="20e5e-118">Это поведения считается допустимым для этих типов.</span><span class="sxs-lookup"><span data-stu-id="20e5e-118">This behavior is considered acceptable for these types.</span></span> <span data-ttu-id="20e5e-119">Однако все операции над строками должны соответствовать семантике среды CLR для типов `VARCHAR`, `NVARCHAR`, `VARCHAR(max)` и `NVARCHAR(max)`.</span><span class="sxs-lookup"><span data-stu-id="20e5e-119">However, all string operations must match common language runtime (CLR) semantics for `VARCHAR`, `NVARCHAR`, `VARCHAR(max)`, and `NVARCHAR(max)`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20e5e-120">См. также</span><span class="sxs-lookup"><span data-stu-id="20e5e-120">See also</span></span>

- [<span data-ttu-id="20e5e-121">Типы данных и функции</span><span class="sxs-lookup"><span data-stu-id="20e5e-121">Data Types and Functions</span></span>](data-types-and-functions.md)
