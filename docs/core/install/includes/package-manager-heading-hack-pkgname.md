---
ms.openlocfilehash: 7a55641b3673dc4d8d9b328f0de99b7247ca51d4
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74998801"
---

<span data-ttu-id="f10b0-101">Пакеты, добавляемые в веб-каналы диспетчера пакетов, именуются в формате, который можно взломать: `{product}-{type}-{version}`.</span><span class="sxs-lookup"><span data-stu-id="f10b0-101">The packages added to the package manager feeds are named in a hackable format: `{product}-{type}-{version}`.</span></span>

- <span data-ttu-id="f10b0-102">**product**</span><span class="sxs-lookup"><span data-stu-id="f10b0-102">**product**</span></span>\
<span data-ttu-id="f10b0-103">Тип устанавливаемого продукта .NET.</span><span class="sxs-lookup"><span data-stu-id="f10b0-103">The type of .NET product to install.</span></span> <span data-ttu-id="f10b0-104">Допустимые параметры:</span><span class="sxs-lookup"><span data-stu-id="f10b0-104">Valid options are:</span></span>

  - <span data-ttu-id="f10b0-105">dotnet</span><span class="sxs-lookup"><span data-stu-id="f10b0-105">dotnet</span></span>
  - <span data-ttu-id="f10b0-106">aspnetcore</span><span class="sxs-lookup"><span data-stu-id="f10b0-106">aspnetcore</span></span>

- <span data-ttu-id="f10b0-107">**type**</span><span class="sxs-lookup"><span data-stu-id="f10b0-107">**type**</span></span>\
<span data-ttu-id="f10b0-108">Позволяет выбрать пакет SDK или среду выполнения.</span><span class="sxs-lookup"><span data-stu-id="f10b0-108">Chooses the SDK or the runtime.</span></span> <span data-ttu-id="f10b0-109">Допустимые параметры:</span><span class="sxs-lookup"><span data-stu-id="f10b0-109">Valid options are:</span></span>

  - <span data-ttu-id="f10b0-110">sdk</span><span class="sxs-lookup"><span data-stu-id="f10b0-110">sdk</span></span>
  - <span data-ttu-id="f10b0-111">исполняющая среда</span><span class="sxs-lookup"><span data-stu-id="f10b0-111">runtime</span></span>

- <span data-ttu-id="f10b0-112">**version**</span><span class="sxs-lookup"><span data-stu-id="f10b0-112">**version**</span></span>\
<span data-ttu-id="f10b0-113">Версия пакета SDK или среды выполнения для установки.</span><span class="sxs-lookup"><span data-stu-id="f10b0-113">The version of the SDK or runtime to install.</span></span> <span data-ttu-id="f10b0-114">Эта статья всегда будет содержать инструкции для последней поддерживаемой версии.</span><span class="sxs-lookup"><span data-stu-id="f10b0-114">This article will always give the instructions for the latest supported version.</span></span> <span data-ttu-id="f10b0-115">Допустимые параметры — любая выпущенная версия, например:</span><span class="sxs-lookup"><span data-stu-id="f10b0-115">Valid options are any released version, such as:</span></span>

  - <span data-ttu-id="f10b0-116">3.0</span><span class="sxs-lookup"><span data-stu-id="f10b0-116">3.0</span></span>
  - <span data-ttu-id="f10b0-117">2.2</span><span class="sxs-lookup"><span data-stu-id="f10b0-117">2.2</span></span>
  - <span data-ttu-id="f10b0-118">2.1</span><span class="sxs-lookup"><span data-stu-id="f10b0-118">2.1</span></span>

### <a name="examples"></a><span data-ttu-id="f10b0-119">Примеры</span><span class="sxs-lookup"><span data-stu-id="f10b0-119">Examples</span></span>

- <span data-ttu-id="f10b0-120">Установка пакета SDK для .NET Core 2.2: `dotnet-sdk-2.2`</span><span class="sxs-lookup"><span data-stu-id="f10b0-120">Install the .NET Core 2.2 SDK: `dotnet-sdk-2.2`</span></span>
- <span data-ttu-id="f10b0-121">Установка среды выполнения ASP.NET Core 3.0: `aspnetcore-runtime-3.0`</span><span class="sxs-lookup"><span data-stu-id="f10b0-121">Install the ASP.NET Core 3.0 runtime: `aspnetcore-runtime-3.0`</span></span>
- <span data-ttu-id="f10b0-122">Установка среды выполнения .NET Core 2.1: `dotnet-runtime-2.1`</span><span class="sxs-lookup"><span data-stu-id="f10b0-122">Install the .NET Core 2.1 runtime: `dotnet-runtime-2.1`</span></span>

### <a name="troubleshoot"></a><span data-ttu-id="f10b0-123">Устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="f10b0-123">Troubleshoot</span></span>

<span data-ttu-id="f10b0-124">Если сочетание пакетов не работает, оно недоступно.</span><span class="sxs-lookup"><span data-stu-id="f10b0-124">If the package combination doesn't work, it's not available.</span></span> <span data-ttu-id="f10b0-125">Например, пакет SDK для ASP.NET Core отсутствует, компоненты этого пакета SDK входят в состав пакета SDK для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="f10b0-125">For example, there isn't an ASP.NET Core SDK, the SDK components are included with the .NET Core SDK.</span></span> <span data-ttu-id="f10b0-126">Значение `aspnetcore-sdk-2.2` неправильное и должно быть равно `dotnet-sdk-2.2`</span><span class="sxs-lookup"><span data-stu-id="f10b0-126">The value `aspnetcore-sdk-2.2` is incorrect and should be `dotnet-sdk-2.2`</span></span>
