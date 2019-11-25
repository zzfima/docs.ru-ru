---
title: Практическое руководство. Импорт пользовательской информации WSDL
ms.date: 03/30/2017
ms.assetid: ddc3718d-ce60-44f6-92af-a5c67477dd99
ms.openlocfilehash: 10fc3282560d35e61044a367f8172571096d76bd
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/12/2019
ms.locfileid: "73975890"
---
# <a name="how-to-import-custom-wsdl"></a>Практическое руководство. Импорт пользовательской информации WSDL
В этом разделе описывается, как импортировать пользовательский код WSDL. Для работы с пользовательским кодом WSDL необходимо реализовать интерфейс <xref:System.ServiceModel.Description.IWsdlImportExtension>.  
  
### <a name="to-import-custom-wsdl"></a>Импорт пользовательского кода WSDL  
  
1. Реализуйте расширение <xref:System.ServiceModel.Description.IWsdlImportExtension>. Реализуйте метод <xref:System.ServiceModel.Description.IWsdlImportExtension.BeforeImport%28System.Web.Services.Description.ServiceDescriptionCollection%2CSystem.Xml.Schema.XmlSchemaSet%2CSystem.Collections.Generic.ICollection%7BSystem.Xml.XmlElement%7D%29>, чтобы он изменял метаданные перед их импортом. Реализуйте методы <xref:System.ServiceModel.Description.IWsdlImportExtension.ImportEndpoint%28System.ServiceModel.Description.WsdlImporter%2CSystem.ServiceModel.Description.WsdlEndpointConversionContext%29> и <xref:System.ServiceModel.Description.IWsdlImportExtension.ImportContract%28System.ServiceModel.Description.WsdlImporter%2CSystem.ServiceModel.Description.WsdlContractConversionContext%29>, чтобы они изменяли контракты и конечные точки, импортированные из метаданных. Чтобы обратиться к импортированному контракту или конечной точке, следует использовать соответствующий объект контекста (<xref:System.ServiceModel.Description.WsdlContractConversionContext> или <xref:System.ServiceModel.Description.WsdlEndpointConversionContext>):  
  
    ```csharp
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
  
2. Настройте клиентское приложение, чтобы оно использовало пользовательский импортер WSDL. Обратите внимание, что при использовании средства Svcutil.exe соответствующие параметры необходимо задать в файле конфигурации этого средства (Svcutil.exe.config):  
  
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
  
3. Создайте новый экземпляр <xref:System.ServiceModel.Description.WsdlImporter> (передав ему экземпляр <xref:System.ServiceModel.Description.MetadataSet>, содержащий документы WSDL, которые требуется импортировать) и вызовите метод <xref:System.ServiceModel.Description.WsdlImporter.ImportAllContracts%2A>:  
  
    ```csharp
    WsdlImporter importer = new WsdlImporter(metaDocs);
    System.Collections.ObjectModel.Collection<ContractDescription> contracts = importer.ImportAllContracts();  
    ```  
  
## <a name="see-also"></a>См. также

- [Метаданные](../feature-details/metadata.md)
- [Экспорт и импорт метаданных](../feature-details/exporting-and-importing-metadata.md)
- [Пользовательская публикация WSDL](../samples/custom-wsdl-publication.md)
