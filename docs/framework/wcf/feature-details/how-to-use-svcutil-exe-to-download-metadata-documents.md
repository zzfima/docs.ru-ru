---
title: Практическое руководство. Использование Svcutil.exe для загрузки документов метаданных
ms.date: 03/30/2017
ms.assetid: 15524274-3167-4627-b722-d6cedb9fa8c6
ms.openlocfilehash: 359cdb58ef65c9fb69c0ecfc759f70164a369cce
ms.sourcegitcommit: 09b4090b78f52fd09b0e430cd4b26576f1fdf96e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/17/2020
ms.locfileid: "76212104"
---
# <a name="how-to-use-svcutilexe-to-download-metadata-documents"></a><span data-ttu-id="17879-102">Практическое руководство. Использование Svcutil.exe для загрузки документов метаданных</span><span class="sxs-lookup"><span data-stu-id="17879-102">How to: Use Svcutil.exe to Download Metadata Documents</span></span>
<span data-ttu-id="17879-103">Средство Svcutil.exe позволяет загружать метаданные из выполняющихся служб и сохранять эти метаданные в локальных файлах.</span><span class="sxs-lookup"><span data-stu-id="17879-103">You can use Svcutil.exe to download metadata from running services and to save the metadata to local files.</span></span> <span data-ttu-id="17879-104">Для схем URL-адресов HTTP и HTTPS Svcutil. exe пытается получить метаданные с помощью WS-MetadataExchange и [обнаружения веб-службы XML](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/fxx6cfx2(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="17879-104">For HTTP and HTTPS URL schemes, Svcutil.exe attempts to retrieve metadata using WS-MetadataExchange and [XML Web Service Discovery](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/fxx6cfx2(v=vs.100)).</span></span> <span data-ttu-id="17879-105">Для всех остальных URL-схем средство Svcutil.exe использует только протокол WS-MetadataExchange.</span><span class="sxs-lookup"><span data-stu-id="17879-105">For all other URL schemes, Svcutil.exe uses only WS-MetadataExchange.</span></span>  
  
 <span data-ttu-id="17879-106">По умолчанию средство Svcutil.exe использует привязки, определенные в классе <xref:System.ServiceModel.Description.MetadataExchangeBindings>.</span><span class="sxs-lookup"><span data-stu-id="17879-106">By default, Svcutil.exe uses the bindings defined in the <xref:System.ServiceModel.Description.MetadataExchangeBindings> class.</span></span> <span data-ttu-id="17879-107">Чтобы настроить привязку, используемую для протокола WS-MetadataExchange, необходимо в файле конфигурации Svcutil.exe (svcutil.exe.config) настроить конечную точку клиента, которая бы использовала контракт `IMetadataExchange` и имя которой совпадало бы со схемой универсального кода ресурса (URI) адреса конечной точки метаданных.</span><span class="sxs-lookup"><span data-stu-id="17879-107">To configure the binding used for WS-MetadataExchange, you must define a client endpoint in the configuration file for Svcutil.exe (svcutil.exe.config) that uses the `IMetadataExchange` contract and that has the same name as the Uniform Resource Identifier (URI) scheme of the metadata endpoint address.</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="17879-108">При запуске программы Svcutil. exe для получения метаданных для службы, которая предоставляет два разных контракта службы, каждая из которых содержит операцию с одним и тем же именем, программа Svcutil. exe выводит сообщение об ошибке "не удается получить метаданные из...." Например, если у вас есть служба, которая предоставляет контракт службы с именем `ICarService`, который имеет операцию `Get(Car c)` и та же служба предоставляет контракт службы, именуемый `IBookService`, который имеет `Get(Book b)`операции.</span><span class="sxs-lookup"><span data-stu-id="17879-108">When running Svcutil.exe to get metadata for a service that exposes two different service contracts that each contain an operation of the same name, Svcutil.exe displays an error saying, "Cannot obtain Metadata from ...." For example, if you have a service that exposes a service contract called `ICarService` that has an operation `Get(Car c)` and the same service exposes a service contract called `IBookService` that has an operation `Get(Book b)`.</span></span> <span data-ttu-id="17879-109">Чтобы устранить эту проблему, выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="17879-109">To work around this issue, do one of the following:</span></span>
>
> - <span data-ttu-id="17879-110">Переименуйте одну из операций.</span><span class="sxs-lookup"><span data-stu-id="17879-110">Rename one of the operations.</span></span>
> - <span data-ttu-id="17879-111">Задайте другое имя в свойстве <xref:System.ServiceModel.OperationContractAttribute.Name%2A>.</span><span class="sxs-lookup"><span data-stu-id="17879-111">Set the <xref:System.ServiceModel.OperationContractAttribute.Name%2A> to a different name.</span></span>
> - <span data-ttu-id="17879-112">Установите другое пространство имен для одной из операций с помощью свойства <xref:System.ServiceModel.ServiceContractAttribute.Namespace%2A>.</span><span class="sxs-lookup"><span data-stu-id="17879-112">Set one of the operations' namespaces to a different namespace using the <xref:System.ServiceModel.ServiceContractAttribute.Namespace%2A> property.</span></span>
  
## <a name="to-download-metadata-using-svcutilexe"></a><span data-ttu-id="17879-113">Загрузка метаданных с помощью средства Svcutil.exe</span><span class="sxs-lookup"><span data-stu-id="17879-113">To download metadata using Svcutil.exe</span></span>  
  
1. <span data-ttu-id="17879-114">Найдите средство Svcutil.exe в следующей папке:</span><span class="sxs-lookup"><span data-stu-id="17879-114">Locate the Svcutil.exe tool at the following location:</span></span>  
  
     <span data-ttu-id="17879-115">C:\Program Files\Microsoft SDKs\Windows\v1.0.\bin</span><span class="sxs-lookup"><span data-stu-id="17879-115">C:\Program Files\Microsoft SDKs\Windows\v1.0.\bin</span></span>  
  
2. <span data-ttu-id="17879-116">Из командной строки запустите средство, используя следующий формат.</span><span class="sxs-lookup"><span data-stu-id="17879-116">At the command prompt, launch the tool using the following format.</span></span>  
  
    ```console
    svcutil.exe /t:metadata  <url>* | <epr>  
    ```  
  
     <span data-ttu-id="17879-117">Параметр `/t:metadata` необходимо указать, чтобы загружались метаданные.</span><span class="sxs-lookup"><span data-stu-id="17879-117">You must specify the `/t:metadata` option to download metadata.</span></span> <span data-ttu-id="17879-118">В противном случае будут созданы код и конфигурация клиента.</span><span class="sxs-lookup"><span data-stu-id="17879-118">Otherwise, client code and configuration are generated.</span></span>  
  
3. <span data-ttu-id="17879-119">Аргумент <`url`> указывает URL-адрес конечной точки службы, предоставляющей метаданные, или документ метаданных, размещенный в сети.</span><span class="sxs-lookup"><span data-stu-id="17879-119">The <`url`>argument specifies the URL to a service endpoint that provides metadata or to a metadata document hosted online.</span></span> <span data-ttu-id="17879-120">Аргумент <`epr`> указывает путь к XML-файлу, который содержит `EndpointAddress` WS-Addressing для конечной точки службы, которая поддерживает WS-MetadataExchange.</span><span class="sxs-lookup"><span data-stu-id="17879-120">The <`epr`> argument specifies the path to an XML file that contains a WS-Addressing `EndpointAddress` for a service endpoint that supports WS-MetadataExchange.</span></span>  
  
 <span data-ttu-id="17879-121">Дополнительные сведения об использовании этого средства для скачивания метаданных см. в разделе [средство служебной программы метаданных ServiceModel (Svcutil. exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span><span class="sxs-lookup"><span data-stu-id="17879-121">For more options about using this tool for metadata download, see [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="17879-122">Пример</span><span class="sxs-lookup"><span data-stu-id="17879-122">Example</span></span>  
 <span data-ttu-id="17879-123">Следующая команда позволяет загрузить документы с метаданными из выполняющейся службы.</span><span class="sxs-lookup"><span data-stu-id="17879-123">The following command downloads metadata documents from a running service.</span></span>  
  
```console
svcutil /t:metadata http://service/metadataEndpoint  
```  
  
## <a name="see-also"></a><span data-ttu-id="17879-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="17879-124">See also</span></span>

- [<span data-ttu-id="17879-125">Служебная программа для метаданных ServiceModel (Svcutil.exe)</span><span class="sxs-lookup"><span data-stu-id="17879-125">ServiceModel Metadata Utility Tool (Svcutil.exe)</span></span>](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)
