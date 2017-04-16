---
title: "Практическое руководство. Указание привязки клиента в конфигурации | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 4a7c79aa-50ee-4991-891e-adc0599323a7
caps.latest.revision: 11
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 11
---
# Практическое руководство. Указание привязки клиента в конфигурации
В этом примере создается клиентское консольное приложение, предназначенное для использования службы калькулятора, и привязка этого клиента задается декларативно в конфигурации. Клиент обращается к `CalculatorService`, который реализует `ICalculator` интерфейс, как служба и клиент используют <xref:System.ServiceModel.BasicHttpBinding> класса.  
  
 В приведенной процедуре предполагается, что служба калькулятора работает. Сведения о том, как построить службу см [как: Укажите привязку службы в конфигурации](../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md). Он также использует [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) , [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] для автоматического создания клиентских компонентов. Инструмент создает код и конфигурацию клиента для доступа к службе.  
  
 Клиент создается в два этапа. Программа Svcutil.exe генерирует класс `ClientCalculator`, реализующий интерфейс `ICalculator`. Затем данное клиентское приложение создается путем конструирования экземпляра класса `ClientCalculator`.  
  
 В большинстве случаев рекомендуется указывать привязку и адрес декларативно в конфигурации, а не принудительно в коде. Как правило, определять конечные точки в коде непрактично, поскольку привязки и адреса для развернутой службы чаще всего отличаются от привязок и адресов, используемых в процессе разработки службы. В общем случае, если не указывать привязку и адрес в коде, их можно изменять без повторной компиляции или повторного развертывания приложения.  
  
 Все перечисленные ниже этапы конфигурации можно выполнить с помощью [средство редактирования конфигурации (SvcConfigEditor.exe)](../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md).  
  
 Копию исходного кода в этом примере см. в разделе [basicbinding обеспечением](../../../docs/framework/wcf/samples/basicbinding.md) образца.  
  
### <a name="specifying-a-client-binding-in-configuration"></a>Указание привязки клиента в конфигурации  
  
1.  Из командной строки запустите программу Svcutil.exe, чтобы создать код из метаданных службы.  
  
    ```  
    Svcutil.exe <service's Metadata Exchange (MEX) address or HTTP GET address>   
    ```  
  
2.  Создаваемый клиент содержит интерфейс `ICalculator`, определяющий контракт службы, которому должна удовлетворять реализация клиента.  
  
     [!code-csharp[C_HowTo_ConfigureClientBinding#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_configureclientbinding/cs/generatedclient.cs#1)]
     [!code-csharp[C_HowTo_ConfigureClientBinding#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_configureclientbinding/cs/source.cs#1)]  
  
3.  Создаваемый клиент также содержит реализацию класса `ClientCalculator`.  
  
     [!code-csharp[C_HowTo_ConfigureClientBinding#2](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_configureclientbinding/cs/generatedclient.cs#2)]
     [!code-csharp[C_HowTo_ConfigureClientBinding#2](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_configureclientbinding/cs/source.cs#2)]  
  
4.  Svcutil.exe также создает конфигурацию для клиента, использующего <xref:System.ServiceModel.BasicHttpBinding> класса. При использовании среды [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] назовите этот файл App.config. Обратите внимание, что информация об адресе и привязке нигде внутри реализации службы не указывается. Кроме того, для извлечения этих сведений из файла конфигурации не требуется писать код.  
  
     [!code[C_HowTo_ConfigureClientBinding#100](../../../samples/snippets/common/VS_Snippets_CFX/c_howto_configureclientbinding/common/client.exe.config#100)]  
  
5.  Создайте экземпляр класса `ClientCalculator` в приложении, затем вызовите операции службы.  
  
     [!code-csharp[C_HowTo_ConfigureClientBinding#3](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_configureclientbinding/cs/client.cs#3)]  
  
6.  Скомпилируйте и запустите клиент.  
  
## <a name="see-also"></a>См. также  
 [Использование привязок для настройки служб и клиентов](../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)