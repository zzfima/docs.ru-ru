---
title: Как выполнить Импорт пользовательского языка WSDL
ms.date: 03/30/2017
ms.assetid: ddc3718d-ce60-44f6-92af-a5c67477dd99
ms.openlocfilehash: dba3ec52d03939a306709e7756ff4e801699cf38
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54575610"
---
# <a name="how-to-import-custom-wsdl"></a><span data-ttu-id="7747a-102">Как выполнить Импорт пользовательского языка WSDL</span><span class="sxs-lookup"><span data-stu-id="7747a-102">How to: Import Custom WSDL</span></span>
<span data-ttu-id="7747a-103">В этом разделе описывается, как импортировать пользовательский код WSDL.</span><span class="sxs-lookup"><span data-stu-id="7747a-103">This topic describes how to import custom WSDL.</span></span> <span data-ttu-id="7747a-104">Для работы с пользовательским кодом WSDL необходимо реализовать интерфейс <xref:System.ServiceModel.Description.IWsdlImportExtension>.</span><span class="sxs-lookup"><span data-stu-id="7747a-104">To handle the custom WSDL, you must implement the <xref:System.ServiceModel.Description.IWsdlImportExtension> interface.</span></span>  
  
### <a name="to-import-custom-wsdl"></a><span data-ttu-id="7747a-105">Импорт пользовательского кода WSDL</span><span class="sxs-lookup"><span data-stu-id="7747a-105">To import custom WSDL</span></span>  
  
1.  <span data-ttu-id="7747a-106">Реализуйте расширение <xref:System.ServiceModel.Description.IWsdlImportExtension>.</span><span class="sxs-lookup"><span data-stu-id="7747a-106">Implement <xref:System.ServiceModel.Description.IWsdlImportExtension>.</span></span> <span data-ttu-id="7747a-107">Реализуйте метод <xref:System.ServiceModel.Description.IWsdlImportExtension.BeforeImport%28System.Web.Services.Description.ServiceDescriptionCollection%2CSystem.Xml.Schema.XmlSchemaSet%2CSystem.Collections.Generic.ICollection%7BSystem.Xml.XmlElement%7D%29>, чтобы он изменял метаданные перед их импортом.</span><span class="sxs-lookup"><span data-stu-id="7747a-107">Implement the <xref:System.ServiceModel.Description.IWsdlImportExtension.BeforeImport%28System.Web.Services.Description.ServiceDescriptionCollection%2CSystem.Xml.Schema.XmlSchemaSet%2CSystem.Collections.Generic.ICollection%7BSystem.Xml.XmlElement%7D%29> method to modify the metadata before it is imported.</span></span> <span data-ttu-id="7747a-108">Реализуйте методы <xref:System.ServiceModel.Description.IWsdlImportExtension.ImportEndpoint%28System.ServiceModel.Description.WsdlImporter%2CSystem.ServiceModel.Description.WsdlEndpointConversionContext%29> и <xref:System.ServiceModel.Description.IWsdlImportExtension.ImportContract%28System.ServiceModel.Description.WsdlImporter%2CSystem.ServiceModel.Description.WsdlContractConversionContext%29>, чтобы они изменяли контракты и конечные точки, импортированные из метаданных.</span><span class="sxs-lookup"><span data-stu-id="7747a-108">Implement the <xref:System.ServiceModel.Description.IWsdlImportExtension.ImportEndpoint%28System.ServiceModel.Description.WsdlImporter%2CSystem.ServiceModel.Description.WsdlEndpointConversionContext%29> and <xref:System.ServiceModel.Description.IWsdlImportExtension.ImportContract%28System.ServiceModel.Description.WsdlImporter%2CSystem.ServiceModel.Description.WsdlContractConversionContext%29> methods to modify contracts and endpoints imported from the metadata.</span></span> <span data-ttu-id="7747a-109">Чтобы обратиться к импортированному контракту или конечной точке, следует использовать соответствующий объект контекста (<xref:System.ServiceModel.Description.WsdlContractConversionContext> или <xref:System.ServiceModel.Description.WsdlEndpointConversionContext>):</span><span class="sxs-lookup"><span data-stu-id="7747a-109">To access the imported contract or endpoint, use the corresponding context object (<xref:System.ServiceModel.Description.WsdlContractConversionContext> or <xref:System.ServiceModel.Description.WsdlEndpointConversionContext>):</span></span>  
  
    ```  
    public class WsdlDocumentationImporter : IWsdlImportExtension  
       {  
          public void ImportContract(WsdlImporter importer, WsdlContractConversionContext context)  
    {  
            // Contract documentation  
         if (context.WsdlPortType.Documentation != null)  
         {  
               context.Contract.Behaviors.Add(new WsdlDocumentationImporter(context.WsdlPortType.Documentation));  
    }  
    // Operation documentation  
    foreach (Operation operation in context.WsdlPortType.Operations)  
    {  
    if (operation.Documentation != null)  
    {  
    OperationDescription operationDescription = context.Contract.Operations.Find(operation.Name);  
    if (operationDescription != null)  
    {  
                            operationDescription.Behaviors.Add(new WsdlDocumentationImporter(operation.Documentation));  
    }  
    }  
    }  
    }  
  
    public void BeforeImport(ServiceDescriptionCollection wsdlDocuments, XmlSchemaSet xmlSchemas, ICollection<XmlElement> policy)   
            {  
                Console.WriteLine("BeforeImport called.");  
            }  
  
    public void ImportEndpoint(WsdlImporter importer, WsdlEndpointConversionContext context)   
            {  
                Console.WriteLine("ImportEndpoint called.");  
            }  
       }  
    ```  
  
2.  <span data-ttu-id="7747a-110">Настройте клиентское приложение, чтобы оно использовало пользовательский импортер WSDL.</span><span class="sxs-lookup"><span data-stu-id="7747a-110">Configure the client application to use the custom WSDL importer.</span></span> <span data-ttu-id="7747a-111">Обратите внимание, что при использовании средства Svcutil.exe соответствующие параметры необходимо задать в файле конфигурации этого средства (Svcutil.exe.config):</span><span class="sxs-lookup"><span data-stu-id="7747a-111">Note that if you are using Svcutil.exe, you should add this configuration to the configuration file for Svcutil.exe (Svcutil.exe.config):</span></span>  
  
    ```xml  
    <system.serviceModel>  
          <client>  
            <endpoint   
              address="http://localhost:8000/Fibonacci"   
              binding="wsHttpBinding"  
              contract="IFibonacci"  
            />  
            <metadata>  
              <wsdlImporters>  
                <extension type="Microsoft.WCF.Documentation.WsdlDocumentationImporter, WsdlDocumentation" />  
              </wsdlImporters>  
            </metadata>  
          </client>  
        </system.serviceModel>  
    ```  
  
3.  <span data-ttu-id="7747a-112">Создайте новый экземпляр <xref:System.ServiceModel.Description.WsdlImporter> (передав ему экземпляр <xref:System.ServiceModel.Description.MetadataSet>, содержащий документы WSDL, которые требуется импортировать) и вызовите метод <xref:System.ServiceModel.Description.WsdlImporter.ImportAllContracts%2A>:</span><span class="sxs-lookup"><span data-stu-id="7747a-112">Create a new <xref:System.ServiceModel.Description.WsdlImporter> instance (passing in the <xref:System.ServiceModel.Description.MetadataSet> instance that contains the WSDL documents that you want to import), and call <xref:System.ServiceModel.Description.WsdlImporter.ImportAllContracts%2A>:</span></span>  
  
    ```  
    WsdlImporter importer = new WsdlImporter(metaDocs);          System.Collections.ObjectModel.Collection<ContractDescription> contracts  = importer.ImportAllContracts();  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="7747a-113">См. также</span><span class="sxs-lookup"><span data-stu-id="7747a-113">See also</span></span>
- [<span data-ttu-id="7747a-114">Метаданные</span><span class="sxs-lookup"><span data-stu-id="7747a-114">Metadata</span></span>](../../../../docs/framework/wcf/feature-details/metadata.md)
- [<span data-ttu-id="7747a-115">Экспорт и импорт метаданных</span><span class="sxs-lookup"><span data-stu-id="7747a-115">Exporting and Importing Metadata</span></span>](../../../../docs/framework/wcf/feature-details/exporting-and-importing-metadata.md)
- [<span data-ttu-id="7747a-116">Пользовательская публикация WSDL</span><span class="sxs-lookup"><span data-stu-id="7747a-116">Custom WSDL Publication</span></span>](../../../../docs/framework/wcf/samples/custom-wsdl-publication.md)
