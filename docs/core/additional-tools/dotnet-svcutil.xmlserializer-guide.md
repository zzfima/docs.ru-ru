# <a name="using-dotnet-svcutilxmlserializer-on-net-core"></a>Использование dotnet-svcutil.xmlserializer в .NET Core

## <a name="prerequisites"></a>Предварительные требования

Для работы dotnet-svcutil.xmlserializer необходимы следующие компоненты. 

* [Пакет SDK для .NET Core 2.1 или более поздней версии](https://www.microsoft.com/net/download/dotnet-core/sdk-2.1.300)
* [Среда выполнения для .NET Core версии 2.1 или более поздней](https://www.microsoft.com/net/download/dotnet-core/runtime-2.1.0).

Вы можете использовать команду `dotnet --info`, чтобы проверить, какие версии пакета SDK и среды выполнения для .NET Core уже установлены.

Чтобы использовать dotnet-svcutil.xmlserializer в консольном приложении .NET Core, сделайте следующее:

1. Создайте службу WCF с именем MyWCFService с помощью шаблона по умолчанию "Приложение WCF-службы" в .NET Framework.  Добавьте атрибут ```[XmlSerializerFormat]``` в метод службы, как показано ниже.
    ```c#
    [ServiceContract]
    public interface IService1
    {
        [XmlSerializerFormat]
        [OperationContract(Action = "http://tempuri.org/IService1/GetData", ReplyAction = "http://tempuri.org/IService1/GetDataResponse")]
        string GetData(int value);
    }
    ```
2. Создайте консольное приложение .NET Core в качестве клиентского приложения WCF, нацеленного на netcoreapp 2.1. Например, создайте приложение с именем MyWCFClient с помощью следующей команды:
    ```
    dotnet new console --name MyWCFClient
    ```
    Проверьте, чтобы файл CSPROJ был нацелен на netcoreapp 2.1. Это можно сделать, используя в этом файле следующий XML-элемент:
    ```xml
    <TargetFramework>netcoreapp2.1</TargetFramework>
    ```
3. Добавьте ссылку на пакет в System.ServiceModel.Http, выполнив следующую команду:
   
   ```dotnet add package System.ServiceModel.Http -v 4.5.0```

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
5. Измените файл CSPROJ, добавив ссылку на пакет dotnet-svcutil.xmlserializer. Например:

    i. Выполните команду: `dotnet add package dotnet-svcutil.xmlserializer -v 1.0.0`.

    ii. Добавьте следующие строки в файл MyWCFClient.csproj:
    ```xml
    <ItemGroup>
      <DotNetCliToolReference Include="dotnet-svcutil.xmlserializer" Version="1.0.0" />
    </ItemGroup>
    ```

6. Выполните сборку приложения с помощью команды `dotnet build`. Если все пройдет успешно, в папке выходных данных создастся сборка с именем MyWCFClient.XmlSerializers.dll. Если создание сборки завершилось сбоем, в выходных данных сборки будут содержаться предупреждения.

7. Запустите службу WCF, например перейдя к http://localhost:2561/Service1.svc в браузере. Затем запустите клиентское приложение,которое будет автоматически загружать и использовать предварительно созданные сериализаторы в среде выполнения.
