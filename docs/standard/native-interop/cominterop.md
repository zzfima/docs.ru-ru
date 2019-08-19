---
title: Взаимодействие c COM в .NET
description: Узнайте, как взаимодействовать с библиотеками COM в .NET.
author: jkoritzinsky
ms.author: jekoritz
ms.date: 07/11/2019
ms.openlocfilehash: 9355e2ae84da623ffa725f5b2ac1bdee25b966d8
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/13/2019
ms.locfileid: "68971892"
---
# <a name="com-interop-in-net"></a><span data-ttu-id="35dd7-103">Взаимодействие c COM в .NET</span><span class="sxs-lookup"><span data-stu-id="35dd7-103">COM Interop in .NET</span></span>

<span data-ttu-id="35dd7-104">Объектная модель компонентов (модель COM) позволяет объекту предоставлять свою функциональность другим компонентам и ведущим приложениям на платформах Windows.</span><span class="sxs-lookup"><span data-stu-id="35dd7-104">The Component Object Model (COM) lets an object expose its functionality to other components and to host applications on Windows platforms.</span></span> <span data-ttu-id="35dd7-105">Чтобы обеспечить пользователям возможность взаимодействия с существующими базами кода, .NET Framework всегда предоставляет широкую поддержку для взаимодействия с библиотеками COM.</span><span class="sxs-lookup"><span data-stu-id="35dd7-105">To help enable users to interoperate with their existing code bases, the .NET Framework has always provided strong support for interoperating with COM libraries.</span></span> <span data-ttu-id="35dd7-106">В .NET Core 3.0 большая часть этой поддержки добавлена в .NET Core в Windows.</span><span class="sxs-lookup"><span data-stu-id="35dd7-106">In .NET Core 3.0, a large portion of this support has been added to .NET Core on Windows.</span></span> <span data-ttu-id="35dd7-107">В этой части документации объясняется, как работают технологии COM-взаимодействия и как можно использовать их для взаимодействия с существующими библиотеками COM.</span><span class="sxs-lookup"><span data-stu-id="35dd7-107">The documentation here will explain how the common COM interop techonologies work and how you can utilize them to interoperate with your existing COM libraries.</span></span>

- [<span data-ttu-id="35dd7-108">Oболочки COM</span><span class="sxs-lookup"><span data-stu-id="35dd7-108">COM Wrappers</span></span>](./com-wrappers.md)
- [<span data-ttu-id="35dd7-109">Вызываемые оболочки COM</span><span class="sxs-lookup"><span data-stu-id="35dd7-109">COM Callable Wrappers</span></span>](./com-callable-wrapper.md)
- [<span data-ttu-id="35dd7-110">Вызываемые оболочки времени выполнения</span><span class="sxs-lookup"><span data-stu-id="35dd7-110">Runtime Callable Wrappers</span></span>](./runtime-callable-wrapper.md)
- [<span data-ttu-id="35dd7-111">Уточнение типов .NET для COM-взаимодействия</span><span class="sxs-lookup"><span data-stu-id="35dd7-111">Qualifying .NET Types for COM Interoperation</span></span>](./qualify-net-types-for-interoperation.md)
