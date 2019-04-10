---
title: Практическое руководство. Разработка расширения для ServiceContractGenerator
ms.date: 03/30/2017
ms.assetid: 876ca823-bd16-4bdf-9e0f-02092df90e51
ms.openlocfilehash: c9e10efccf0d51e6b78aace1296d227a78a9f91d
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2019
ms.locfileid: "59340624"
---
# <a name="how-to-write-an-extension-for-the-servicecontractgenerator"></a><span data-ttu-id="d804e-102">Практическое руководство. Разработка расширения для ServiceContractGenerator</span><span class="sxs-lookup"><span data-stu-id="d804e-102">How to: Write an Extension for the ServiceContractGenerator</span></span>
<span data-ttu-id="d804e-103">В этом разделе описывается, как разработать расширение для <xref:System.ServiceModel.Description.ServiceContractGenerator>.</span><span class="sxs-lookup"><span data-stu-id="d804e-103">This topic describes how to write an extension for the <xref:System.ServiceModel.Description.ServiceContractGenerator>.</span></span> <span data-ttu-id="d804e-104">Это можно сделать путем реализации интерфейса <xref:System.ServiceModel.Description.IOperationContractGenerationExtension> для поведения операции или интерфейса <xref:System.ServiceModel.Description.IServiceContractGenerationExtension> для поведения контракта.</span><span class="sxs-lookup"><span data-stu-id="d804e-104">This can be done by implementing the <xref:System.ServiceModel.Description.IOperationContractGenerationExtension> interface on an operation behavior or implementing the <xref:System.ServiceModel.Description.IServiceContractGenerationExtension> interface on a contract behavior.</span></span> <span data-ttu-id="d804e-105">Здесь показана реализация интерфейса <xref:System.ServiceModel.Description.IServiceContractGenerationExtension> для поведения контракта.</span><span class="sxs-lookup"><span data-stu-id="d804e-105">This topic shows how to implement the <xref:System.ServiceModel.Description.IServiceContractGenerationExtension> interface on a contract behavior.</span></span>  
  
 <span data-ttu-id="d804e-106"><xref:System.ServiceModel.Description.ServiceContractGenerator> создает контракты службы, типы клиента и конфигурации клиента из экземпляров <xref:System.ServiceModel.Description.ServiceEndpoint>, <xref:System.ServiceModel.Description.ContractDescription> и <xref:System.ServiceModel.Channels.Binding>.</span><span class="sxs-lookup"><span data-stu-id="d804e-106">The <xref:System.ServiceModel.Description.ServiceContractGenerator> generates service contracts, client types, and client configurations from <xref:System.ServiceModel.Description.ServiceEndpoint>, <xref:System.ServiceModel.Description.ContractDescription>, and <xref:System.ServiceModel.Channels.Binding> instances.</span></span> <span data-ttu-id="d804e-107">Как правило, экземпляры <xref:System.ServiceModel.Description.ServiceEndpoint>, <xref:System.ServiceModel.Description.ContractDescription> и <xref:System.ServiceModel.Channels.Binding> импортируются из метаданных службы, а затем используются для создания кода для вызова службы.</span><span class="sxs-lookup"><span data-stu-id="d804e-107">Typically, you import <xref:System.ServiceModel.Description.ServiceEndpoint>, <xref:System.ServiceModel.Description.ContractDescription>, and <xref:System.ServiceModel.Channels.Binding> instances from service metadata and then use these instances to generate code to call the service.</span></span> <span data-ttu-id="d804e-108">В данном примере реализация <xref:System.ServiceModel.Description.IWsdlImportExtension> используется для обработки заметок WSDL, а затем для добавления расширений создания кода в импортированные контракты для создания комментариев к сгенерированному коду.</span><span class="sxs-lookup"><span data-stu-id="d804e-108">In this example, an <xref:System.ServiceModel.Description.IWsdlImportExtension> implementation is used to process WSDL annotations and then add code generation extensions to the imported contracts to generate comments on the generated code.</span></span>  
  
### <a name="to-write-an-extension-for-the-servicecontractgenerator"></a><span data-ttu-id="d804e-109">Разработка расширения для ServiceContractGenerator</span><span class="sxs-lookup"><span data-stu-id="d804e-109">To write an extension for the ServiceContractGenerator</span></span>  
  
1. <span data-ttu-id="d804e-110">Реализуйте расширение <xref:System.ServiceModel.Description.IServiceContractGenerationExtension>.</span><span class="sxs-lookup"><span data-stu-id="d804e-110">Implement <xref:System.ServiceModel.Description.IServiceContractGenerationExtension>.</span></span> <span data-ttu-id="d804e-111">Чтобы изменить сгенерированный контракт службы, воспользуйтесь экземпляром <xref:System.ServiceModel.Description.ServiceContractGenerationContext>, переданным методу <xref:System.ServiceModel.Description.IServiceContractGenerationExtension.GenerateContract%28System.ServiceModel.Description.ServiceContractGenerationContext%29>.</span><span class="sxs-lookup"><span data-stu-id="d804e-111">To modify the generated service contract, use the <xref:System.ServiceModel.Description.ServiceContractGenerationContext> instance passed into the <xref:System.ServiceModel.Description.IServiceContractGenerationExtension.GenerateContract%28System.ServiceModel.Description.ServiceContractGenerationContext%29> method.</span></span>  
  
    ```  
    public void GenerateContract(ServiceContractGenerationContext context)  
    {  
        Console.WriteLine("In generate contract.");  
    context.ContractType.Comments.AddRange(Formatter.FormatComments(commentText));  
    }  
    ```  
  
2. <span data-ttu-id="d804e-112">Реализуйте расширение <xref:System.ServiceModel.Description.IWsdlImportExtension> в том же классе.</span><span class="sxs-lookup"><span data-stu-id="d804e-112">Implement <xref:System.ServiceModel.Description.IWsdlImportExtension> on the same class.</span></span> <span data-ttu-id="d804e-113">Метод <xref:System.ServiceModel.Description.IWsdlImportExtension.ImportContract%28System.ServiceModel.Description.WsdlImporter%2CSystem.ServiceModel.Description.WsdlContractConversionContext%29> может обработать определенное расширение WSDL (в данном случае заметки WSDL), добавив расширение создания кода в импортированный экземпляр <xref:System.ServiceModel.Description.ContractDescription>.</span><span class="sxs-lookup"><span data-stu-id="d804e-113">The <xref:System.ServiceModel.Description.IWsdlImportExtension.ImportContract%28System.ServiceModel.Description.WsdlImporter%2CSystem.ServiceModel.Description.WsdlContractConversionContext%29> method can process a specific WSDL extension (WSDL annotations in this case) by adding a code generation extension to the imported <xref:System.ServiceModel.Description.ContractDescription> instance.</span></span>  
  
    ```  
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
    ```  
  
3. <span data-ttu-id="d804e-114">Добавьте средство импорта WSDL в конфигурацию клиента.</span><span class="sxs-lookup"><span data-stu-id="d804e-114">Add the WSDL importer to your client configuration.</span></span>  
  
    ```xml  
    <metadata>  
      <wsdlImporters>  
        <extension type="Microsoft.WCF.Documentation.WsdlDocumentationImporter, WsdlDocumentation" />  
      </wsdlImporters>  
    </metadata>  
    ```  
  
4. <span data-ttu-id="d804e-115">Создайте объект `MetadataExchangeClient` и вызовите метод `GetMetadata` в коде клиента.</span><span class="sxs-lookup"><span data-stu-id="d804e-115">In the client code, create a `MetadataExchangeClient` and call `GetMetadata`.</span></span>  
  
    ```  
    MetadataExchangeClient mexClient = new MetadataExchangeClient(metadataAddress);  
    mexClient.ResolveMetadataReferences = true;  
    MetadataSet metaDocs = mexClient.GetMetadata();  
    ```  
  
5. <span data-ttu-id="d804e-116">Создайте объект `WsdlImporter` и вызовите метод `ImportAllContracts`.</span><span class="sxs-lookup"><span data-stu-id="d804e-116">Create a `WsdlImporter` and call `ImportAllContracts`.</span></span>  
  
    ```  
    WsdlImporter importer = new WsdlImporter(metaDocs);            System.Collections.ObjectModel.Collection<ContractDescription> contracts = importer.ImportAllContracts();  
    ```  
  
6. <span data-ttu-id="d804e-117">Создайте объект `ServiceContractGenerator` и вызовите метод `GenerateServiceContractType` для каждого контракта.</span><span class="sxs-lookup"><span data-stu-id="d804e-117">Create a `ServiceContractGenerator` and call `GenerateServiceContractType` for each contract.</span></span>  
  
    ```  
    ServiceContractGenerator generator = new ServiceContractGenerator();  
    foreach (ContractDescription contract in contracts)  
    {  
       generator.GenerateServiceContractType(contract);  
    }  
    if (generator.Errors.Count != 0)  
       throw new Exception("There were errors during code compilation.");  
    ```  
  
7. <xref:System.ServiceModel.Description.IServiceContractGenerationExtension.GenerateContract%28System.ServiceModel.Description.ServiceContractGenerationContext%29> <span data-ttu-id="d804e-118">вызывается автоматически для каждого поведения контракта, реализующего <xref:System.ServiceModel.Description.IServiceContractGenerationExtension>.</span><span class="sxs-lookup"><span data-stu-id="d804e-118">is called automatically for each contract behavior on a given contract that implements <xref:System.ServiceModel.Description.IServiceContractGenerationExtension>.</span></span> <span data-ttu-id="d804e-119">Затем этот метод может изменить передаваемый контекст <xref:System.ServiceModel.Description.ServiceContractGenerationContext>.</span><span class="sxs-lookup"><span data-stu-id="d804e-119">This method can then modify the <xref:System.ServiceModel.Description.ServiceContractGenerationContext> passed in.</span></span> <span data-ttu-id="d804e-120">В данном примере добавлены комментарии.</span><span class="sxs-lookup"><span data-stu-id="d804e-120">In this example comments are added.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d804e-121">См. также</span><span class="sxs-lookup"><span data-stu-id="d804e-121">See also</span></span>

- [<span data-ttu-id="d804e-122">Метаданные</span><span class="sxs-lookup"><span data-stu-id="d804e-122">Metadata</span></span>](../../../../docs/framework/wcf/feature-details/metadata.md)
- [<span data-ttu-id="d804e-123">Практическое руководство. Импорт пользовательской информации WSDL</span><span class="sxs-lookup"><span data-stu-id="d804e-123">How to: Import Custom WSDL</span></span>](../../../../docs/framework/wcf/extending/how-to-import-custom-wsdl.md)
