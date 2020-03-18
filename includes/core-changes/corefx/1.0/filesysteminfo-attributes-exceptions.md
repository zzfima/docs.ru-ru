---
ms.openlocfilehash: 4091bdcf7d9ed8872aed5faa6e6d3ed143903787
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "77449413"
---
### <a name="unauthorizedaccessexception-thrown-by-filesysteminfoattributes"></a><span data-ttu-id="ba8a5-101">Исключение UnauthorizedAccessException, вызванное FileSystemInfo.Attributes</span><span class="sxs-lookup"><span data-stu-id="ba8a5-101">UnauthorizedAccessException thrown by FileSystemInfo.Attributes</span></span>

<span data-ttu-id="ba8a5-102">В .NET Core <xref:System.UnauthorizedAccessException> возникает, когда вызывающий пытается задать значение атрибута файла, но у него нет разрешений на запись.</span><span class="sxs-lookup"><span data-stu-id="ba8a5-102">In .NET Core, an <xref:System.UnauthorizedAccessException> is thrown when the caller attempts to set a file attribute value but doesn't have write permission.</span></span>

#### <a name="change-description"></a><span data-ttu-id="ba8a5-103">Описание изменений</span><span class="sxs-lookup"><span data-stu-id="ba8a5-103">Change description</span></span>

<span data-ttu-id="ba8a5-104">В .NET Framework <xref:System.ArgumentException> возникает, когда вызывающий пытается задать значение атрибута файла в <xref:System.IO.FileSystemInfo.Attributes?displayProperty=nameWithType>, но у него нет разрешений на запись.</span><span class="sxs-lookup"><span data-stu-id="ba8a5-104">In .NET Framework, an <xref:System.ArgumentException> is thrown when the caller attempts to set a file attribute value in <xref:System.IO.FileSystemInfo.Attributes?displayProperty=nameWithType> but doesn't have write permission.</span></span> <span data-ttu-id="ba8a5-105">В .NET Core вместо него возникает <xref:System.UnauthorizedAccessException></span><span class="sxs-lookup"><span data-stu-id="ba8a5-105">In .NET Core, an <xref:System.UnauthorizedAccessException> is thrown instead.</span></span> <span data-ttu-id="ba8a5-106">(в .NET Core <xref:System.ArgumentException> по-прежнему возникает, если вызывающий пытается задать недопустимый атрибут файла).</span><span class="sxs-lookup"><span data-stu-id="ba8a5-106">(In .NET Core, an <xref:System.ArgumentException> is still thrown if the caller attempts to set an invalid file attribute.)</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="ba8a5-107">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="ba8a5-107">Version introduced</span></span>

<span data-ttu-id="ba8a5-108">1,0</span><span class="sxs-lookup"><span data-stu-id="ba8a5-108">1.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="ba8a5-109">Рекомендованное действие</span><span class="sxs-lookup"><span data-stu-id="ba8a5-109">Recommended action</span></span>

<span data-ttu-id="ba8a5-110">Изменяйте любые инструкции `catch`, чтобы получить <xref:System.UnauthorizedAccessException> вместо или в дополнение к <xref:System.ArgumentException> по мере необходимости.</span><span class="sxs-lookup"><span data-stu-id="ba8a5-110">Modify any `catch` statements to catch an <xref:System.UnauthorizedAccessException> instead of, or in addition to, an <xref:System.ArgumentException>, as necessary.</span></span>

#### <a name="category"></a><span data-ttu-id="ba8a5-111">Категория</span><span class="sxs-lookup"><span data-stu-id="ba8a5-111">Category</span></span>

<span data-ttu-id="ba8a5-112">CoreFX</span><span class="sxs-lookup"><span data-stu-id="ba8a5-112">CoreFx</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="ba8a5-113">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="ba8a5-113">Affected APIs</span></span>

- <xref:System.IO.FileSystemInfo.Attributes?displayProperty=nameWithType>

<!--

#### Affected APIs

- `P:System.IO.FileSystemInfo.Attributes`

-->
