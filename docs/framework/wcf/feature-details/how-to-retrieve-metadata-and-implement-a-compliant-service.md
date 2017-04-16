---
title: "Практическое руководство. Извлечение данных и реализация совместимой службы | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: f6f3a2b9-c8aa-4b0b-832c-ec2927bf1163
caps.latest.revision: 13
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 13
---
# Практическое руководство. Извлечение данных и реализация совместимой службы
Часто разработку и реализацию служб выполняют разные люди. В средах, в которых приложения с возможностью взаимодействия имеют большое значение, контракты можно разработать или описать на языке WSDL, и разработчик должен реализовать службу, соответствующую предоставляемому контракту. Также может возникнуть необходимость мигрировать существующую службу в [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] с сохранением формата подключения. Кроме того, дуплексные контракты требуют, чтобы вызывающие стороны также реализовывали контракт обратного вызова.  
  
 В этих случаях необходимо использовать [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) (или эквивалентное средство) для создания интерфейса контракта службы на управляемом языке, который можно реализовать для выполнения требований контракта. Обычно [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) используется для получения контракт службы, используемый с фабрикой каналов или [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] тип клиента, а также файл конфигурации клиента, который устанавливает правильную привязку и адрес. Чтобы использовать созданный файл конфигурации, следует изменить его на файл конфигурации службы. Также может возникнуть необходимость в изменении контракта службы.  
  
### <a name="to-retrieve-data-and-implement-a-compliant-service"></a>Извлечение данных и реализация совместимой службы  
  
1.  Используйте [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) для файлов метаданных или конечную точку метаданных для создания файла кода.  
  
2.  Найдите часть выходного файла кода, содержащий интерфейс (если имеется более одного), помеченный атрибутом <xref:System.ServiceModel.ServiceContractAttribute?displayProperty=fullName> атрибута. В следующем примере кода показаны два интерфейса, созданные [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md). Первый интерфейс (`ISampleService`) представляет собой интерфейс контракта службы, который реализуется, чтобы создать совместимую службу. Второй (`ISampleServiceChannel`) представляет собой вспомогательный интерфейс для использования клиентом, который расширяет и интерфейс контракта службы и <xref:System.ServiceModel.IClientChannel?displayProperty=fullName> и предназначен для использования в клиентском приложении.  
  
     [!code-csharp[ClientProxyCodeSample#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/clientproxycodesample/cs/proxycode.cs#2)]  
  
3.  Если в языке WSDL не указано ответное действие для всех операций, созданных контрактов операций может быть <xref:System.ServiceModel.OperationContractAttribute.ReplyAction%2A> свойство подстановочный знак (*). Удалите этот параметр свойства. В противном случае при реализации метаданных контракта службы метаданные невозможно будет экспортировать для этих операций.  
  
4.  Реализуйте интерфейс для класса и разместите службу. Пример см. в разделе [как: реализация контракта службы](../../../../docs/framework/wcf/how-to-implement-a-wcf-contract.md), или см. ниже в разделе пример простой реализации.  
  
5.  В конфигурации клиента, файл, [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) приводит к возникновению ошибки, измените [ <> \> ](../../../../docs/framework/configure-apps/file-schema/wcf/client.md) раздел конфигурации для [ <> \> ](../../../../docs/framework/configure-apps/file-schema/wcf/services.md) раздел конфигурации. (Пример созданного файла конфигурации клиентского приложения см. в следующем разделе "Пример".)  
  
6.  В [ <> \> ](../../../../docs/framework/configure-apps/file-schema/wcf/services.md) конфигурации создайте `name` атрибут в [ <> \> ](../../../../docs/framework/configure-apps/file-schema/wcf/services.md) раздел конфигурации для реализации службы.  
  
7.  Присвойте атрибуту `name` службы имя конфигурации для реализации службы.  
  
8.  Добавьте элементы конфигурации конечной точки, использующие реализованный контракт службы, в раздел конфигурации службы.  
  
## <a name="example"></a>Пример  
 В следующем примере кода показан файл кода, созданные при выполнении большинства [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) для файлов метаданных.  
  
 В коде демонстрируется следующее.  
  
-   Интерфейс контракта службы, который после реализации отвечает требованиям контракта (`ISampleService`).  
  
-   Вспомогательный интерфейс для использования клиентом, который расширяет и интерфейс контракта службы и <xref:System.ServiceModel.IClientChannel?displayProperty=fullName> и предназначен для использования в клиентском приложении (`ISampleServiceChannel`).  
  
-   Вспомогательный класс, который расширяет <xref:System.ServiceModel.ClientBase%601?displayProperty=fullName> и предназначен для использования в клиентском приложении (`SampleServiceClient`).  
  
-   Файл конфигурации, созданный из службы.  
  
-   Простая реализация службы `ISampleService`.  
  
-   Преобразование файла конфигурации на стороне клиента в версию на стороне службы.  
  
 [!code-csharp[ClientProxyCodeSample#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/clientproxycodesample/cs/proxycode.cs#1)]  
  
 [!code[ClientProxyCodeSample#10](../../../../samples/snippets/common/VS_Snippets_CFX/clientproxycodesample/common/client.exe.config#10)]
 [!code-csharp[ClientProxyCodeSample#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/clientproxycodesample/cs/client.exe.config#10)]  
  
 [!code-csharp[ClientProxyCodeSample#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/clientproxycodesample/cs/hostapplication.cs#5)]  
  
 [!code[ClientProxyCodeSample#20](../../../../samples/snippets/common/VS_Snippets_CFX/clientproxycodesample/common/hostapplication.exe.config#20)]
 [!code-csharp[ClientProxyCodeSample#20](../../../../samples/snippets/csharp/VS_Snippets_CFX/clientproxycodesample/cs/hostapplication.exe.config#20)]  
  
## <a name="see-also"></a>См. также  
 [Средство ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)