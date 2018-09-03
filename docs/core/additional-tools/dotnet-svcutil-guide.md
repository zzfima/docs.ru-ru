---
title: Средство Microsoft WCF dotnet-svcutil
description: Обзор инструмента Microsoft WCF dotnet-svcutil, который расширяет функциональные возможности проектов .NET Core и ASP.NET Core аналогично инструменту WCF svcutil для проектов .NET Framework.
author: mlacouture
ms.author: jralexander
ms.date: 08/20/2018
ms.openlocfilehash: bb4d8e5f3997318b720535b0f1e07fc33d13338a
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2018
ms.locfileid: "43484125"
---
# <a name="microsoft-wcf-dotnet-svcutil-tool"></a><span data-ttu-id="6e193-103">Средство Microsoft WCF dotnet-svcutil</span><span class="sxs-lookup"><span data-stu-id="6e193-103">Microsoft WCF dotnet-svcutil tool</span></span>

<span data-ttu-id="6e193-104">Средство WCF (Windows Communication Foundation) **dotnet-svcutil** — это средство .NET Core CLI, которое извлекает метаданные веб-службы в сетевом расположении или из WSDL-файла, а затем создает класс WCF, содержащий клиентские методы прокси-сервера, который используется для доступа к операциям веб-службы.</span><span class="sxs-lookup"><span data-stu-id="6e193-104">The Windows Communication Foundation (WCF) **dotnet-svcutil** tool is a .NET Core CLI tool that retrieves metadata from a web service on a network location or from a WSDL file, and generates a WCF class containing client proxy methods that access the web service operations.</span></span>

<span data-ttu-id="6e193-105">Как и [**Service Model Metadata — svcutil**](../../framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) для проектов .NET Framework, **dotnet-svcutil** является программой командной строки для создания ссылки на веб-службу, совместимой с проектами .NET Core и .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="6e193-105">Similar to the [**Service Model Metadata - svcutil**](../../framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) tool for .NET Framework projects, the **dotnet-svcutil** is a command-line tool for generating a web service reference compatible with .NET Core and .NET Standard projects.</span></span>

<span data-ttu-id="6e193-106">Средство **dotnet-svcutil** служит альтернативой для поставщика подключенной службы Visual Studio [**WCF Web Service Reference**](wcf-web-service-reference-guide.md), впервые представленного в Visual Studio 2017 версии 15.5.</span><span class="sxs-lookup"><span data-stu-id="6e193-106">The **dotnet-svcutil** tool is an alternative option to the [**WCF Web Service Reference**](wcf-web-service-reference-guide.md) Visual Studio connected service provider that first shipped with Visual Studio 2017 v15.5.</span></span> <span data-ttu-id="6e193-107">Как и .NET Core CLI, средство **dotnet-svcutil** доступно на платформах Linux, macOS и Windows.</span><span class="sxs-lookup"><span data-stu-id="6e193-107">The **dotnet-svcutil** tool as a .NET Core CLI tool, is available cross-platform on Linux, macOS, and Windows.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6e193-108">Ссылаться на службы следует только из надежного источника.</span><span class="sxs-lookup"><span data-stu-id="6e193-108">You should only reference services from a trusted source.</span></span> <span data-ttu-id="6e193-109">Добавление ссылок из ненадежного источника может нарушить безопасность.</span><span class="sxs-lookup"><span data-stu-id="6e193-109">Adding references from an untrusted source may compromise security.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="6e193-110">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="6e193-110">Prerequisites</span></span>

* <span data-ttu-id="6e193-111">[Пакет SDK для .NET Core](https://www.microsoft.com/net/download) 1.0.4 или более поздней версии</span><span class="sxs-lookup"><span data-stu-id="6e193-111">[.NET Core SDK](https://www.microsoft.com/net/download) v1.0.4 or later versions</span></span>
* <span data-ttu-id="6e193-112">Любой редактор кода</span><span class="sxs-lookup"><span data-stu-id="6e193-112">Your favorite code editor</span></span>

## <a name="getting-started"></a><span data-ttu-id="6e193-113">Начало работы</span><span class="sxs-lookup"><span data-stu-id="6e193-113">Getting started</span></span>

<span data-ttu-id="6e193-114">В следующем примере описываются шаги, необходимые для добавления ссылки на веб-службу в проект консольного приложения .NET Core и вызова службы.</span><span class="sxs-lookup"><span data-stu-id="6e193-114">The following example walks you through the steps required to add a web service reference to a .NET Core console project and invoke the service.</span></span> <span data-ttu-id="6e193-115">Вы создадите консольное приложение .NET Core с именем _HelloSvcutil_ и добавите ссылку на веб-службу, которая реализует следующий контракт:</span><span class="sxs-lookup"><span data-stu-id="6e193-115">You will create a .NET Core console application named _HelloSvcutil_ and will add a reference to a web service that implements the following contract:</span></span>

```csharp
[ServiceContract]
public interface ISayHello
{
    [OperationContract]
    string Hello(string name);
}
```

<span data-ttu-id="6e193-116">В этом примере предполагается, что веб-служба размещена по следующему адресу: `http://contoso.com/SayHello.svc`</span><span class="sxs-lookup"><span data-stu-id="6e193-116">For this example, the web service will be assumed to be hosted at the following address: `http://contoso.com/SayHello.svc`</span></span>

<span data-ttu-id="6e193-117">В окне командной строки Windows, macOS или Linux выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="6e193-117">From a Windows, macOS, or Linux command window perform the following steps:</span></span>

1. <span data-ttu-id="6e193-118">Создайте для проекта каталог с именем _HelloSvcutil_ и сделайте его текущим каталогом, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="6e193-118">Create a directory named _HelloSvcutil_ for your project and make it your current directory, as in the following example:</span></span>

```console
mkdir HelloSvcutil
cd HelloSvcutil
```

2. <span data-ttu-id="6e193-119">Создайте в этом каталоге новый проект консольного приложения C# с помощью команд [`dotnet new`](../tools/dotnet-new.md), как показано ниже:</span><span class="sxs-lookup"><span data-stu-id="6e193-119">Create a new C# console project in that directory using the [`dotnet new`](../tools/dotnet-new.md) command as follows:</span></span>

```console
dotnet new console
```

3. <span data-ttu-id="6e193-120">Откройте в редакторе файл проекта `HelloSvcutil.csproj`, измените элемент `Project` и добавьте [пакет NuGet `dotnet-svcutil`](https://nuget.org/packages/dotnet-svcutil) в виде ссылки на средство командной строки, используя следующий код:</span><span class="sxs-lookup"><span data-stu-id="6e193-120">Open the `HelloSvcutil.csproj` project file in your editor, edit the `Project` element, and add the [`dotnet-svcutil` NuGet package](https://nuget.org/packages/dotnet-svcutil) as a CLI tool reference, using the following code:</span></span>

```xml
<ItemGroup>
  <DotNetCliToolReference Include="dotnet-svcutil" Version="1.0.*" />
</ItemGroup>
```

4. <span data-ttu-id="6e193-121">Восстановите пакет _dotnet-svcutil_ с помощью команды [`dotnet restore`](../tools/dotnet-restore.md), как показано ниже:</span><span class="sxs-lookup"><span data-stu-id="6e193-121">Restore the _dotnet-svcutil_ package using the [`dotnet restore`](../tools/dotnet-restore.md) command as follows:</span></span>

```console
dotnet restore
```

5. <span data-ttu-id="6e193-122">Запустите _dotnet_ с помощью команды _svcutil_, чтобы создать файл со ссылкой на веб-службу, как показано ниже:</span><span class="sxs-lookup"><span data-stu-id="6e193-122">Run _dotnet_ with the _svcutil_ command to generate the web service reference file as follows:</span></span>

```console
dotnet svcutil http://contoso.com/SayHello.svc
```
<span data-ttu-id="6e193-123">Созданный файл сохраняется с именем _HelloSvcutil/ServiceReference1/Reference.cs_.</span><span class="sxs-lookup"><span data-stu-id="6e193-123">The generated file is saved as _HelloSvcutil/ServiceReference1/Reference.cs_.</span></span> <span data-ttu-id="6e193-124">Средство _dotnet_svcutil_ также добавляет в проект все необходимые пакеты WCF, которые указаны в коде прокси-сервера как ссылки на пакет.</span><span class="sxs-lookup"><span data-stu-id="6e193-124">The _dotnet_svcutil_ tool also adds to the project the appropriate WCF packages required by the proxy code as package references.</span></span>

6. <span data-ttu-id="6e193-125">Восстановите пакеты WCF с помощью команды [`dotnet restore`](../tools/dotnet-restore.md), как показано ниже:</span><span class="sxs-lookup"><span data-stu-id="6e193-125">Restore the WCF packages using the [`dotnet restore`](../tools/dotnet-restore.md) command as follows:</span></span>

```console
dotnet restore
```

7. <span data-ttu-id="6e193-126">Откройте в редакторе файл `Program.cs` и замените автоматически созданный код метода `Main()` приведенным ниже кодом для вызова веб-службы.</span><span class="sxs-lookup"><span data-stu-id="6e193-126">Open the `Program.cs` file in your editor, edit the `Main()` method, and replace the auto-generated code with the following code to invoke the web service:</span></span>

```csharp
static void Main(string[] args)
{
    var client = new SayHelloClient();
    Console.WriteLine(client.HelloAsync("dotnet-svcutil").Result);
}
```

8. <span data-ttu-id="6e193-127">Запустите приложение с помощью команды [`dotnet run`](../tools/dotnet-run.md), как показано ниже:</span><span class="sxs-lookup"><span data-stu-id="6e193-127">Run the application using the [`dotnet run`](../tools/dotnet-run.md) command as follows:</span></span>

```console
dotnet run
```
<span data-ttu-id="6e193-128">Вы увидите такой результат: "Hello dotnet-svcutil!".</span><span class="sxs-lookup"><span data-stu-id="6e193-128">You should see the following output: "Hello dotnet-svcutil!"</span></span>

<span data-ttu-id="6e193-129">Подробное описание параметров средства `dotnet-svcutil` можно получить, вызвав это средство с параметром help, как показано ниже:</span><span class="sxs-lookup"><span data-stu-id="6e193-129">For a detailed description of the `dotnet-svcutil` tool parameters, invoke the tool passing the help parameter as follows:</span></span>

```console
dotnet svcutil --help
```

## <a name="next-steps"></a><span data-ttu-id="6e193-130">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="6e193-130">Next steps</span></span>

### <a name="feedback--questions"></a><span data-ttu-id="6e193-131">Отзывы и вопросы</span><span class="sxs-lookup"><span data-stu-id="6e193-131">Feedback & questions</span></span>

<span data-ttu-id="6e193-132">Если у вас появились вопросы или отзывы, [сообщите об этом на сайте GitHub](https://github.com/dotnet/wcf/issues/new).</span><span class="sxs-lookup"><span data-stu-id="6e193-132">If you have any questions or feedback, [open an issue on GitHub](https://github.com/dotnet/wcf/issues/new).</span></span> <span data-ttu-id="6e193-133">Вы также можете просмотреть имеющиеся вопросы или проблемы [в репозитории WCF на сайте GitHub](https://github.com/dotnet/wcf/issues?utf8=%E2%9C%93&q=is:issue%20label:tooling).</span><span class="sxs-lookup"><span data-stu-id="6e193-133">You can also review any existing questions or issues [at the WCF repo on GitHub](https://github.com/dotnet/wcf/issues?utf8=%E2%9C%93&q=is:issue%20label:tooling).</span></span>

### <a name="release-notes"></a><span data-ttu-id="6e193-134">заметки о выпуске;</span><span class="sxs-lookup"><span data-stu-id="6e193-134">Release notes</span></span>

* <span data-ttu-id="6e193-135">Актуальные сведения о выпуске, включая описание известных проблем, см. в [заметках о выпуске](https://github.com/dotnet/wcf/blob/master/release-notes/dotnet-svcutil-notes.md).</span><span class="sxs-lookup"><span data-stu-id="6e193-135">Refer to the [Release notes](https://github.com/dotnet/wcf/blob/master/release-notes/dotnet-svcutil-notes.md) for updated release information, including known issues.</span></span>

### <a name="information"></a><span data-ttu-id="6e193-136">Сведения</span><span class="sxs-lookup"><span data-stu-id="6e193-136">Information</span></span>

* [<span data-ttu-id="6e193-137">Пакет NuGet dotnet-svcutil</span><span class="sxs-lookup"><span data-stu-id="6e193-137">dotnet-svcutil NuGet Package</span></span>](https://nuget.org/packages/dotnet-svcutil)
