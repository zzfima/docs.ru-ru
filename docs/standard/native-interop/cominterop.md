---
title: Взаимодействие c COM в .NET
description: Узнайте, как взаимодействовать с библиотеками COM в .NET.
ms.date: 07/11/2019
ms.openlocfilehash: 4ea5c2330f8f90d676bfe7003a7307fc38822edf
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75706378"
---
# <a name="com-interop-in-net"></a><span data-ttu-id="54801-103">Взаимодействие c COM в .NET</span><span class="sxs-lookup"><span data-stu-id="54801-103">COM Interop in .NET</span></span>

<span data-ttu-id="54801-104">Объектная модель компонентов (модель COM) позволяет объекту предоставлять свою функциональность другим компонентам и ведущим приложениям на платформах Windows.</span><span class="sxs-lookup"><span data-stu-id="54801-104">The Component Object Model (COM) lets an object expose its functionality to other components and to host applications on Windows platforms.</span></span> <span data-ttu-id="54801-105">Чтобы обеспечить пользователям возможность взаимодействия с существующими базами кода, .NET Framework всегда предоставляет широкую поддержку для взаимодействия с библиотеками COM.</span><span class="sxs-lookup"><span data-stu-id="54801-105">To help enable users to interoperate with their existing code bases, the .NET Framework has always provided strong support for interoperating with COM libraries.</span></span> <span data-ttu-id="54801-106">В .NET Core 3.0 большая часть этой поддержки добавлена в .NET Core в Windows.</span><span class="sxs-lookup"><span data-stu-id="54801-106">In .NET Core 3.0, a large portion of this support has been added to .NET Core on Windows.</span></span> <span data-ttu-id="54801-107">В этой части документации объясняется, как работают технологии COM-взаимодействия и как можно использовать их для взаимодействия с существующими библиотеками COM.</span><span class="sxs-lookup"><span data-stu-id="54801-107">The documentation here will explain how the common COM interop techonologies work and how you can utilize them to interoperate with your existing COM libraries.</span></span>

- [<span data-ttu-id="54801-108">Oболочки COM</span><span class="sxs-lookup"><span data-stu-id="54801-108">COM Wrappers</span></span>](./com-wrappers.md)
- [<span data-ttu-id="54801-109">Вызываемые оболочки COM</span><span class="sxs-lookup"><span data-stu-id="54801-109">COM Callable Wrappers</span></span>](./com-callable-wrapper.md)
- [<span data-ttu-id="54801-110">Вызываемые оболочки времени выполнения</span><span class="sxs-lookup"><span data-stu-id="54801-110">Runtime Callable Wrappers</span></span>](./runtime-callable-wrapper.md)
- [<span data-ttu-id="54801-111">Уточнение типов .NET для COM-взаимодействия</span><span class="sxs-lookup"><span data-stu-id="54801-111">Qualifying .NET Types for COM Interoperation</span></span>](./qualify-net-types-for-interoperation.md)
