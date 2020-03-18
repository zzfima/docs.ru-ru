---
title: Использование dotnet-svcutil.xmlserializer
description: Узнайте, как использовать пакет NuGet `dotnet-svcutil.xmlserializer`, чтобы предварительно генерировать сборку сериализации для проектов .NET Core.
author: huanwu
ms.date: 11/27/2018
ms.openlocfilehash: 4811647c294118cb160d25805e7d3ada97f071f9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "75344901"
---
# <a name="using-dotnet-svcutilxmlserializer-on-net-core"></a><span data-ttu-id="8cdb2-103">Использование dotnet-svcutil.xmlserializer в .NET Core</span><span class="sxs-lookup"><span data-stu-id="8cdb2-103">Using dotnet-svcutil.xmlserializer on .NET Core</span></span>

<span data-ttu-id="8cdb2-104">Пакет NuGet `dotnet-svcutil.xmlserializer` может предварительно генерировать сборку сериализации для проектов .NET Core.</span><span class="sxs-lookup"><span data-stu-id="8cdb2-104">The `dotnet-svcutil.xmlserializer` NuGet package can pre-generate a serialization assembly for .NET Core projects.</span></span> <span data-ttu-id="8cdb2-105">Он предварительно генерирует код сериализации C# для типов в клиентском приложении, которые используются в контракте службы WCF и которые можно сериализовать с помощью XmlSerializer.</span><span class="sxs-lookup"><span data-stu-id="8cdb2-105">It pre-generates C# serialization code for the types in the client application that are used by the WCF Service Contract and that can be serialized by the XmlSerializer.</span></span> <span data-ttu-id="8cdb2-106">Это улучшает начальную производительность сериализации XML при сериализации или десериализации объектов этих типов.</span><span class="sxs-lookup"><span data-stu-id="8cdb2-106">This improves the startup performance of XML serialization when serializing or deserializing objects of those types.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="8cdb2-107">Prerequisites</span><span class="sxs-lookup"><span data-stu-id="8cdb2-107">Prerequisites</span></span>

* <span data-ttu-id="8cdb2-108">[пакет SDK для .NET Core 2.1](https://dotnet.microsoft.com/download) или более поздней версии;</span><span class="sxs-lookup"><span data-stu-id="8cdb2-108">[.NET Core 2.1 SDK](https://dotnet.microsoft.com/download) or later</span></span>
* <span data-ttu-id="8cdb2-109">Любой редактор кода</span><span class="sxs-lookup"><span data-stu-id="8cdb2-109">Your favorite code editor</span></span>

<span data-ttu-id="8cdb2-110">Вы можете использовать команду `dotnet --info`, чтобы проверить, какие версии пакета SDK и среды выполнения для .NET Core уже установлены.</span><span class="sxs-lookup"><span data-stu-id="8cdb2-110">You can use the command `dotnet --info` to check which versions of .NET Core SDK and runtime you already have installed.</span></span>

## <a name="getting-started"></a><span data-ttu-id="8cdb2-111">Начало работы</span><span class="sxs-lookup"><span data-stu-id="8cdb2-111">Getting started</span></span>

<span data-ttu-id="8cdb2-112">Чтобы использовать `dotnet-svcutil.xmlserializer` в консольном приложении .NET Core, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="8cdb2-112">To use `dotnet-svcutil.xmlserializer` in a .NET Core console application:</span></span>

1. <span data-ttu-id="8cdb2-113">Создайте службу WCF с именем MyWCFService с помощью шаблона по умолчанию "Приложение WCF-службы" в .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="8cdb2-113">Create a WCF Service named 'MyWCFService' using the default template 'WCF Service Application' in .NET Framework.</span></span> <span data-ttu-id="8cdb2-114">Добавьте атрибут `[XmlSerializerFormat]` в метод службы.</span><span class="sxs-lookup"><span data-stu-id="8cdb2-114">Add `[XmlSerializerFormat]` attribute on the service method like the following:</span></span>

   ```csharp
    [ServiceContract]
    public interface IService1
    {
        [XmlSerializerFormat]
        [OperationContract(Action = "http://tempuri.org/IService1/GetData", ReplyAction = "http://tempuri.org/IService1/GetDataResponse")]
        string GetData(int value);
    }
    ```

2. <span data-ttu-id="8cdb2-115">Для этого создайте консольное приложение .NET Core как клиентское приложение WCF, ориентированное на .NET Core 2.1 или более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="8cdb2-115">Create a .NET Core console application as WCF client application that targets at .NET Core 2.1 or later versions.</span></span> <span data-ttu-id="8cdb2-116">Например, с помощью приведенной ниже команды создайте приложение с именем MyWCFClient.</span><span class="sxs-lookup"><span data-stu-id="8cdb2-116">For example, create an app named 'MyWCFClient' with the following command:</span></span>

    ```dotnetcli
    dotnet new console --name MyWCFClient
    ```

    <span data-ttu-id="8cdb2-117">Чтобы убедиться, что проект предназначен для .NET Core 2.1 или более поздней версии, в файле проекта проверьте XML-элемент `TargetFramework`.</span><span class="sxs-lookup"><span data-stu-id="8cdb2-117">To ensure your project is targeting .NET Core 2.1 or later, inspect the `TargetFramework` XML element in your project file:</span></span>

    ```xml
    <TargetFramework>netcoreapp2.1</TargetFramework>
    ```

3. <span data-ttu-id="8cdb2-118">Добавьте ссылку на пакет в `System.ServiceModel.Http`, выполнив приведенную ниже команду.</span><span class="sxs-lookup"><span data-stu-id="8cdb2-118">Add a package reference to `System.ServiceModel.Http` by running the following command:</span></span>

    ```dotnetcli
    dotnet add package System.ServiceModel.Http
    ```

4. <span data-ttu-id="8cdb2-119">Добавьте код клиента WCF:</span><span class="sxs-lookup"><span data-stu-id="8cdb2-119">Add the WCF Client code:</span></span>

    ```csharp
    using System.ServiceModel;

        class Program
        {
            static void Main(string[] args)
            {
                var myBinding = new BasicHttpBinding();
                var myEndpoint = new EndpointAddress("http://localhost:2561/Service1.svc"); //Fill your service url here
                var myChannelFactory = new ChannelFactory<IService1>(myBinding, myEndpoint);
                IService1 client = myChannelFactory.CreateChannel();
                string s = client.GetData(1);
                ((ICommunicationObject)client).Close();
            }
        }

    [ServiceContract]
    public interface IService1
    {
        [XmlSerializerFormat]
        [OperationContract(Action = "http://tempuri.org/IService1/GetData", ReplyAction = "http://tempuri.org/IService1/GetDataResponse")]
        string GetData(int value);
    }
    ```

5. <span data-ttu-id="8cdb2-120">Добавьте ссылку на пакет `dotnet-svcutil.xmlserializer`, выполнив приведенную ниже команду.</span><span class="sxs-lookup"><span data-stu-id="8cdb2-120">Add a reference to the `dotnet-svcutil.xmlserializer` package by running the following command:</span></span>
  
    ```dotnetcli
    dotnet add package dotnet-svcutil.xmlserializer
    ```

    <span data-ttu-id="8cdb2-121">При выполнении команды следует добавить запись в файл проекта, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="8cdb2-121">Running the command should add an entry to your project file similar to this:</span></span>
  
    ```xml
    <ItemGroup>
      <DotNetCliToolReference Include="dotnet-svcutil.xmlserializer" Version="1.0.0" />
    </ItemGroup>
    ```

6. <span data-ttu-id="8cdb2-122">Выполните сборку приложения с помощью команды `dotnet build`.</span><span class="sxs-lookup"><span data-stu-id="8cdb2-122">Build the application by running `dotnet build`.</span></span> <span data-ttu-id="8cdb2-123">Если все пройдет успешно, в папке выходных данных генерируется сборка с именем *MyWCFClient.XmlSerializers.dll*.</span><span class="sxs-lookup"><span data-stu-id="8cdb2-123">If everything succeeds, an assembly named *MyWCFClient.XmlSerializers.dll* is generated in the output folder.</span></span> <span data-ttu-id="8cdb2-124">В выходных данных сборки будут отображаться предупреждения, если создание сборки средством завершилось сбоем.</span><span class="sxs-lookup"><span data-stu-id="8cdb2-124">If the tool failed to generate the assembly, you'll see warnings in the build output.</span></span>

7. <span data-ttu-id="8cdb2-125">Например, перейдя к `http://localhost:2561/Service1.svc` в браузере, запустите службу WCF.</span><span class="sxs-lookup"><span data-stu-id="8cdb2-125">Start the WCF service by, for example, running `http://localhost:2561/Service1.svc` in the browser.</span></span> <span data-ttu-id="8cdb2-126">Затем запустите клиентское приложение,которое будет автоматически загружать и использовать предварительно созданные сериализаторы в среде выполнения.</span><span class="sxs-lookup"><span data-stu-id="8cdb2-126">Then start the client application, and it will automatically load and use the pre-generated serializers at runtime.</span></span>
