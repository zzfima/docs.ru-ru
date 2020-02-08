---
ms.openlocfilehash: ef3e4f9f8145677732b9d2e66d416be277697f55
ms.sourcegitcommit: cdf5084648bf5e77970cbfeaa23f1cab3e6e234e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/01/2020
ms.locfileid: "76920636"
---

<span data-ttu-id="edda0-101">Пакеты, добавляемые в веб-каналы диспетчера пакетов, именуются в формате, который можно взломать: `{product}-{type}-{version}`.</span><span class="sxs-lookup"><span data-stu-id="edda0-101">The packages added to the package manager feeds are named in a hackable format: `{product}-{type}-{version}`.</span></span>

- <span data-ttu-id="edda0-102">**product**</span><span class="sxs-lookup"><span data-stu-id="edda0-102">**product**</span></span>\
<span data-ttu-id="edda0-103">Тип устанавливаемого продукта .NET.</span><span class="sxs-lookup"><span data-stu-id="edda0-103">The type of .NET product to install.</span></span> <span data-ttu-id="edda0-104">Допустимые параметры:</span><span class="sxs-lookup"><span data-stu-id="edda0-104">Valid options are:</span></span>

  - <span data-ttu-id="edda0-105">dotnet</span><span class="sxs-lookup"><span data-stu-id="edda0-105">dotnet</span></span>
  - <span data-ttu-id="edda0-106">aspnetcore</span><span class="sxs-lookup"><span data-stu-id="edda0-106">aspnetcore</span></span>

- <span data-ttu-id="edda0-107">**type**</span><span class="sxs-lookup"><span data-stu-id="edda0-107">**type**</span></span>\
<span data-ttu-id="edda0-108">Позволяет выбрать пакет SDK или среду выполнения.</span><span class="sxs-lookup"><span data-stu-id="edda0-108">Chooses the SDK or the runtime.</span></span> <span data-ttu-id="edda0-109">Допустимые параметры:</span><span class="sxs-lookup"><span data-stu-id="edda0-109">Valid options are:</span></span>

  - <span data-ttu-id="edda0-110">sdk</span><span class="sxs-lookup"><span data-stu-id="edda0-110">sdk</span></span>
  - <span data-ttu-id="edda0-111">исполняющая среда</span><span class="sxs-lookup"><span data-stu-id="edda0-111">runtime</span></span>

- <span data-ttu-id="edda0-112">**version**</span><span class="sxs-lookup"><span data-stu-id="edda0-112">**version**</span></span>\
<span data-ttu-id="edda0-113">Версия пакета SDK или среды выполнения для установки.</span><span class="sxs-lookup"><span data-stu-id="edda0-113">The version of the SDK or runtime to install.</span></span> <span data-ttu-id="edda0-114">Эта статья всегда будет содержать инструкции для последней поддерживаемой версии.</span><span class="sxs-lookup"><span data-stu-id="edda0-114">This article will always give the instructions for the latest supported version.</span></span> <span data-ttu-id="edda0-115">Допустимые параметры — любая выпущенная версия, например:</span><span class="sxs-lookup"><span data-stu-id="edda0-115">Valid options are any released version, such as:</span></span>

  - <span data-ttu-id="edda0-116">3.0</span><span class="sxs-lookup"><span data-stu-id="edda0-116">3.0</span></span>
  - <span data-ttu-id="edda0-117">2.2</span><span class="sxs-lookup"><span data-stu-id="edda0-117">2.2</span></span>
  - <span data-ttu-id="edda0-118">2.1</span><span class="sxs-lookup"><span data-stu-id="edda0-118">2.1</span></span>

### <a name="examples"></a><span data-ttu-id="edda0-119">Примеры</span><span class="sxs-lookup"><span data-stu-id="edda0-119">Examples</span></span>

- <span data-ttu-id="edda0-120">Установка пакета SDK для .NET Core 2.2: `dotnet-sdk-2.2`</span><span class="sxs-lookup"><span data-stu-id="edda0-120">Install the .NET Core 2.2 SDK: `dotnet-sdk-2.2`</span></span>
- <span data-ttu-id="edda0-121">Установка среды выполнения ASP.NET Core 3.1: `aspnetcore-runtime-3.1`</span><span class="sxs-lookup"><span data-stu-id="edda0-121">Install the ASP.NET Core 3.1 runtime: `aspnetcore-runtime-3.1`</span></span>
- <span data-ttu-id="edda0-122">Установка среды выполнения .NET Core 2.1: `dotnet-runtime-2.1`</span><span class="sxs-lookup"><span data-stu-id="edda0-122">Install the .NET Core 2.1 runtime: `dotnet-runtime-2.1`</span></span>

### <a name="package-missing"></a><span data-ttu-id="edda0-123">Пакет отсутствует</span><span class="sxs-lookup"><span data-stu-id="edda0-123">Package missing</span></span>

<span data-ttu-id="edda0-124">Если сочетание пакета и версии больше не поддерживается, оно недоступно.</span><span class="sxs-lookup"><span data-stu-id="edda0-124">If the package-version combination doesn't work, it's not available.</span></span> <span data-ttu-id="edda0-125">Например, пакет SDK для ASP.NET Core отсутствует, компоненты этого пакета SDK входят в состав пакета SDK для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="edda0-125">For example, there isn't an ASP.NET Core SDK, the SDK components are included with the .NET Core SDK.</span></span> <span data-ttu-id="edda0-126">Значение `aspnetcore-sdk-2.2` неправильное и должно быть равно `dotnet-sdk-2.2`</span><span class="sxs-lookup"><span data-stu-id="edda0-126">The value `aspnetcore-sdk-2.2` is incorrect and should be `dotnet-sdk-2.2`.</span></span>
