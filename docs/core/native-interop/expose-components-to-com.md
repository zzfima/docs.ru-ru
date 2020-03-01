---
title: Предоставление доступа к компонентам .NET Core для COM
ms.date: 07/12/2019
helpviewer_keywords:
- exposing .NET Core components to COM
- interoperation with unmanaged code, exposing .NET Core components
- COM interop, exposing COM components
ms.assetid: 21271167-fe7f-46ba-a81f-a6812ea649d4
author: jkoritzinsky
ms.author: jekoritz
ms.openlocfilehash: 301177113f67748b62ea2686615cfe5378fdc2fd
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2020
ms.locfileid: "78157548"
---
# <a name="exposing-net-core-components-to-com"></a><span data-ttu-id="f1032-102">Предоставление доступа к компонентам .NET Core для COM</span><span class="sxs-lookup"><span data-stu-id="f1032-102">Exposing .NET Core components to COM</span></span>

<span data-ttu-id="f1032-103">В .NET Core процесс предоставления объектов .NET для модели COM значительно упрощен по сравнению с .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f1032-103">In .NET Core, the process for exposing your .NET objects to COM has been significantly streamlined in comparison to .NET Framework.</span></span> <span data-ttu-id="f1032-104">Ниже описывается, как предоставить класс для модели COM.</span><span class="sxs-lookup"><span data-stu-id="f1032-104">The following process will walk you through how to expose a class to COM.</span></span> <span data-ttu-id="f1032-105">В этом учебнике демонстрируется выполнение следующих действий:</span><span class="sxs-lookup"><span data-stu-id="f1032-105">This tutorial shows you how to:</span></span>

- <span data-ttu-id="f1032-106">Предоставление класса для модели COM из .NET Core.</span><span class="sxs-lookup"><span data-stu-id="f1032-106">Expose a class to COM from .NET Core.</span></span>
- <span data-ttu-id="f1032-107">Создайте сервер COM в процессе сборки библиотеки .NET Core.</span><span class="sxs-lookup"><span data-stu-id="f1032-107">Generate a COM server as part of building your .NET Core library.</span></span>
- <span data-ttu-id="f1032-108">Автоматически создайте параллельный манифест сервера для модели COM без поддержки реестра.</span><span class="sxs-lookup"><span data-stu-id="f1032-108">Automatically generate a side-by-side server manifest for Registry-Free COM.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f1032-109">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="f1032-109">Prerequisites</span></span>

- <span data-ttu-id="f1032-110">Установите [пакет SDK для .NET Core 3.0](https://dotnet.microsoft.com/download) или более новой версии.</span><span class="sxs-lookup"><span data-stu-id="f1032-110">Install [.NET Core 3.0 SDK](https://dotnet.microsoft.com/download) or a newer version.</span></span>

## <a name="create-the-library"></a><span data-ttu-id="f1032-111">Создание библиотеки</span><span class="sxs-lookup"><span data-stu-id="f1032-111">Create the library</span></span>

<span data-ttu-id="f1032-112">Сначала нужно создать библиотеку.</span><span class="sxs-lookup"><span data-stu-id="f1032-112">The first step is to create the library.</span></span>

1. <span data-ttu-id="f1032-113">Создайте новую папку и в этой папке выполните следующую команду.</span><span class="sxs-lookup"><span data-stu-id="f1032-113">Create a new folder, and in that folder run the following command:</span></span>

    ```dotnetcli
    dotnet new classlib
    ```

2. <span data-ttu-id="f1032-114">Откройте `Class1.cs`.</span><span class="sxs-lookup"><span data-stu-id="f1032-114">Open `Class1.cs`.</span></span>
3. <span data-ttu-id="f1032-115">Добавьте `using System.Runtime.InteropServices;` в начало файла.</span><span class="sxs-lookup"><span data-stu-id="f1032-115">Add `using System.Runtime.InteropServices;` to the top of the file.</span></span>
4. <span data-ttu-id="f1032-116">Создайте интерфейс с именем `IServer`.</span><span class="sxs-lookup"><span data-stu-id="f1032-116">Create an interface named `IServer`.</span></span> <span data-ttu-id="f1032-117">Пример:</span><span class="sxs-lookup"><span data-stu-id="f1032-117">For example:</span></span>

   [!code-csharp[The IServer interface](~/samples/core/extensions/COMServerDemo/COMContract/IServer.cs)]

5. <span data-ttu-id="f1032-118">Добавьте в интерфейс атрибут `[Guid("<IID>")]` с идентификатором GUID реализуемого интерфейса COM.</span><span class="sxs-lookup"><span data-stu-id="f1032-118">Add the `[Guid("<IID>")]` attribute to the interface, with the interface GUID for the COM interface you're implementing.</span></span> <span data-ttu-id="f1032-119">Например, `[Guid("fe103d6e-e71b-414c-80bf-982f18f6c1c7")]`.</span><span class="sxs-lookup"><span data-stu-id="f1032-119">For example, `[Guid("fe103d6e-e71b-414c-80bf-982f18f6c1c7")]`.</span></span> <span data-ttu-id="f1032-120">Обратите внимание, что этот идентификатор GUID должен быть уникальным, так как он является единственным идентификатором данного интерфейса для модели COM.</span><span class="sxs-lookup"><span data-stu-id="f1032-120">Note that this GUID needs to be unique since it is the only identifier of this interface for COM.</span></span> <span data-ttu-id="f1032-121">Чтобы создать идентификатор GUID в Visual Studio, выберите "Сервис" > "Создать GUID". Откроется средство создания идентификатора GUID.</span><span class="sxs-lookup"><span data-stu-id="f1032-121">In Visual Studio, you can generate a GUID by going to Tools > Create GUID to open the Create GUID tool.</span></span>
6. <span data-ttu-id="f1032-122">Добавьте в интерфейс атрибут `[InterfaceType]` и укажите, какие базовые COM-интерфейсы должен реализовывать ваш интерфейс.</span><span class="sxs-lookup"><span data-stu-id="f1032-122">Add the `[InterfaceType]` attribute to the interface and specify what base COM interfaces your interface should implement.</span></span>
7. <span data-ttu-id="f1032-123">Создайте класс `Server`, реализующий `IServer`.</span><span class="sxs-lookup"><span data-stu-id="f1032-123">Create a class named `Server` that implements `IServer`.</span></span>
8. <span data-ttu-id="f1032-124">Добавьте в класс атрибут `[Guid("<CLSID>")]` с идентификатором GUID реализуемого класса COM.</span><span class="sxs-lookup"><span data-stu-id="f1032-124">Add the `[Guid("<CLSID>")]` attribute to the class, with the class identifier GUID for the COM class you're implementing.</span></span> <span data-ttu-id="f1032-125">Например, `[Guid("9f35b6f5-2c05-4e7f-93aa-ee087f6e7ab6")]`.</span><span class="sxs-lookup"><span data-stu-id="f1032-125">For example, `[Guid("9f35b6f5-2c05-4e7f-93aa-ee087f6e7ab6")]`.</span></span> <span data-ttu-id="f1032-126">Так же как и в случае с идентификатором GUID интерфейса, этот идентификатор GUID должен быть уникальным, так как он является единственным идентификатором данного класса для модели COM.</span><span class="sxs-lookup"><span data-stu-id="f1032-126">As with the interface GUID, this GUID must be unique since it is the only identifier of this interface to COM.</span></span>
9. <span data-ttu-id="f1032-127">Добавьте атрибут `[ComVisible(true)]` как в интерфейс, так и в класс.</span><span class="sxs-lookup"><span data-stu-id="f1032-127">Add the `[ComVisible(true)]` attribute to both the interface and the class.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f1032-128">В отличие от .NET Framework, .NET Core требует указывать идентификатор CLSID любого класса, который должен активироваться через модель COM.</span><span class="sxs-lookup"><span data-stu-id="f1032-128">Unlike in .NET Framework, .NET Core requires you to specify the CLSID of any class you want to be activatable via COM.</span></span>

## <a name="generate-the-com-host"></a><span data-ttu-id="f1032-129">Создание узла COM</span><span class="sxs-lookup"><span data-stu-id="f1032-129">Generate the COM host</span></span>

1. <span data-ttu-id="f1032-130">Откройте файл проекта `.csproj` и добавьте элемент `<EnableComHosting>true</EnableComHosting>` внутри тега `<PropertyGroup></PropertyGroup>`.</span><span class="sxs-lookup"><span data-stu-id="f1032-130">Open the `.csproj` project file and add `<EnableComHosting>true</EnableComHosting>` inside a `<PropertyGroup></PropertyGroup>` tag.</span></span>
2. <span data-ttu-id="f1032-131">Выполните построение проекта.</span><span class="sxs-lookup"><span data-stu-id="f1032-131">Build the project.</span></span>

<span data-ttu-id="f1032-132">В результате будут получены файлы `ProjectName.dll`, `ProjectName.deps.json`, `ProjectName.runtimeconfig.json` и `ProjectName.comhost.dll`.</span><span class="sxs-lookup"><span data-stu-id="f1032-132">The resulting output will have a `ProjectName.dll`, `ProjectName.deps.json`, `ProjectName.runtimeconfig.json` and `ProjectName.comhost.dll` file.</span></span>

## <a name="register-the-com-host-for-com"></a><span data-ttu-id="f1032-133">Регистрация узла COM для модели COM</span><span class="sxs-lookup"><span data-stu-id="f1032-133">Register the COM host for COM</span></span>

<span data-ttu-id="f1032-134">Откройте командную строку с повышенными привилегиями и запустите `regsvr32 ProjectName.comhost.dll`.</span><span class="sxs-lookup"><span data-stu-id="f1032-134">Open an elevated command prompt and run `regsvr32 ProjectName.comhost.dll`.</span></span> <span data-ttu-id="f1032-135">Это приведет к регистрации всех предоставленных объектов .NET в модели COM.</span><span class="sxs-lookup"><span data-stu-id="f1032-135">That will register all of your exposed .NET objects with COM.</span></span>

## <a name="enabling-regfree-com"></a><span data-ttu-id="f1032-136">Реализация модели COM без поддержки реестра</span><span class="sxs-lookup"><span data-stu-id="f1032-136">Enabling RegFree COM</span></span>

1. <span data-ttu-id="f1032-137">Откройте файл проекта `.csproj` и добавьте элемент `<EnableRegFreeCom>true</EnableRegFreeCom>` внутри тега `<PropertyGroup></PropertyGroup>`.</span><span class="sxs-lookup"><span data-stu-id="f1032-137">Open the `.csproj` project file and add `<EnableRegFreeCom>true</EnableRegFreeCom>` inside a `<PropertyGroup></PropertyGroup>` tag.</span></span>
2. <span data-ttu-id="f1032-138">Выполните построение проекта.</span><span class="sxs-lookup"><span data-stu-id="f1032-138">Build the project.</span></span>

<span data-ttu-id="f1032-139">В результате будет также получен файл `ProjectName.X.manifest`.</span><span class="sxs-lookup"><span data-stu-id="f1032-139">The resulting output will now also have a `ProjectName.X.manifest` file.</span></span> <span data-ttu-id="f1032-140">Это параллельный манифест для использования с моделью COM без поддержки реестра.</span><span class="sxs-lookup"><span data-stu-id="f1032-140">This file is the side-by-side manifest for use with Registry-Free COM.</span></span>

## <a name="sample"></a><span data-ttu-id="f1032-141">Пример</span><span class="sxs-lookup"><span data-stu-id="f1032-141">Sample</span></span>

<span data-ttu-id="f1032-142">В репозитории dotnet/samples на сайте GitHub есть полнофункциональный [пример сервера COM](https://github.com/dotnet/samples/tree/master/core/extensions/COMServerDemo).</span><span class="sxs-lookup"><span data-stu-id="f1032-142">There is a fully functional [COM server sample](https://github.com/dotnet/samples/tree/master/core/extensions/COMServerDemo) in the dotnet/samples repository on GitHub.</span></span>

## <a name="additional-notes"></a><span data-ttu-id="f1032-143">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="f1032-143">Additional notes</span></span>

<span data-ttu-id="f1032-144">В отличие от .NET Framework, в .NET Core создание библиотеки типов COM (TLB) из сборки .NET Core не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="f1032-144">Unlike in .NET Framework, there is no support in .NET Core for generating a COM Type Library (TLB) from a .NET Core assembly.</span></span> <span data-ttu-id="f1032-145">Нужно вручную написать файл IDL или заголовок C/C++ для собственных объявлений COM-интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="f1032-145">The guidance is to either manually write an IDL file or a C/C++ header for the native declarations of the COM interfaces.</span></span>

<span data-ttu-id="f1032-146">Кроме того, загрузка как .NET Framework, так и .NET Core в один и тот же процесс имеет ограничения диагностического характера.</span><span class="sxs-lookup"><span data-stu-id="f1032-146">Additionally, loading both .NET Framework and .NET Core into the same process does have diagnostic limitations.</span></span> <span data-ttu-id="f1032-147">Основное ограничение — отладка управляемых компонентов, так как невозможно одновременно выполнить отладку .NET Framework и .NET Core.</span><span class="sxs-lookup"><span data-stu-id="f1032-147">The primary limitation is the debugging of managed components as it is not possible to debug both .NET Framework and .NET Core at the same time.</span></span> <span data-ttu-id="f1032-148">Кроме того, два экземпляра среды выполнения не используют управляемые сборки совместно.</span><span class="sxs-lookup"><span data-stu-id="f1032-148">In addition, the two runtime instances don't share managed assemblies.</span></span> <span data-ttu-id="f1032-149">Это означает, что невозможно совместно использовать фактические типы .NET в двух средах выполнения, вместо этого все взаимодействия должны быть ограничены предоставленными контрактами COM-интерфейса.</span><span class="sxs-lookup"><span data-stu-id="f1032-149">This means that it isn't possible to share actual .NET types across the two runtimes and instead all interactions must be restricted to the exposed COM interface contracts.</span></span>
