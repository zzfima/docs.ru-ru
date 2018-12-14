# <a name="using-dotnet-svcutilxmlserializer-on-net-core"></a><span data-ttu-id="38ea6-101">Использование dotnet-svcutil.xmlserializer в .NET Core</span><span class="sxs-lookup"><span data-stu-id="38ea6-101">Using dotnet-svcutil.xmlserializer on .NET Core</span></span>

## <a name="prerequisites"></a><span data-ttu-id="38ea6-102">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="38ea6-102">Prerequisites</span></span>

<span data-ttu-id="38ea6-103">Для работы dotnet-svcutil.xmlserializer необходимы следующие компоненты.</span><span class="sxs-lookup"><span data-stu-id="38ea6-103">The following is required for dotnet-svcutil.xmlserializer to work.</span></span> 

* [<span data-ttu-id="38ea6-104">Пакет SDK для .NET Core 2.1 или более поздней версии</span><span class="sxs-lookup"><span data-stu-id="38ea6-104">.NET Core 2.1 SDK or later</span></span>](https://www.microsoft.com/net/download/dotnet-core/sdk-2.1.300)
* <span data-ttu-id="38ea6-105">[Среда выполнения для .NET Core версии 2.1 или более поздней](https://www.microsoft.com/net/download/dotnet-core/runtime-2.1.0).</span><span class="sxs-lookup"><span data-stu-id="38ea6-105">[.NET Core Runtime 2.1 or later](https://www.microsoft.com/net/download/dotnet-core/runtime-2.1.0)</span></span>

<span data-ttu-id="38ea6-106">Вы можете использовать команду `dotnet --info`, чтобы проверить, какие версии пакета SDK и среды выполнения для .NET Core уже установлены.</span><span class="sxs-lookup"><span data-stu-id="38ea6-106">You can use the command `dotnet --info` to check which versions of .NET Core SDK and runtime you already have installed.</span></span>

<span data-ttu-id="38ea6-107">Чтобы использовать dotnet-svcutil.xmlserializer в консольном приложении .NET Core, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="38ea6-107">To use dotnet-svcutil.xmlserializer in a .NET Core console application:</span></span>

1. <span data-ttu-id="38ea6-108">Создайте службу WCF с именем MyWCFService с помощью шаблона по умолчанию "Приложение WCF-службы" в .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="38ea6-108">Create a WCF Service named 'MyWCFService' using the default template 'WCF Service Application' in .NET Framework.</span></span>  <span data-ttu-id="38ea6-109">Добавьте атрибут ```[XmlSerializerFormat]``` в метод службы, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="38ea6-109">Add ```[XmlSerializerFormat]``` attribute on the service method like the following</span></span>
    ```c#
    [ServiceContract]
    public interface IService1
    {
        [XmlSerializerFormat]
        [OperationContract(Action = "http://tempuri.org/IService1/GetData", ReplyAction = "http://tempuri.org/IService1/GetDataResponse")]
        string GetData(int value);
    }
    ```
2. <span data-ttu-id="38ea6-110">Создайте консольное приложение .NET Core в качестве клиентского приложения WCF, нацеленного на netcoreapp 2.1. Например, создайте приложение с именем MyWCFClient с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="38ea6-110">Create a .NET Core console application as WCF client application that targets at netcoreapp 2.1, e.g. create an app named 'MyWCFClient' with the command,</span></span>
    ```
    dotnet new console --name MyWCFClient
    ```
    <span data-ttu-id="38ea6-111">Проверьте, чтобы файл CSPROJ был нацелен на netcoreapp 2.1.</span><span class="sxs-lookup"><span data-stu-id="38ea6-111">Make sure your csproj targets a netcoreapp 2.1.</span></span> <span data-ttu-id="38ea6-112">Это можно сделать, используя в этом файле следующий XML-элемент:</span><span class="sxs-lookup"><span data-stu-id="38ea6-112">This is done using the following XML element in your .csproj file</span></span>
    ```xml
    <TargetFramework>netcoreapp2.1</TargetFramework>
    ```
3. <span data-ttu-id="38ea6-113">Добавьте ссылку на пакет в System.ServiceModel.Http, выполнив следующую команду:</span><span class="sxs-lookup"><span data-stu-id="38ea6-113">Add a package reference to System.ServiceModel.Http by running the following command:</span></span>
   
   ```dotnet add package System.ServiceModel.Http -v 4.5.0```

4. <span data-ttu-id="38ea6-114">Добавьте код клиента WCF:</span><span class="sxs-lookup"><span data-stu-id="38ea6-114">Add the WCF Client code:</span></span>
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
5. <span data-ttu-id="38ea6-115">Измените файл CSPROJ, добавив ссылку на пакет dotnet-svcutil.xmlserializer.</span><span class="sxs-lookup"><span data-stu-id="38ea6-115">Edit the .csproj file and add a reference to the dotnet-svcutil.xmlserializer package.</span></span> <span data-ttu-id="38ea6-116">Например:</span><span class="sxs-lookup"><span data-stu-id="38ea6-116">For example:</span></span>

    <span data-ttu-id="38ea6-117">i.</span><span class="sxs-lookup"><span data-stu-id="38ea6-117">i.</span></span> <span data-ttu-id="38ea6-118">Выполните команду: `dotnet add package dotnet-svcutil.xmlserializer -v 1.0.0`.</span><span class="sxs-lookup"><span data-stu-id="38ea6-118">Run command: `dotnet add package dotnet-svcutil.xmlserializer -v 1.0.0`</span></span>

    <span data-ttu-id="38ea6-119">ii.</span><span class="sxs-lookup"><span data-stu-id="38ea6-119">ii.</span></span> <span data-ttu-id="38ea6-120">Добавьте следующие строки в файл MyWCFClient.csproj:</span><span class="sxs-lookup"><span data-stu-id="38ea6-120">Add the following lines in MyWCFClient.csproj,</span></span>
    ```xml
    <ItemGroup>
      <DotNetCliToolReference Include="dotnet-svcutil.xmlserializer" Version="1.0.0" />
    </ItemGroup>
    ```

6. <span data-ttu-id="38ea6-121">Выполните сборку приложения с помощью команды `dotnet build`.</span><span class="sxs-lookup"><span data-stu-id="38ea6-121">Build the application by running `dotnet build`.</span></span> <span data-ttu-id="38ea6-122">Если все пройдет успешно, в папке выходных данных создастся сборка с именем MyWCFClient.XmlSerializers.dll.</span><span class="sxs-lookup"><span data-stu-id="38ea6-122">If everything succeeds, an assembly named MyWCFClient.XmlSerializers.dll will be generated in the output folder.</span></span> <span data-ttu-id="38ea6-123">Если создание сборки завершилось сбоем, в выходных данных сборки будут содержаться предупреждения.</span><span class="sxs-lookup"><span data-stu-id="38ea6-123">You will see warnings in the build output if the tool failed to generate the assembly.</span></span>

7. <span data-ttu-id="38ea6-124">Запустите службу WCF, например перейдя к http://localhost:2561/Service1.svc в браузере.</span><span class="sxs-lookup"><span data-stu-id="38ea6-124">Start the WCF service e.g. by running http://localhost:2561/Service1.svc in the browser.</span></span> <span data-ttu-id="38ea6-125">Затем запустите клиентское приложение,которое будет автоматически загружать и использовать предварительно созданные сериализаторы в среде выполнения.</span><span class="sxs-lookup"><span data-stu-id="38ea6-125">Then start the client application, and it will automatically load and use the pre-generated serializers at runtime.</span></span>
