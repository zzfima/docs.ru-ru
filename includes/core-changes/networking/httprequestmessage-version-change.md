---
ms.openlocfilehash: ff156afb3da4b921517fd841c5de2295265a8d7b
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2019
ms.locfileid: "73198539"
---
### <a name="default-value-of-httprequestmessageversion-changed-to-11"></a><span data-ttu-id="35ebf-101">Значение по умолчанию HttpRequestMessage.Version изменено на 1.1</span><span class="sxs-lookup"><span data-stu-id="35ebf-101">Default value of HttpRequestMessage.Version changed to 1.1</span></span>

<span data-ttu-id="35ebf-102">Значение свойства <xref:System.Net.Http.HttpRequestMessage.Version?displayProperty=fullName> по умолчанию изменено с 2.0 на 1.1.</span><span class="sxs-lookup"><span data-stu-id="35ebf-102">The default value of the <xref:System.Net.Http.HttpRequestMessage.Version?displayProperty=fullName> property has changed from 2.0 to 1.1.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="35ebf-103">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="35ebf-103">Version introduced</span></span>

<span data-ttu-id="35ebf-104">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="35ebf-104">.NET Core 3.0</span></span>

#### <a name="change-description"></a><span data-ttu-id="35ebf-105">Описание изменений</span><span class="sxs-lookup"><span data-stu-id="35ebf-105">Change description</span></span>

<span data-ttu-id="35ebf-106">В .NET Core с 1.0 по 2.0 значением свойства <xref:System.Net.Http.HttpRequestMessage.Version?displayProperty=fullName> по умолчанию является 1.1.</span><span class="sxs-lookup"><span data-stu-id="35ebf-106">In .NET Core 1.0 through 2.0, the default value of the <xref:System.Net.Http.HttpRequestMessage.Version?displayProperty=fullName> property is 1.1.</span></span> <span data-ttu-id="35ebf-107">Начиная с .NET Core 2.1 оно было изменено на 2.1.</span><span class="sxs-lookup"><span data-stu-id="35ebf-107">Starting with .NET Core 2.1, it was changed to 2.1.</span></span>

<span data-ttu-id="35ebf-108">Начиная с .NET Core 3.0 номер версии по умолчанию, возвращаемый свойством <xref:System.Net.Http.HttpRequestMessage.Version?displayProperty=fullName>, снова стал 1.1.</span><span class="sxs-lookup"><span data-stu-id="35ebf-108">Starting with .NET Core 3.0, the default version number returned by the <xref:System.Net.Http.HttpRequestMessage.Version?displayProperty=fullName> property is once again 1.1.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="35ebf-109">Рекомендуемое действие</span><span class="sxs-lookup"><span data-stu-id="35ebf-109">Recommended action</span></span>

<span data-ttu-id="35ebf-110">Обновите код, если он зависит от свойства <xref:System.Net.Http.HttpRequestMessage.Version?displayProperty=fullName>, возвращающего значение по умолчанию 2.0.</span><span class="sxs-lookup"><span data-stu-id="35ebf-110">Update your code if it depends on the <xref:System.Net.Http.HttpRequestMessage.Version?displayProperty=fullName> property returning a default value of 2.0.</span></span>

#### <a name="category"></a><span data-ttu-id="35ebf-111">Категория</span><span class="sxs-lookup"><span data-stu-id="35ebf-111">Category</span></span>

<span data-ttu-id="35ebf-112">Сети</span><span class="sxs-lookup"><span data-stu-id="35ebf-112">Networking</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="35ebf-113">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="35ebf-113">Affected APIs</span></span>

- <xref:System.Net.Http.HttpRequestMessage.Version?displayProperty=fullName>

<!--
a def
### Affected APIs

- `P:System.Net.Http.HttpRequestMessage.Version`

-- >

