---
title: Сборки и параллельное выполнение
ms.date: 08/20/2019
helpviewer_keywords:
- side-by-side execution [.NET Framework]
- assemblies [.NET Framework], side-by-side execution
ms.assetid: e42036ee-7590-47d1-b884-cc856e39bd5d
ms.openlocfilehash: 234efba66d87b520b54d6d113afcc4bba0bfe06a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138664"
---
# <a name="assemblies-and-side-by-side-execution"></a><span data-ttu-id="17e7a-102">Сборки и параллельное выполнение</span><span class="sxs-lookup"><span data-stu-id="17e7a-102">Assemblies and side-by-side execution</span></span>

<span data-ttu-id="17e7a-103">Под параллельным выполнением понимается возможность сохранения и выполнения нескольких версий приложения или компонента на одном компьютере.</span><span class="sxs-lookup"><span data-stu-id="17e7a-103">Side-by-side execution is the ability to store and execute multiple versions of an application or component on the same computer.</span></span> <span data-ttu-id="17e7a-104">Это означает, что одновременно на одном и том же компьютере в одно и то же время можно иметь несколько версий среды выполнения и несколько версий приложений и компонентов, использующих среду выполнения данной версии.</span><span class="sxs-lookup"><span data-stu-id="17e7a-104">This means that you can have multiple versions of the runtime, and multiple versions of applications and components that use a version of the runtime, on the same computer at the same time.</span></span> <span data-ttu-id="17e7a-105">Параллельное выполнение предоставляет дополнительные возможности выбора версий компонента, с которым связано приложение, а также дополнительные возможности выбора используемой приложением версии среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="17e7a-105">Side-by-side execution gives you more control over what versions of a component an application binds to, and more control over what version of the runtime an application uses.</span></span>  
  
<span data-ttu-id="17e7a-106">Поддержка параллельного хранения и выполнения различных версий одной и той же сборки является неотъемлемой частью использования строгих имен. Эта поддержка встроена в инфраструктуру среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="17e7a-106">Support for side-by-side storage and execution of different versions of the same assembly is an integral part of strong naming and is built into the infrastructure of the runtime.</span></span> <span data-ttu-id="17e7a-107">Поскольку номер версии сборки со строгим именем является частью ее удостоверения, среда выполнения позволяет хранить несколько версий одной и той же сборки в глобальном кэше сборок и загружать эти сборки на этапе выполнения.</span><span class="sxs-lookup"><span data-stu-id="17e7a-107">Because the strong-named assembly's version number is part of its identity, the runtime can store multiple versions of the same assembly in the global assembly cache and load those assemblies at run time.</span></span>  
  
<span data-ttu-id="17e7a-108">Хотя среда выполнения предоставляет возможность создавать параллельные приложения, параллельное выполнение не реализуется автоматически.</span><span class="sxs-lookup"><span data-stu-id="17e7a-108">Although the runtime provides you with the ability to create side-by-side applications, side-by-side execution is not automatic.</span></span> <span data-ttu-id="17e7a-109">Дополнительные сведения о создании приложений для параллельного выполнения см. в разделе [Рекомендации по созданию компонентов для параллельного выполнения](../../framework/deployment/guidelines-for-creating-components-for-side-by-side-execution.md).</span><span class="sxs-lookup"><span data-stu-id="17e7a-109">For more information on creating applications for side-by-side execution, see [Guidelines for creating components for side-by-side execution](../../framework/deployment/guidelines-for-creating-components-for-side-by-side-execution.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17e7a-110">См. также</span><span class="sxs-lookup"><span data-stu-id="17e7a-110">See also</span></span>

- [<span data-ttu-id="17e7a-111">Обнаружение сборок в среде выполнения</span><span class="sxs-lookup"><span data-stu-id="17e7a-111">How the runtime locates assemblies</span></span>](../../framework/deployment/how-the-runtime-locates-assemblies.md)
- [<span data-ttu-id="17e7a-112">Сборки в .NET</span><span class="sxs-lookup"><span data-stu-id="17e7a-112">Assemblies in .NET</span></span>](index.md)
