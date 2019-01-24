---
title: Как выполнить Использование Svcutil.exe для загрузки документов метаданных
ms.date: 03/30/2017
ms.assetid: 15524274-3167-4627-b722-d6cedb9fa8c6
ms.openlocfilehash: dc3a1d402a9f6ffb69c1f692800698609f9fa84b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54603278"
---
# <a name="how-to-use-svcutilexe-to-download-metadata-documents"></a><span data-ttu-id="59c7e-102">Как выполнить Использование Svcutil.exe для загрузки документов метаданных</span><span class="sxs-lookup"><span data-stu-id="59c7e-102">How to: Use Svcutil.exe to Download Metadata Documents</span></span>
<span data-ttu-id="59c7e-103">Средство Svcutil.exe позволяет загружать метаданные из выполняющихся служб и сохранять эти метаданные в локальных файлах.</span><span class="sxs-lookup"><span data-stu-id="59c7e-103">You can use Svcutil.exe to download metadata from running services and to save the metadata to local files.</span></span> <span data-ttu-id="59c7e-104">Для схем HTTP и HTTPS URL-адрес Svcutil.exe предпринимает попытку извлечь метаданные с помощью WS-MetadataExchange и [обнаружение веб-служб XML](https://go.microsoft.com/fwlink/?LinkId=94950).</span><span class="sxs-lookup"><span data-stu-id="59c7e-104">For HTTP and HTTPS URL schemes, Svcutil.exe attempts to retrieve metadata using WS-MetadataExchange and [XML Web Service Discovery](https://go.microsoft.com/fwlink/?LinkId=94950).</span></span> <span data-ttu-id="59c7e-105">Для всех остальных URL-схем средство Svcutil.exe использует только протокол WS-MetadataExchange.</span><span class="sxs-lookup"><span data-stu-id="59c7e-105">For all other URL schemes, Svcutil.exe uses only WS-MetadataExchange.</span></span>  
  
 <span data-ttu-id="59c7e-106">По умолчанию средство Svcutil.exe использует привязки, определенные в классе <xref:System.ServiceModel.Description.MetadataExchangeBindings>.</span><span class="sxs-lookup"><span data-stu-id="59c7e-106">By default, Svcutil.exe uses the bindings defined in the <xref:System.ServiceModel.Description.MetadataExchangeBindings> class.</span></span> <span data-ttu-id="59c7e-107">Чтобы настроить привязку, используемую для протокола WS-MetadataExchange, необходимо в файле конфигурации Svcutil.exe (svcutil.exe.config) настроить конечную точку клиента, которая бы использовала контракт `IMetadataExchange` и имя которой совпадало бы со схемой универсального кода ресурса (URI) адреса конечной точки метаданных.</span><span class="sxs-lookup"><span data-stu-id="59c7e-107">To configure the binding used for WS-MetadataExchange, you must define a client endpoint in the configuration file for Svcutil.exe (svcutil.exe.config) that uses the `IMetadataExchange` contract and that has the same name as the Uniform Resource Identifier (URI) scheme of the metadata endpoint address.</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="59c7e-108">При запуске Svcutil.exe получить метаданные для службы, которая предоставляет две разные службы контрактов, что каждый содержат операции с тем же именем, Svcutil.exe выводит сообщение об ошибке говорит: «Не удается получить метаданные из...» Например, если у вас есть службы, которая предоставляет контракт службы с именем `ICarService` , содержащий операцию `Get(Car c)` и той же службы предоставляет доступ к контракту службы с именем `IBookService` , содержащий операцию `Get(Book b)`.</span><span class="sxs-lookup"><span data-stu-id="59c7e-108">When running Svcutil.exe to get metadata for a service that exposes two different service contracts that each contain an operation of the same name, Svcutil.exe displays an error saying, "Cannot obtain Metadata from ...." For example, if you have a service that exposes a service contract called `ICarService` that has an operation `Get(Car c)` and the same service exposes a service contract called `IBookService` that has an operation `Get(Book b)`.</span></span> <span data-ttu-id="59c7e-109">Чтобы устранить эту проблему, выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="59c7e-109">To work around this issue, do one of the following:</span></span>
>
> - <span data-ttu-id="59c7e-110">Переименуйте одну из операций.</span><span class="sxs-lookup"><span data-stu-id="59c7e-110">Rename one of the operations.</span></span>
> - <span data-ttu-id="59c7e-111">Задайте другое имя в свойстве <xref:System.ServiceModel.OperationContractAttribute.Name%2A>.</span><span class="sxs-lookup"><span data-stu-id="59c7e-111">Set the <xref:System.ServiceModel.OperationContractAttribute.Name%2A> to a different name.</span></span>
> - <span data-ttu-id="59c7e-112">Установите другое пространство имен для одной из операций с помощью свойства <xref:System.ServiceModel.ServiceContractAttribute.Namespace%2A>.</span><span class="sxs-lookup"><span data-stu-id="59c7e-112">Set one of the operations' namespaces to a different namespace using the <xref:System.ServiceModel.ServiceContractAttribute.Namespace%2A> property.</span></span>
  
## <a name="to-download-metadata-using-svcutilexe"></a><span data-ttu-id="59c7e-113">Загрузка метаданных с помощью средства Svcutil.exe</span><span class="sxs-lookup"><span data-stu-id="59c7e-113">To download metadata using Svcutil.exe</span></span>  
  
1.  <span data-ttu-id="59c7e-114">Найдите средство Svcutil.exe в следующей папке:</span><span class="sxs-lookup"><span data-stu-id="59c7e-114">Locate the Svcutil.exe tool at the following location:</span></span>  
  
     <span data-ttu-id="59c7e-115">C:\Program Files\Microsoft SDKs\Windows\v1.0.\bin</span><span class="sxs-lookup"><span data-stu-id="59c7e-115">C:\Program Files\Microsoft SDKs\Windows\v1.0.\bin</span></span>  
  
2.  <span data-ttu-id="59c7e-116">Из командной строки запустите средство, используя следующий формат.</span><span class="sxs-lookup"><span data-stu-id="59c7e-116">At the command prompt, launch the tool using the following format.</span></span>  
  
    ```  
    svcutil.exe /t:metadata  <url>* | <epr>  
    ```  
  
     <span data-ttu-id="59c7e-117">Параметр `/t:metadata` необходимо указать, чтобы загружались метаданные.</span><span class="sxs-lookup"><span data-stu-id="59c7e-117">You must specify the `/t:metadata` option to download metadata.</span></span> <span data-ttu-id="59c7e-118">В противном случае будут созданы код и конфигурация клиента.</span><span class="sxs-lookup"><span data-stu-id="59c7e-118">Otherwise, client code and configuration are generated.</span></span>  
  
3.  <span data-ttu-id="59c7e-119"><`url`> Аргумент задает URL-адрес конечной точки службы, которая предоставляет метаданные или документ метаданных, размещенного в сети.</span><span class="sxs-lookup"><span data-stu-id="59c7e-119">The <`url`>argument specifies the URL to a service endpoint that provides metadata or to a metadata document hosted online.</span></span> <span data-ttu-id="59c7e-120"><`epr`> Аргумент задает путь к XML-файл, содержащий WS-Addressing `EndpointAddress` для конечной точки службы, поддерживающей протокол WS-MetadataExchange.</span><span class="sxs-lookup"><span data-stu-id="59c7e-120">The <`epr`> argument specifies the path to an XML file that contains a WS-Addressing `EndpointAddress` for a service endpoint that supports WS-MetadataExchange.</span></span>  
  
 <span data-ttu-id="59c7e-121">Дополнительные сведения об использовании этого средства для загрузки метаданных, см. в разделе [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span><span class="sxs-lookup"><span data-stu-id="59c7e-121">For more options about using this tool for metadata download, see [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="59c7e-122">Пример</span><span class="sxs-lookup"><span data-stu-id="59c7e-122">Example</span></span>  
 <span data-ttu-id="59c7e-123">Следующая команда позволяет загрузить документы с метаданными из выполняющейся службы.</span><span class="sxs-lookup"><span data-stu-id="59c7e-123">The following command downloads metadata documents from a running service.</span></span>  
  
```  
svcutil /t:metadata http://service/metadataEndpoint  
```  
  
## <a name="see-also"></a><span data-ttu-id="59c7e-124">См. также</span><span class="sxs-lookup"><span data-stu-id="59c7e-124">See also</span></span>
- [<span data-ttu-id="59c7e-125">Служебная программа для метаданных ServiceModel (Svcutil.exe)</span><span class="sxs-lookup"><span data-stu-id="59c7e-125">ServiceModel Metadata Utility Tool (Svcutil.exe)</span></span>](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)
