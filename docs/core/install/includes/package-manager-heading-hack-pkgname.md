---
ms.openlocfilehash: 47e8e15a64236d8ade2febb1add81fa4e5c030d9
ms.sourcegitcommit: ed3f926b6cdd372037bbcc214dc8f08a70366390
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/16/2020
ms.locfileid: "76116146"
---

<span data-ttu-id="0bab4-101">Пакеты, добавляемые в веб-каналы диспетчера пакетов, именуются в формате, который можно взломать: `{product}-{type}-{version}`.</span><span class="sxs-lookup"><span data-stu-id="0bab4-101">The packages added to the package manager feeds are named in a hackable format: `{product}-{type}-{version}`.</span></span>

- <span data-ttu-id="0bab4-102">**product**</span><span class="sxs-lookup"><span data-stu-id="0bab4-102">**product**</span></span>\
<span data-ttu-id="0bab4-103">Тип устанавливаемого продукта .NET.</span><span class="sxs-lookup"><span data-stu-id="0bab4-103">The type of .NET product to install.</span></span> <span data-ttu-id="0bab4-104">Допустимые параметры:</span><span class="sxs-lookup"><span data-stu-id="0bab4-104">Valid options are:</span></span>

  - <span data-ttu-id="0bab4-105">dotnet</span><span class="sxs-lookup"><span data-stu-id="0bab4-105">dotnet</span></span>
  - <span data-ttu-id="0bab4-106">aspnetcore</span><span class="sxs-lookup"><span data-stu-id="0bab4-106">aspnetcore</span></span>

- <span data-ttu-id="0bab4-107">**type**</span><span class="sxs-lookup"><span data-stu-id="0bab4-107">**type**</span></span>\
<span data-ttu-id="0bab4-108">Позволяет выбрать пакет SDK или среду выполнения.</span><span class="sxs-lookup"><span data-stu-id="0bab4-108">Chooses the SDK or the runtime.</span></span> <span data-ttu-id="0bab4-109">Допустимые параметры:</span><span class="sxs-lookup"><span data-stu-id="0bab4-109">Valid options are:</span></span>

  - <span data-ttu-id="0bab4-110">sdk</span><span class="sxs-lookup"><span data-stu-id="0bab4-110">sdk</span></span>
  - <span data-ttu-id="0bab4-111">исполняющая среда</span><span class="sxs-lookup"><span data-stu-id="0bab4-111">runtime</span></span>

- <span data-ttu-id="0bab4-112">**version**</span><span class="sxs-lookup"><span data-stu-id="0bab4-112">**version**</span></span>\
<span data-ttu-id="0bab4-113">Версия пакета SDK или среды выполнения для установки.</span><span class="sxs-lookup"><span data-stu-id="0bab4-113">The version of the SDK or runtime to install.</span></span> <span data-ttu-id="0bab4-114">Эта статья всегда будет содержать инструкции для последней поддерживаемой версии.</span><span class="sxs-lookup"><span data-stu-id="0bab4-114">This article will always give the instructions for the latest supported version.</span></span> <span data-ttu-id="0bab4-115">Допустимые параметры — любая выпущенная версия, например:</span><span class="sxs-lookup"><span data-stu-id="0bab4-115">Valid options are any released version, such as:</span></span>

  - <span data-ttu-id="0bab4-116">3.0</span><span class="sxs-lookup"><span data-stu-id="0bab4-116">3.0</span></span>
  - <span data-ttu-id="0bab4-117">2.2</span><span class="sxs-lookup"><span data-stu-id="0bab4-117">2.2</span></span>
  - <span data-ttu-id="0bab4-118">2.1</span><span class="sxs-lookup"><span data-stu-id="0bab4-118">2.1</span></span>

### <a name="examples"></a><span data-ttu-id="0bab4-119">Примеры</span><span class="sxs-lookup"><span data-stu-id="0bab4-119">Examples</span></span>

- <span data-ttu-id="0bab4-120">Установка пакета SDK для .NET Core 2.2: `dotnet-sdk-2.2`</span><span class="sxs-lookup"><span data-stu-id="0bab4-120">Install the .NET Core 2.2 SDK: `dotnet-sdk-2.2`</span></span>
- <span data-ttu-id="0bab4-121">Установка среды выполнения ASP.NET Core 3.1: `aspnetcore-runtime-3.1`</span><span class="sxs-lookup"><span data-stu-id="0bab4-121">Install the ASP.NET Core 3.1 runtime: `aspnetcore-runtime-3.1`</span></span>
- <span data-ttu-id="0bab4-122">Установка среды выполнения .NET Core 2.1: `dotnet-runtime-2.1`</span><span class="sxs-lookup"><span data-stu-id="0bab4-122">Install the .NET Core 2.1 runtime: `dotnet-runtime-2.1`</span></span>

### <a name="troubleshoot"></a><span data-ttu-id="0bab4-123">Устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="0bab4-123">Troubleshoot</span></span>

<span data-ttu-id="0bab4-124">Если сочетание пакетов не работает, оно недоступно.</span><span class="sxs-lookup"><span data-stu-id="0bab4-124">If the package combination doesn't work, it's not available.</span></span> <span data-ttu-id="0bab4-125">Например, пакет SDK для ASP.NET Core отсутствует, компоненты этого пакета SDK входят в состав пакета SDK для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="0bab4-125">For example, there isn't an ASP.NET Core SDK, the SDK components are included with the .NET Core SDK.</span></span> <span data-ttu-id="0bab4-126">Значение `aspnetcore-sdk-2.2` неправильное и должно быть равно `dotnet-sdk-2.2`</span><span class="sxs-lookup"><span data-stu-id="0bab4-126">The value `aspnetcore-sdk-2.2` is incorrect and should be `dotnet-sdk-2.2`</span></span>
