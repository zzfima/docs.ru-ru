---
title: Ограничения Xamarin
ms.date: 12/13/2019
description: Описание некоторых ограничений, которые будут возникать при использовании Xamarin.
ms.openlocfilehash: 192f25954726919dc66d706e755e0853404b4d85
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450408"
---
# <a name="xamarin-limitations"></a><span data-ttu-id="fd99e-103">Ограничения Xamarin</span><span class="sxs-lookup"><span data-stu-id="fd99e-103">Xamarin limitations</span></span>

<span data-ttu-id="fd99e-104">Microsoft. Data. SQLite предназначен для .NET Standard 2,0 и поддерживается в Xamarin.</span><span class="sxs-lookup"><span data-stu-id="fd99e-104">Microsoft.Data.Sqlite targets .NET Standard 2.0 and is supported on Xamarin.</span></span> <span data-ttu-id="fd99e-105">В следующей таблице показано, на каких платформах пакет Склитепклрав по умолчанию предоставляет собственные двоичные файлы SQLite для.</span><span class="sxs-lookup"><span data-stu-id="fd99e-105">The following table shows which platforms the default SQLitePCLRaw bundle provides native SQLite binaries for.</span></span> <span data-ttu-id="fd99e-106">Дополнительные сведения об использовании разных наборов или предоставлении собственных двоичных файлов SQLite см. в разделе [пользовательские версии SQLite](custom-versions.md) .</span><span class="sxs-lookup"><span data-stu-id="fd99e-106">See [Custom SQLite versions](custom-versions.md) for details on using a different bundle or providing your own native SQLite binaries.</span></span>

| <span data-ttu-id="fd99e-107">Platform</span><span class="sxs-lookup"><span data-stu-id="fd99e-107">Platform</span></span> | <span data-ttu-id="fd99e-108">Двоичные файлы SQLite</span><span class="sxs-lookup"><span data-stu-id="fd99e-108">SQLite binaries</span></span> |
| --- | --- |
| <span data-ttu-id="fd99e-109">**Xamarin.Android**</span><span class="sxs-lookup"><span data-stu-id="fd99e-109">**Xamarin.Android**</span></span> | <span data-ttu-id="fd99e-110">—</span><span class="sxs-lookup"><span data-stu-id="fd99e-110">—</span></span> |
| &nbsp;&nbsp;&nbsp;&nbsp;`arm64-v8a` | <span data-ttu-id="fd99e-111">✔</span><span class="sxs-lookup"><span data-stu-id="fd99e-111">✔</span></span> |
| &nbsp;&nbsp;&nbsp;&nbsp;`armeabi-v7a` | <span data-ttu-id="fd99e-112">✔</span><span class="sxs-lookup"><span data-stu-id="fd99e-112">✔</span></span> |
| &nbsp;&nbsp;&nbsp;&nbsp;`x86` | <span data-ttu-id="fd99e-113">✔</span><span class="sxs-lookup"><span data-stu-id="fd99e-113">✔</span></span> |
| &nbsp;&nbsp;&nbsp;&nbsp;`x86_64` | <span data-ttu-id="fd99e-114">✔</span><span class="sxs-lookup"><span data-stu-id="fd99e-114">✔</span></span> |
| <span data-ttu-id="fd99e-115">**Xamarin.iOS**</span><span class="sxs-lookup"><span data-stu-id="fd99e-115">**Xamarin.iOS**</span></span> | <span data-ttu-id="fd99e-116">✔</span><span class="sxs-lookup"><span data-stu-id="fd99e-116">✔</span></span> |
| <span data-ttu-id="fd99e-117">**Xamarin.Mac**</span><span class="sxs-lookup"><span data-stu-id="fd99e-117">**Xamarin.Mac**</span></span> | <span data-ttu-id="fd99e-118">✔</span><span class="sxs-lookup"><span data-stu-id="fd99e-118">✔</span></span> |
| <span data-ttu-id="fd99e-119">**Xamarin. TVOS**</span><span class="sxs-lookup"><span data-stu-id="fd99e-119">**Xamarin.TVOS**</span></span> | <span data-ttu-id="fd99e-120">✔</span><span class="sxs-lookup"><span data-stu-id="fd99e-120">✔</span></span> |
| <span data-ttu-id="fd99e-121">**UWP**</span><span class="sxs-lookup"><span data-stu-id="fd99e-121">**UWP**</span></span> | <span data-ttu-id="fd99e-122">—</span><span class="sxs-lookup"><span data-stu-id="fd99e-122">—</span></span> |
| &nbsp;&nbsp;&nbsp;&nbsp;`arm` | <span data-ttu-id="fd99e-123">✔</span><span class="sxs-lookup"><span data-stu-id="fd99e-123">✔</span></span> |
| &nbsp;&nbsp;&nbsp;&nbsp;`arm64` | <span data-ttu-id="fd99e-124">✔</span><span class="sxs-lookup"><span data-stu-id="fd99e-124">✔</span></span> |
| &nbsp;&nbsp;&nbsp;&nbsp;`x64` | <span data-ttu-id="fd99e-125">✔</span><span class="sxs-lookup"><span data-stu-id="fd99e-125">✔</span></span> |
| &nbsp;&nbsp;&nbsp;&nbsp;`x86` | <span data-ttu-id="fd99e-126">✔</span><span class="sxs-lookup"><span data-stu-id="fd99e-126">✔</span></span> |

## <a name="ios"></a><span data-ttu-id="fd99e-127">iOS</span><span class="sxs-lookup"><span data-stu-id="fd99e-127">iOS</span></span>

<span data-ttu-id="fd99e-128">Microsoft. Data. SQLite пытается автоматически инициализировать пакеты Склитепклрав.</span><span class="sxs-lookup"><span data-stu-id="fd99e-128">Microsoft.Data.Sqlite tries to automatically initialize SQLitePCLRaw bundles.</span></span> <span data-ttu-id="fd99e-129">К сожалению, из-за ограничений для компиляции Xamarin. iOS на момент времени (AOT) попытка завершается неудачей и появляется следующая ошибка.</span><span class="sxs-lookup"><span data-stu-id="fd99e-129">Unfortunately, because of limitations in the ahead-of-time (AOT) compilation for Xamarin.iOS, the attempt fails and you get the following error.</span></span>

> <span data-ttu-id="fd99e-130">Необходимо вызвать `SQLitePCL.raw.SetProvider()`.</span><span class="sxs-lookup"><span data-stu-id="fd99e-130">You need to call `SQLitePCL.raw.SetProvider()`.</span></span> <span data-ttu-id="fd99e-131">Если вы используете пакет пакета, это делается путем вызова `SQLitePCL.Batteries.Init()`.</span><span class="sxs-lookup"><span data-stu-id="fd99e-131">If you're using a bundle package, this is done by calling `SQLitePCL.Batteries.Init()`.</span></span>

<span data-ttu-id="fd99e-132">Чтобы инициализировать пакет, добавьте следующую строку кода в приложение перед использованием Microsoft. Data. SQLite.</span><span class="sxs-lookup"><span data-stu-id="fd99e-132">To initialize the bundle, add the following line of code to your app before using Microsoft.Data.Sqlite.</span></span>

```csharp
SQLitePCL.Batteries_V2.Init();
```

## <a name="see-also"></a><span data-ttu-id="fd99e-133">См. также:</span><span class="sxs-lookup"><span data-stu-id="fd99e-133">See also</span></span>

* [<span data-ttu-id="fd99e-134">Ограничения Async</span><span class="sxs-lookup"><span data-stu-id="fd99e-134">Async limitations</span></span>](async.md)
* [<span data-ttu-id="fd99e-135">Пользовательские версии SQLite</span><span class="sxs-lookup"><span data-stu-id="fd99e-135">Custom SQLite versions</span></span>](custom-versions.md)
