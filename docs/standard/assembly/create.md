---
title: Создание сборок
ms.date: 08/19/2019
helpviewer_keywords:
- assemblies [.NET Framework], multifile
- single-file assemblies
- assemblies [.NET Framework], creating
- multifile assemblies
ms.assetid: 54832ee9-dca8-4c8b-913c-c0b9d265e9a4
ms.openlocfilehash: 81fffb2b2e1d56d6068bf6f663a13fad6968a383
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2019
ms.locfileid: "73740518"
---
# <a name="create-assemblies"></a><span data-ttu-id="ca67d-102">Создание сборок</span><span class="sxs-lookup"><span data-stu-id="ca67d-102">Create assemblies</span></span>

<span data-ttu-id="ca67d-103">Однофайловую или многофайловую сборку можно создать с помощью интегрированной среды разработки, например Visual Studio, либо с помощью компиляторов и средств, доступных в Windows SDK.</span><span class="sxs-lookup"><span data-stu-id="ca67d-103">You can create single-file or multifile assemblies using an IDE, such as Visual Studio, or the compilers and tools provided by the Windows SDK.</span></span> <span data-ttu-id="ca67d-104">Простейшая сборка представляет собой один файл, имеющий простое имя и загружаемый в единственный домен приложения.</span><span class="sxs-lookup"><span data-stu-id="ca67d-104">The simplest assembly is a single file that has a simple name and is loaded into a single application domain.</span></span> <span data-ttu-id="ca67d-105">На эту сборку нельзя ссылаться из других сборок, находящихся вне папки приложения; кроме того, к ней неприменим механизм проверки версий.</span><span class="sxs-lookup"><span data-stu-id="ca67d-105">This assembly cannot be referenced by other assemblies outside the application directory and does not undergo version checking.</span></span> <span data-ttu-id="ca67d-106">Для удаления приложения, состоящего из сборки, достаточно просто удалить папку, в которой оно располагается.</span><span class="sxs-lookup"><span data-stu-id="ca67d-106">To uninstall the application made up of the assembly, you simply delete the directory where it resides.</span></span> <span data-ttu-id="ca67d-107">Для большинства разработчиков сборки с такими возможностями достаточно для развертывания приложения.</span><span class="sxs-lookup"><span data-stu-id="ca67d-107">For many developers, an assembly with these features is all that is needed to deploy an application.</span></span>

<span data-ttu-id="ca67d-108">Многофайловую сборку можно создать на основе нескольких модулей кода и файлов ресурсов.</span><span class="sxs-lookup"><span data-stu-id="ca67d-108">You can create a multifile assembly from several code modules and resource files.</span></span> <span data-ttu-id="ca67d-109">Кроме того, можно создать сборку, которая будет совместно использоваться несколькими приложениями.</span><span class="sxs-lookup"><span data-stu-id="ca67d-109">You can also create an assembly that can be shared by multiple applications.</span></span> <span data-ttu-id="ca67d-110">Совместно используемая сборка должна иметь строгое имя и должна быть развернута в глобальном кэше сборок.</span><span class="sxs-lookup"><span data-stu-id="ca67d-110">A shared assembly must have a strong name and can be deployed in the global assembly cache.</span></span>

<span data-ttu-id="ca67d-111">Существует несколько способов объединения модулей кода и ресурсов в сборки; способ зависит от следующих факторов.</span><span class="sxs-lookup"><span data-stu-id="ca67d-111">You have several options when grouping code modules and resources into assemblies, depending on the following factors:</span></span>

- <span data-ttu-id="ca67d-112">Управление версиями</span><span class="sxs-lookup"><span data-stu-id="ca67d-112">Versioning</span></span>

     <span data-ttu-id="ca67d-113">Объединение модулей, имеющих одни и те же сведения о версии.</span><span class="sxs-lookup"><span data-stu-id="ca67d-113">Group modules that should have the same version information.</span></span>

- <span data-ttu-id="ca67d-114">Развертывание</span><span class="sxs-lookup"><span data-stu-id="ca67d-114">Deployment</span></span>

     <span data-ttu-id="ca67d-115">Объединение модулей кода и ресурсов, поддерживающих данную модель развертывания.</span><span class="sxs-lookup"><span data-stu-id="ca67d-115">Group code modules and resources that support your model of deployment.</span></span>

- <span data-ttu-id="ca67d-116">Повторное использование</span><span class="sxs-lookup"><span data-stu-id="ca67d-116">Reuse</span></span>

     <span data-ttu-id="ca67d-117">Объединение модулей, если они могут логически использоваться совместно для некоторых целей.</span><span class="sxs-lookup"><span data-stu-id="ca67d-117">Group modules if they can be logically used together for some purpose.</span></span> <span data-ttu-id="ca67d-118">Например, сборка, состоящая из типов и классов, редко используемых для сопровождения программы, может быть помещена в ту же самую сборку.</span><span class="sxs-lookup"><span data-stu-id="ca67d-118">For example, an assembly consisting of types and classes used infrequently for program maintenance can be put in the same assembly.</span></span> <span data-ttu-id="ca67d-119">Кроме того, типы, предназначенные для совместного использования несколькими приложениями, могут быть объединены в сборку, которая должна быть подписана строгим именем.</span><span class="sxs-lookup"><span data-stu-id="ca67d-119">In addition, types that you intend to share with multiple applications should be grouped into an assembly and the assembly should be signed with a strong name.</span></span>

- <span data-ttu-id="ca67d-120">Безопасность</span><span class="sxs-lookup"><span data-stu-id="ca67d-120">Security</span></span>

     <span data-ttu-id="ca67d-121">Объединение модулей, содержащих типы, которым требуются одни и те же разрешения безопасности.</span><span class="sxs-lookup"><span data-stu-id="ca67d-121">Group modules containing types that require the same security permissions.</span></span>

- <span data-ttu-id="ca67d-122">Область действия</span><span class="sxs-lookup"><span data-stu-id="ca67d-122">Scoping</span></span>

     <span data-ttu-id="ca67d-123">Объединение модулей, содержащих типы, область видимости которых должна быть ограничена этой же сборкой.</span><span class="sxs-lookup"><span data-stu-id="ca67d-123">Group modules containing types whose visibility should be restricted to the same assembly.</span></span>

<span data-ttu-id="ca67d-124">Особое внимание нужно уделить предоставлению доступа к сборкам среды CLR из неуправляемых COM-приложений.</span><span class="sxs-lookup"><span data-stu-id="ca67d-124">There are special considerations when making common language runtime assemblies available to unmanaged COM applications.</span></span> <span data-ttu-id="ca67d-125">Дополнительные сведения о работе с неуправляемым кодом см. в разделе [Предоставление COM-клиентам доступа к компонентам .NET Framework](../../framework/interop/exposing-dotnet-components-to-com.md).</span><span class="sxs-lookup"><span data-stu-id="ca67d-125">For more information about working with unmanaged code, see [Expose .NET Framework components to COM](../../framework/interop/exposing-dotnet-components-to-com.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="ca67d-126">См. также</span><span class="sxs-lookup"><span data-stu-id="ca67d-126">See also</span></span>

- [<span data-ttu-id="ca67d-127">Управление версиями сборок</span><span class="sxs-lookup"><span data-stu-id="ca67d-127">Assembly versioning</span></span>](versioning.md)
- [<span data-ttu-id="ca67d-128">Практическое руководство. Создание однофайловой сборки</span><span class="sxs-lookup"><span data-stu-id="ca67d-128">How to: Build a single-file assembly</span></span>](../../framework/app-domains/build-single-file-assembly.md)
- [<span data-ttu-id="ca67d-129">Практическое руководство. Создание многофайловой сборки</span><span class="sxs-lookup"><span data-stu-id="ca67d-129">How to: Build a multifile assembly</span></span>](../../framework/app-domains/build-multifile-assembly.md)
- [<span data-ttu-id="ca67d-130">Обнаружение сборок в среде выполнения</span><span class="sxs-lookup"><span data-stu-id="ca67d-130">How the runtime locates assemblies</span></span>](../../framework/deployment/how-the-runtime-locates-assemblies.md)
- [<span data-ttu-id="ca67d-131">Многофайловые сборки</span><span class="sxs-lookup"><span data-stu-id="ca67d-131">Multifile assemblies</span></span>](../../framework/app-domains/multifile-assemblies.md)
