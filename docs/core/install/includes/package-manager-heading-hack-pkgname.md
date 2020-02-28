---
ms.openlocfilehash: 51b3c1b3e3d61b23a0511ca807afef0269ac9ee4
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "77466072"
---

<span data-ttu-id="5f06c-101">Пакеты, добавляемые в веб-каналы диспетчера пакетов, именуются в формате, который можно взломать: `{product}-{type}-{version}`.</span><span class="sxs-lookup"><span data-stu-id="5f06c-101">The packages added to the package manager feeds are named in a hackable format: `{product}-{type}-{version}`.</span></span>

- <span data-ttu-id="5f06c-102">**product**</span><span class="sxs-lookup"><span data-stu-id="5f06c-102">**product**</span></span>\
<span data-ttu-id="5f06c-103">Тип устанавливаемого продукта .NET.</span><span class="sxs-lookup"><span data-stu-id="5f06c-103">The type of .NET product to install.</span></span> <span data-ttu-id="5f06c-104">Допустимые параметры:</span><span class="sxs-lookup"><span data-stu-id="5f06c-104">Valid options are:</span></span>

  - <span data-ttu-id="5f06c-105">dotnet</span><span class="sxs-lookup"><span data-stu-id="5f06c-105">dotnet</span></span>
  - <span data-ttu-id="5f06c-106">aspnetcore</span><span class="sxs-lookup"><span data-stu-id="5f06c-106">aspnetcore</span></span>

- <span data-ttu-id="5f06c-107">**type**</span><span class="sxs-lookup"><span data-stu-id="5f06c-107">**type**</span></span>\
<span data-ttu-id="5f06c-108">Позволяет выбрать пакет SDK или среду выполнения.</span><span class="sxs-lookup"><span data-stu-id="5f06c-108">Chooses the SDK or the runtime.</span></span> <span data-ttu-id="5f06c-109">Допустимые параметры:</span><span class="sxs-lookup"><span data-stu-id="5f06c-109">Valid options are:</span></span>

  - <span data-ttu-id="5f06c-110">sdk</span><span class="sxs-lookup"><span data-stu-id="5f06c-110">sdk</span></span>
  - <span data-ttu-id="5f06c-111">исполняющая среда</span><span class="sxs-lookup"><span data-stu-id="5f06c-111">runtime</span></span>

- <span data-ttu-id="5f06c-112">**version**</span><span class="sxs-lookup"><span data-stu-id="5f06c-112">**version**</span></span>\
<span data-ttu-id="5f06c-113">Версия пакета SDK или среды выполнения для установки.</span><span class="sxs-lookup"><span data-stu-id="5f06c-113">The version of the SDK or runtime to install.</span></span> <span data-ttu-id="5f06c-114">Эта статья всегда будет содержать инструкции для последней поддерживаемой версии.</span><span class="sxs-lookup"><span data-stu-id="5f06c-114">This article will always give the instructions for the latest supported version.</span></span> <span data-ttu-id="5f06c-115">Допустимые параметры — любая выпущенная версия, например:</span><span class="sxs-lookup"><span data-stu-id="5f06c-115">Valid options are any released version, such as:</span></span>

  - <span data-ttu-id="5f06c-116">3.1</span><span class="sxs-lookup"><span data-stu-id="5f06c-116">3.1</span></span>
  - <span data-ttu-id="5f06c-117">3.0</span><span class="sxs-lookup"><span data-stu-id="5f06c-117">3.0</span></span>
  - <span data-ttu-id="5f06c-118">2.1</span><span class="sxs-lookup"><span data-stu-id="5f06c-118">2.1</span></span>

  <span data-ttu-id="5f06c-119">Возможно, пакет SDK или среда выполнения, которые вы пытаетесь скачать, недоступны для вашего дистрибутива Linux.</span><span class="sxs-lookup"><span data-stu-id="5f06c-119">It's possible the SDK/runtime you're trying to download is not available for your Linux distribution.</span></span> <span data-ttu-id="5f06c-120">Список поддерживаемых дистрибутивов см. в статье [Зависимости и требования для .NET Core](../dependencies.md?pivots=os-linux).</span><span class="sxs-lookup"><span data-stu-id="5f06c-120">For a list of supported distributions, see [.NET Core dependencies and requirements](../dependencies.md?pivots=os-linux).</span></span>

### <a name="examples"></a><span data-ttu-id="5f06c-121">Примеры</span><span class="sxs-lookup"><span data-stu-id="5f06c-121">Examples</span></span>

- <span data-ttu-id="5f06c-122">Установка среды выполнения ASP.NET Core 3.1: `aspnetcore-runtime-3.1`</span><span class="sxs-lookup"><span data-stu-id="5f06c-122">Install the ASP.NET Core 3.1 runtime: `aspnetcore-runtime-3.1`</span></span>
- <span data-ttu-id="5f06c-123">Установка среды выполнения .NET Core 2.1: `dotnet-runtime-2.1`</span><span class="sxs-lookup"><span data-stu-id="5f06c-123">Install the .NET Core 2.1 runtime: `dotnet-runtime-2.1`</span></span>
- <span data-ttu-id="5f06c-124">Установка пакета SDK для .NET Core 3.0: `dotnet-sdk-3.0`</span><span class="sxs-lookup"><span data-stu-id="5f06c-124">Install the .NET Core 3.0 SDK: `dotnet-sdk-3.0`</span></span>

### <a name="package-missing"></a><span data-ttu-id="5f06c-125">Пакет отсутствует</span><span class="sxs-lookup"><span data-stu-id="5f06c-125">Package missing</span></span>

<span data-ttu-id="5f06c-126">Если сочетание пакета и версии больше не поддерживается, оно недоступно.</span><span class="sxs-lookup"><span data-stu-id="5f06c-126">If the package-version combination doesn't work, it's not available.</span></span> <span data-ttu-id="5f06c-127">Например, пакет SDK для ASP.NET Core отсутствует, компоненты этого пакета SDK входят в состав пакета SDK для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="5f06c-127">For example, there isn't an ASP.NET Core SDK, the SDK components are included with the .NET Core SDK.</span></span> <span data-ttu-id="5f06c-128">Значение `aspnetcore-sdk-2.2` неправильное и должно быть равно `dotnet-sdk-2.2`</span><span class="sxs-lookup"><span data-stu-id="5f06c-128">The value `aspnetcore-sdk-2.2` is incorrect and should be `dotnet-sdk-2.2`.</span></span> <span data-ttu-id="5f06c-129">Список дистрибутивов Linux, поддерживаемых .NET Core, см. в статье [Зависимости и требования для .NET Core](../dependencies.md?pivots=os-linux).</span><span class="sxs-lookup"><span data-stu-id="5f06c-129">For a list of Linux distributions supported by .NET Core, see [.NET Core dependencies and requirements](../dependencies.md?pivots=os-linux).</span></span>
