---
title: Компиляция проекта, использующего взаимодействие
ms.date: 03/30/2017
helpviewer_keywords:
- interoperation with unmanaged code, compiling
- COM interop, compiling
- exposing COM components to .NET Framework
- compiling interop projects
- interoperation with unmanaged code, exposing COM components
- COM interop, exposing COM components
ms.assetid: 6fcf6588-5e25-41af-b4ae-780974f2c3df
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5bc92eb9d4b7b0ae5db56303f3fbfa991c58e06a
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2019
ms.locfileid: "72523831"
---
# <a name="compiling-an-interop-project"></a><span data-ttu-id="be177-102">Компиляция проекта, использующего взаимодействие</span><span class="sxs-lookup"><span data-stu-id="be177-102">Compiling an Interop Project</span></span>

<span data-ttu-id="be177-103">Проекты, использующие COM-взаимодействие, в которых содержатся ссылки на одну или несколько сборок с импортированными типами COM, компилируются так же, как и любые другие управляемые проекты.</span><span class="sxs-lookup"><span data-stu-id="be177-103">COM interop projects that reference one or more assemblies containing imported COM types are compiled like any other managed project.</span></span> <span data-ttu-id="be177-104">Ссылки на сборки взаимодействия можно использовать как в среде разработки (например, Visual Studio), так при использовании компилятора командной строки.</span><span class="sxs-lookup"><span data-stu-id="be177-104">You can reference interop assemblies in a development environment such as Visual Studio, or you can reference them when you use a command-line compiler.</span></span> <span data-ttu-id="be177-105">В обоих случаях для корректной компиляции сборка взаимодействия должна находиться в одном каталоге с другими файлами проекта.</span><span class="sxs-lookup"><span data-stu-id="be177-105">In either case, to compile properly, the interop assembly must be in the same directory as the other project files.</span></span>

 <span data-ttu-id="be177-106">Ссылки на сборки взаимодействия можно использовать двумя способами:</span><span class="sxs-lookup"><span data-stu-id="be177-106">There are two ways to reference interop assemblies:</span></span>

- <span data-ttu-id="be177-107">Внедренные типы взаимодействия. Начиная с .NET Framework 4 и Visual Studio 2010, можно указать компилятору внедрять информацию о типах из сборки взаимодействия в исполняемый файл.</span><span class="sxs-lookup"><span data-stu-id="be177-107">Embedded interop types: Beginning with the .NET Framework 4 and Visual Studio 2010, you can instruct the compiler to embed type information from an interop assembly into your executable.</span></span> <span data-ttu-id="be177-108">Это рекомендуемая методика.</span><span class="sxs-lookup"><span data-stu-id="be177-108">This is the recommended technique.</span></span>

- <span data-ttu-id="be177-109">Развертывание сборок взаимодействия. Можно создать стандартную ссылку на сборку взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="be177-109">Deploying interop assemblies: You can create a standard reference to an interop assembly.</span></span> <span data-ttu-id="be177-110">В этом случае сборки взаимодействия должны быть развернуты вместе с приложением.</span><span class="sxs-lookup"><span data-stu-id="be177-110">In this case, the interop assembly must be deployed with your application.</span></span>

 <span data-ttu-id="be177-111">Различия между этими двумя способами более подробно описываются в разделе [Использование COM-типов в управляемом коде](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/3y76b69k(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="be177-111">The differences between these two techniques are discussed in greater detail in [Using COM Types in Managed Code](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/3y76b69k(v=vs.100)).</span></span>

 <span data-ttu-id="be177-112">Внедрение типов взаимодействия с помощью Visual Studio демонстрируется в разделе [Пошаговое руководство. Внедрение типов из управляемых сборок в Visual Studio](../../standard/assembly/embed-types-visual-studio.md).</span><span class="sxs-lookup"><span data-stu-id="be177-112">Embedding interop types with Visual Studio is demonstrated in [Walkthrough: Embedding Types from Managed Assemblies in Visual Studio](../../standard/assembly/embed-types-visual-studio.md).</span></span>

 <span data-ttu-id="be177-113">Чтобы сослаться на сборку взаимодействия с помощью компилятора командной строки и внедрить сведения о типе в исполняемые файлы, используйте параметр [-C# Link (параметры компилятора)](../../csharp/language-reference/compiler-options/link-compiler-option.md) или [-Link (Visual Basic)](../../visual-basic/reference/command-line-compiler/link.md) и укажите имя сборки взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="be177-113">To reference an interop assembly with a command-line compiler and embed type information in your executables, use the [-link (C# Compiler Options)](../../csharp/language-reference/compiler-options/link-compiler-option.md) or the [-link (Visual Basic)](../../visual-basic/reference/command-line-compiler/link.md) compiler switch and specify the name of the interop assembly.</span></span>

> [!NOTE]
> <span data-ttu-id="be177-114">Приложения Visual C++ не поддерживают внедрение сведений о типах, однако могут взаимодействовать с приложениями и надстройками, в которых такая возможность присутствует.</span><span class="sxs-lookup"><span data-stu-id="be177-114">Visual C++ applications cannot embed type information, but they can interoperate with applications or add-ins that do.</span></span>

 <span data-ttu-id="be177-115">Чтобы скомпилировать приложение, которое включает основную сборку взаимодействия при развертывании, задайте параметр компилятора **/reference** и укажите имя сборки взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="be177-115">To compile an application that includes a primary interop assembly when it is deployed, use the **/reference** compiler switch and specify the name of the interop assembly.</span></span>

## <a name="see-also"></a><span data-ttu-id="be177-116">См. также</span><span class="sxs-lookup"><span data-stu-id="be177-116">See also</span></span>

- [<span data-ttu-id="be177-117">Предоставление COM-компонентов платформе .NET Framework</span><span class="sxs-lookup"><span data-stu-id="be177-117">Exposing COM Components to the .NET Framework</span></span>](exposing-com-components.md)
- [<span data-ttu-id="be177-118">Независимость от языка и независимые от языка компоненты</span><span class="sxs-lookup"><span data-stu-id="be177-118">Language Independence and Language-Independent Components</span></span>](../../standard/language-independence-and-language-independent-components.md)
- <span data-ttu-id="be177-119">[Using COM Types in Managed Code](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/3y76b69k(v=vs.100)) (Использование COM-типов в управляемом коде)</span><span class="sxs-lookup"><span data-stu-id="be177-119">[Using COM Types in Managed Code](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/3y76b69k(v=vs.100))</span></span>
- [<span data-ttu-id="be177-120">Пошаговое руководство. Внедрение типов из управляемых сборок в Visual Studio</span><span class="sxs-lookup"><span data-stu-id="be177-120">Walkthrough: Embedding Types from Managed Assemblies in Visual Studio</span></span>](../../standard/assembly/embed-types-visual-studio.md)
- [<span data-ttu-id="be177-121">Импорт библиотеки типов в виде сборки</span><span class="sxs-lookup"><span data-stu-id="be177-121">Importing a Type Library as an Assembly</span></span>](importing-a-type-library-as-an-assembly.md)
