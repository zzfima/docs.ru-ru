---
title: "Компиляция проекта, использующего взаимодействие"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- interoperation with unmanaged code, compiling
- COM interop, compiling
- exposing COM components to .NET Framework
- compiling interop projects
- interoperation with unmanaged code, exposing COM components
- COM interop, exposing COM components
ms.assetid: 6fcf6588-5e25-41af-b4ae-780974f2c3df
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 8115df3159b715fbd01a15621c391cbe35612dfe
ms.sourcegitcommit: d95a91d685565f4d95c8773b558752864a6a3d7e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2018
---
# <a name="compiling-an-interop-project"></a><span data-ttu-id="4329d-102">Компиляция проекта, использующего взаимодействие</span><span class="sxs-lookup"><span data-stu-id="4329d-102">Compiling an Interop Project</span></span>
<span data-ttu-id="4329d-103">Проекты, использующие COM-взаимодействие, в которых содержатся ссылки на одну или несколько сборок с импортированными типами COM, компилируются так же, как и любые другие управляемые проекты.</span><span class="sxs-lookup"><span data-stu-id="4329d-103">COM interop projects that reference one or more assemblies containing imported COM types are compiled like any other managed project.</span></span> <span data-ttu-id="4329d-104">Ссылки на сборки взаимодействия можно использовать как в среде разработки (например, Visual Studio), так при использовании компилятора командной строки.</span><span class="sxs-lookup"><span data-stu-id="4329d-104">You can reference interop assemblies in a development environment such as Visual Studio, or you can reference them when you use a command-line compiler.</span></span> <span data-ttu-id="4329d-105">В обоих случаях для корректной компиляции сборка взаимодействия должна находиться в одном каталоге с другими файлами проекта.</span><span class="sxs-lookup"><span data-stu-id="4329d-105">In either case, to compile properly, the interop assembly must be in the same directory as the other project files.</span></span>  
  
 <span data-ttu-id="4329d-106">Ссылки на сборки взаимодействия можно использовать двумя способами:</span><span class="sxs-lookup"><span data-stu-id="4329d-106">There are two ways to reference interop assemblies:</span></span>  
  
-   <span data-ttu-id="4329d-107">С помощью встроенных типов взаимодействия. Начиная с версий [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] и [!INCLUDE[vs_dev10_long](../../../includes/vs-dev10-long-md.md)], можно дать указание компилятору внедрять сведения о типах из сборки взаимодействия в исполняемый файл.</span><span class="sxs-lookup"><span data-stu-id="4329d-107">Embedded interop types: Beginning with the [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] and [!INCLUDE[vs_dev10_long](../../../includes/vs-dev10-long-md.md)], you can instruct the compiler to embed type information from an interop assembly into your executable.</span></span> <span data-ttu-id="4329d-108">Это рекомендуемая методика.</span><span class="sxs-lookup"><span data-stu-id="4329d-108">This is the recommended technique.</span></span>  
  
-   <span data-ttu-id="4329d-109">Развертывание сборок взаимодействия. Можно создать стандартную ссылку на сборку взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="4329d-109">Deploying interop assemblies: You can create a standard reference to an interop assembly.</span></span> <span data-ttu-id="4329d-110">В этом случае сборки взаимодействия должны быть развернуты вместе с приложением.</span><span class="sxs-lookup"><span data-stu-id="4329d-110">In this case, the interop assembly must be deployed with your application.</span></span>  
  
 <span data-ttu-id="4329d-111">Различия между этими двумя способами более подробно описываются в разделе [Использование COM-типов в управляемом коде](https://msdn.microsoft.com/library/1a95a8ca-c8b8-4464-90b0-5ee1a1135b66(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="4329d-111">The differences between these two techniques are discussed in greater detail in [Using COM Types in Managed Code](https://msdn.microsoft.com/library/1a95a8ca-c8b8-4464-90b0-5ee1a1135b66(v=vs.100)).</span></span>  
  
 <span data-ttu-id="4329d-112">Внедрение типов взаимодействия в Visual Studio демонстрируется в разделах [Пошаговое руководство. Внедрение данных о типе из сборок для приложений Microsoft Office](http://msdn.microsoft.com/library/85b55e05-bc5e-4665-b6ae-e1ada9299fd3) и [Пошаговое руководство. Внедрение данных о типах из управляемых сборок](http://msdn.microsoft.com/library/b28ec92c-1867-4847-95c0-61adfe095e21).</span><span class="sxs-lookup"><span data-stu-id="4329d-112">Embedding interop types with Visual Studio is demonstrated in [Walkthrough: Embedding Type Information from Microsoft Office Assemblies](http://msdn.microsoft.com/library/85b55e05-bc5e-4665-b6ae-e1ada9299fd3) and [Walkthrough: Embedding Types from Managed Assemblies](http://msdn.microsoft.com/library/b28ec92c-1867-4847-95c0-61adfe095e21).</span></span>  
  
 <span data-ttu-id="4329d-113">Чтобы задать ссылку на сборку взаимодействия в компиляторе командной строки и внедрить сведения о типах в исполняемые файлы, задайте параметр компилятора [/link (параметры компилятора C#)](~/docs/csharp/language-reference/compiler-options/link-compiler-option.md) или [/link (Visual Basic)](~/docs/visual-basic/reference/command-line-compiler/link.md) и укажите имя сборки взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="4329d-113">To reference an interop assembly with a command-line compiler and embed type information in your executables, use the [/link (C# Compiler Options)](~/docs/csharp/language-reference/compiler-options/link-compiler-option.md) or the [/link (Visual Basic)](~/docs/visual-basic/reference/command-line-compiler/link.md) compiler switch and specify the name of the interop assembly.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4329d-114">Приложения Visual C++ не поддерживают внедрение сведений о типах, однако могут взаимодействовать с приложениями и надстройками, в которых такая возможность присутствует.</span><span class="sxs-lookup"><span data-stu-id="4329d-114">Visual C++ applications cannot embed type information, but they can interoperate with applications or add-ins that do.</span></span>  
  
 <span data-ttu-id="4329d-115">Чтобы скомпилировать приложение, которое включает основную сборку взаимодействия при развертывании, задайте параметр компилятора **/reference** и укажите имя сборки взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="4329d-115">To compile an application that includes a primary interop assembly when it is deployed, use the **/reference** compiler switch and specify the name of the interop assembly.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4329d-116">См. также</span><span class="sxs-lookup"><span data-stu-id="4329d-116">See Also</span></span>  
 [<span data-ttu-id="4329d-117">Предоставление COM-компонентов платформе .NET Framework</span><span class="sxs-lookup"><span data-stu-id="4329d-117">Exposing COM Components to the .NET Framework</span></span>](../../../docs/framework/interop/exposing-com-components.md)  
 [<span data-ttu-id="4329d-118">Независимость от языка и независимые от языка компоненты</span><span class="sxs-lookup"><span data-stu-id="4329d-118">Language Independence and Language-Independent Components</span></span>](../../../docs/standard/language-independence-and-language-independent-components.md)  
 <span data-ttu-id="4329d-119">[Использование типов COM в управляемом коде](https://msdn.microsoft.com/library/1a95a8ca-c8b8-4464-90b0-5ee1a1135b66(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="4329d-119">[Using COM Types in Managed Code](https://msdn.microsoft.com/library/1a95a8ca-c8b8-4464-90b0-5ee1a1135b66(v=vs.100))</span></span>  
 [<span data-ttu-id="4329d-120">Пошаговое руководство. Внедрение данных о типе из сборок для приложений Microsoft Office</span><span class="sxs-lookup"><span data-stu-id="4329d-120">Walkthrough: Embedding Type Information from Microsoft Office Assemblies</span></span>](http://msdn.microsoft.com/library/85b55e05-bc5e-4665-b6ae-e1ada9299fd3)  
 [<span data-ttu-id="4329d-121">Пошаговое руководство. Внедрение данных о типах из управляемых сборок</span><span class="sxs-lookup"><span data-stu-id="4329d-121">Walkthrough: Embedding Types from Managed Assemblies</span></span>](http://msdn.microsoft.com/library/b28ec92c-1867-4847-95c0-61adfe095e21)  
 [<span data-ttu-id="4329d-122">Импорт библиотеки типов в виде сборки</span><span class="sxs-lookup"><span data-stu-id="4329d-122">Importing a Type Library as an Assembly</span></span>](../../../docs/framework/interop/importing-a-type-library-as-an-assembly.md)
