---
title: Использование dotnet-svcutil.xmlserializer
description: Узнайте, как использовать пакет NuGet `dotnet-svcutil.xmlserializer`, чтобы предварительно генерировать сборку сериализации для проектов .NET Core.
author: huanwu
ms.date: 11/27/2018
ms.openlocfilehash: 4811647c294118cb160d25805e7d3ada97f071f9
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/25/2019
ms.locfileid: "75344901"
---
# <a name="using-dotnet-svcutilxmlserializer-on-net-core"></a>Использование dotnet-svcutil.xmlserializer в .NET Core

Пакет NuGet `dotnet-svcutil.xmlserializer` может предварительно генерировать сборку сериализации для проектов .NET Core. Он предварительно генерирует код сериализации C# для типов в клиентском приложении, которые используются в контракте службы WCF и которые можно сериализовать с помощью XmlSerializer. Это улучшает начальную производительность сериализации XML при сериализации или десериализации объектов этих типов.

## <a name="prerequisites"></a>Предварительные требования

* [пакет SDK для .NET Core 2.1](https://dotnet.microsoft.com/download) или более поздней версии;
* Любой редактор кода

Вы можете использовать команду `dotnet --info`, чтобы проверить, какие версии пакета SDK и среды выполнения для .NET Core уже установлены.

## <a name="getting-started"></a>Начало работы

Чтобы использовать `dotnet-svcutil.xmlserializer` в консольном приложении .NET Core, выполните следующие действия.

1. Создайте службу WCF с именем MyWCFService с помощью шаблона по умолчанию "Приложение WCF-службы" в .NET Framework. Добавьте атрибут `[XmlSerializerFormat]` в метод службы.

   ```csharp
    [ServiceContract]
    public interface IService1
    {
        [XmlSerializerFormat]
        [OperationContract(Action = "http://tempuri.org/IService1/GetData", ReplyAction = "http://tempuri.org/IService1/GetDataResponse")]
        string GetData(int value);
    }
    ```

2. Для этого создайте консольное приложение .NET Core как клиентское приложение WCF, ориентированное на .NET Core 2.1 или более поздних версий. Например, с помощью приведенной ниже команды создайте приложение с именем MyWCFClient.

    ```dotnetcli
    dotnet new console --name MyWCFClient
    ```

    Чтобы убедиться, что проект предназначен для .NET Core 2.1 или более поздней версии, в файле проекта проверьте XML-элемент `TargetFramework`.

    ```xml
    <TargetFramework>netcoreapp2.1</TargetFramework>
    ```

3. Добавьте ссылку на пакет в `System.ServiceModel.Http`, выполнив приведенную ниже команду.

    ```dotnetcli
    dotnet add package System.ServiceModel.Http
    ```

4. Добавьте код клиента WCF:

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

5. Добавьте ссылку на пакет `dotnet-svcutil.xmlserializer`, выполнив приведенную ниже команду.
  
    ```dotnetcli
    dotnet add package dotnet-svcutil.xmlserializer
    ```

    При выполнении команды следует добавить запись в файл проекта, как показано ниже.
  
    ```xml
    <ItemGroup>
      <DotNetCliToolReference Include="dotnet-svcutil.xmlserializer" Version="1.0.0" />
    </ItemGroup>
    ```

6. Выполните сборку приложения с помощью команды `dotnet build`. Если все пройдет успешно, в папке выходных данных генерируется сборка с именем *MyWCFClient.XmlSerializers.dll*. В выходных данных сборки будут отображаться предупреждения, если создание сборки средством завершилось сбоем.

7. Например, перейдя к `http://localhost:2561/Service1.svc` в браузере, запустите службу WCF. Затем запустите клиентское приложение,которое будет автоматически загружать и использовать предварительно созданные сериализаторы в среде выполнения.
