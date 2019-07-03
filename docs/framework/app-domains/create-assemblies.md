---
title: Создание сборок
ms.date: 03/30/2017
helpviewer_keywords:
- assemblies [.NET Framework], multifile
- single-file assemblies
- assemblies [.NET Framework], creating
- multifile assemblies
ms.assetid: 54832ee9-dca8-4c8b-913c-c0b9d265e9a4
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8e544976b0b801b08af238b2aeb36b5611154379
ms.sourcegitcommit: 34593b4d0be779699d38a9949d6aec11561657ec
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/11/2019
ms.locfileid: "66832902"
---
# <a name="creating-assemblies"></a><span data-ttu-id="0877f-102">Создание сборок</span><span class="sxs-lookup"><span data-stu-id="0877f-102">Creating Assemblies</span></span>

<span data-ttu-id="0877f-103">Можно создать однофайловую или многофайловую сборку с помощью интегрированной среды разработки, например Visual Studio, или с помощью компиляторов и средств, предоставляемых в пакете средств разработки программного обеспечения для Windows.</span><span class="sxs-lookup"><span data-stu-id="0877f-103">You can create single-file or multifile assemblies using an IDE, such as Visual Studio, or the compilers and tools provided by the Windows Software Development Kit (SDK).</span></span> <span data-ttu-id="0877f-104">Простейшая сборка представляет собой один файл, имеющий простое имя и загружаемый в единственный домен приложения.</span><span class="sxs-lookup"><span data-stu-id="0877f-104">The simplest assembly is a single file that has a simple name and is loaded into a single application domain.</span></span> <span data-ttu-id="0877f-105">На эту сборку нельзя ссылаться из других сборок, находящихся вне папки приложения; кроме того, к ней неприменим механизм проверки версий.</span><span class="sxs-lookup"><span data-stu-id="0877f-105">This assembly cannot be referenced by other assemblies outside the application directory and does not undergo version checking.</span></span> <span data-ttu-id="0877f-106">Для удаления приложения, состоящего из сборки, достаточно просто удалить папку, в которой оно располагается.</span><span class="sxs-lookup"><span data-stu-id="0877f-106">To uninstall the application made up of the assembly, you simply delete the directory where it resides.</span></span> <span data-ttu-id="0877f-107">Для большинства разработчиков сборки с такими возможностями достаточно для развертывания приложения.</span><span class="sxs-lookup"><span data-stu-id="0877f-107">For many developers, an assembly with these features is all that is needed to deploy an application.</span></span>

<span data-ttu-id="0877f-108">Многофайловую сборку можно создать на основе нескольких модулей кода и файлов ресурсов.</span><span class="sxs-lookup"><span data-stu-id="0877f-108">You can create a multifile assembly from several code modules and resource files.</span></span> <span data-ttu-id="0877f-109">Кроме того, можно создать сборку, которая будет совместно использоваться несколькими приложениями.</span><span class="sxs-lookup"><span data-stu-id="0877f-109">You can also create an assembly that can be shared by multiple applications.</span></span> <span data-ttu-id="0877f-110">Совместно используемая сборка должна иметь строгое имя и должна быть развернута в глобальном кэше сборок.</span><span class="sxs-lookup"><span data-stu-id="0877f-110">A shared assembly must have a strong name and can be deployed in the global assembly cache.</span></span>

<span data-ttu-id="0877f-111">Существует несколько способов объединения модулей кода и ресурсов в сборки; способ зависит от следующих факторов.</span><span class="sxs-lookup"><span data-stu-id="0877f-111">You have several options when grouping code modules and resources into assemblies, depending on the following factors:</span></span>

- <span data-ttu-id="0877f-112">Управление версиями</span><span class="sxs-lookup"><span data-stu-id="0877f-112">Versioning</span></span>

     <span data-ttu-id="0877f-113">Объединение модулей, имеющих одни и те же сведения о версии.</span><span class="sxs-lookup"><span data-stu-id="0877f-113">Group modules that should have the same version information.</span></span>

- <span data-ttu-id="0877f-114">Развертывание</span><span class="sxs-lookup"><span data-stu-id="0877f-114">Deployment</span></span>

     <span data-ttu-id="0877f-115">Объединение модулей кода и ресурсов, поддерживающих данную модель развертывания.</span><span class="sxs-lookup"><span data-stu-id="0877f-115">Group code modules and resources that support your model of deployment.</span></span>

- <span data-ttu-id="0877f-116">Повторное использование</span><span class="sxs-lookup"><span data-stu-id="0877f-116">Reuse</span></span>

     <span data-ttu-id="0877f-117">Объединение модулей, если они могут логически использоваться совместно для некоторых целей.</span><span class="sxs-lookup"><span data-stu-id="0877f-117">Group modules if they can be logically used together for some purpose.</span></span> <span data-ttu-id="0877f-118">Например, сборка, состоящая из типов и классов, редко используемых для сопровождения программы, может быть помещена в ту же самую сборку.</span><span class="sxs-lookup"><span data-stu-id="0877f-118">For example, an assembly consisting of types and classes used infrequently for program maintenance can be put in the same assembly.</span></span> <span data-ttu-id="0877f-119">Кроме того, типы, предназначенные для совместного использования несколькими приложениями, могут быть объединены в сборку, которая должна быть подписана строгим именем.</span><span class="sxs-lookup"><span data-stu-id="0877f-119">In addition, types that you intend to share with multiple applications should be grouped into an assembly and the assembly should be signed with a strong name.</span></span>

- <span data-ttu-id="0877f-120">Безопасность</span><span class="sxs-lookup"><span data-stu-id="0877f-120">Security</span></span>

     <span data-ttu-id="0877f-121">Объединение модулей, содержащих типы, которым требуются одни и те же разрешения безопасности.</span><span class="sxs-lookup"><span data-stu-id="0877f-121">Group modules containing types that require the same security permissions.</span></span>

- <span data-ttu-id="0877f-122">Область действия</span><span class="sxs-lookup"><span data-stu-id="0877f-122">Scoping</span></span>

     <span data-ttu-id="0877f-123">Объединение модулей, содержащих типы, область видимости которых должна быть ограничена этой же сборкой.</span><span class="sxs-lookup"><span data-stu-id="0877f-123">Group modules containing types whose visibility should be restricted to the same assembly.</span></span>

<span data-ttu-id="0877f-124">Необходимо обратить особое внимание при предоставлении доступа к сборкам среды CLR из неуправляемых COM-приложений.</span><span class="sxs-lookup"><span data-stu-id="0877f-124">Special considerations must be made when making common language runtime assemblies available to unmanaged COM applications.</span></span> <span data-ttu-id="0877f-125">Дополнительные сведения о работе с неуправляемым кодом содержатся в разделе [Предоставление COM-клиентам доступа к компонентам .NET Framework](../../../docs/framework/interop/exposing-dotnet-components-to-com.md).</span><span class="sxs-lookup"><span data-stu-id="0877f-125">For more information about working with unmanaged code, see [Exposing .NET Framework Components to COM](../../../docs/framework/interop/exposing-dotnet-components-to-com.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="0877f-126">См. также</span><span class="sxs-lookup"><span data-stu-id="0877f-126">See also</span></span>

- [<span data-ttu-id="0877f-127">Программирование с использованием сборок</span><span class="sxs-lookup"><span data-stu-id="0877f-127">Programming with Assemblies</span></span>](../../../docs/framework/app-domains/programming-with-assemblies.md)
- [<span data-ttu-id="0877f-128">Управление версиями сборок</span><span class="sxs-lookup"><span data-stu-id="0877f-128">Assembly Versioning</span></span>](../../../docs/framework/app-domains/assembly-versioning.md)
- [<span data-ttu-id="0877f-129">Практическое руководство. Построение однофайловой сборки</span><span class="sxs-lookup"><span data-stu-id="0877f-129">How to: Build a Single-File Assembly</span></span>](../../../docs/framework/app-domains/how-to-build-a-single-file-assembly.md)
- [<span data-ttu-id="0877f-130">Практическое руководство. Создание многофайловой сборки</span><span class="sxs-lookup"><span data-stu-id="0877f-130">How to: Build a Multifile Assembly</span></span>](../../../docs/framework/app-domains/how-to-build-a-multifile-assembly.md)
- [<span data-ttu-id="0877f-131">Обнаружение сборок в среде выполнения</span><span class="sxs-lookup"><span data-stu-id="0877f-131">How the Runtime Locates Assemblies</span></span>](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
- [<span data-ttu-id="0877f-132">Многофайловые сборки</span><span class="sxs-lookup"><span data-stu-id="0877f-132">Multifile Assemblies</span></span>](../../../docs/framework/app-domains/multifile-assemblies.md)
