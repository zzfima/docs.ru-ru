---
title: Практическое руководство. Извлечение данных и реализация совместимой службы
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f6f3a2b9-c8aa-4b0b-832c-ec2927bf1163
caps.latest.revision: ''
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: ac7654fa041688bbd703d564f6703df9671fbaea
ms.sourcegitcommit: c883637b41ee028786edceece4fa872939d2e64c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/26/2018
---
# <a name="how-to-retrieve-metadata-and-implement-a-compliant-service"></a>Практическое руководство. Извлечение данных и реализация совместимой службы
Часто разработку и реализацию служб выполняют разные люди. В средах, в которых приложения с возможностью взаимодействия имеют большое значение, контракты можно разработать или описать на языке WSDL, и разработчик должен реализовать службу, соответствующую предоставляемому контракту. Также может возникнуть необходимость мигрировать существующую службу в [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] с сохранением формата подключения. Кроме того, дуплексные контракты требуют, чтобы вызывающие стороны также реализовывали контракт обратного вызова.  
  
 В этих случаях необходимо использовать [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) (или аналогичный инструмент) для создания интерфейса контракта службы на управляемом языке, который можно реализовать для выполнения требований контракт. Обычно [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) используется для получения контракта службы, который используется с фабрикой каналов или [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] а также файл конфигурации клиента, который устанавливает тип клиента правильную привязку и адрес. Чтобы использовать созданный файл конфигурации, следует изменить его на файл конфигурации службы. Также может возникнуть необходимость в изменении контракта службы.  
  
### <a name="to-retrieve-data-and-implement-a-compliant-service"></a>Извлечение данных и реализация совместимой службы  
  
1.  Используйте [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) от файлов метаданных или конечную точку метаданных для создания файла кода.  
  
2.  Найдите часть выходного файла кода, содержащую требуемый интерфейс (если имеется более одного), отмеченный атрибутом <xref:System.ServiceModel.ServiceContractAttribute?displayProperty=nameWithType>. В следующем примере кода показаны два интерфейса, созданные [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md). Первый интерфейс (`ISampleService`) представляет собой интерфейс контракта службы, который реализуется, чтобы создать совместимую службу. Второй интерфейс (`ISampleServiceChannel`) представляет собой вспомогательный интерфейс, используемый для клиентов и расширяющий как интерфейс контракта службы, так и канал <xref:System.ServiceModel.IClientChannel?displayProperty=nameWithType>, и используется в клиентском приложении.  
  
     [!code-csharp[ClientProxyCodeSample#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/clientproxycodesample/cs/proxycode.cs#2)]  
  
3.  Если в языке WSDL не указано ответное действие для всех операций, свойству <xref:System.ServiceModel.OperationContractAttribute.ReplyAction%2A> созданных контрактов операций может быть присвоено значение подстановочного знака (*). Удалите этот параметр свойства. В противном случае при реализации метаданных контракта службы метаданные невозможно будет экспортировать для этих операций.  
  
4.  Реализуйте интерфейс для класса и разместите службу. Пример см. в разделе [как: реализация контракта службы](../../../../docs/framework/wcf/how-to-implement-a-wcf-contract.md), или в разделе простая реализация ниже в разделе "Пример".  
  
5.  Файл, который в конфигурации клиента [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) приводит к возникновению ошибки, измените [ \<клиента >](../../../../docs/framework/configure-apps/file-schema/wcf/client.md) раздел конфигурации для [ \<services >](../../../../docs/framework/configure-apps/file-schema/wcf/services.md) раздел конфигурации. (Пример созданного файла конфигурации клиентского приложения см. в следующем разделе "Пример".)  
  
6.  В пределах [ \<службы >](../../../../docs/framework/configure-apps/file-schema/wcf/services.md) конфигурации создайте `name` атрибута в [ \<службы >](../../../../docs/framework/configure-apps/file-schema/wcf/services.md) раздел конфигурации для службы Реализация.  
  
7.  Присвойте атрибуту `name` службы имя конфигурации для реализации службы.  
  
8.  Добавьте элементы конфигурации конечной точки, использующие реализованный контракт службы, в раздел конфигурации службы.  
  
## <a name="example"></a>Пример  
 В следующем примере кода показано, большая часть файла кода, созданные при выполнении [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) файлов метаданных.  
  
 В коде демонстрируется следующее.  
  
-   Интерфейс контракта службы, который после реализации отвечает требованиям контракта (`ISampleService`).  
  
-   Вспомогательный интерфейс, используемый для клиентов и расширяющий как интерфейс контракта службы, так и канал <xref:System.ServiceModel.IClientChannel?displayProperty=nameWithType>. Этот интерфейс используется в клиентском приложении (`ISampleServiceChannel`).  
  
-   Вспомогательный класс, расширяющий класс <xref:System.ServiceModel.ClientBase%601?displayProperty=nameWithType> и используемый в клиентском приложении (`SampleServiceClient`).  
  
-   Файл конфигурации, созданный из службы.  
  
-   Простая реализация службы `ISampleService`.  
  
-   Преобразование файла конфигурации на стороне клиента в версию на стороне службы.  
  
 [!code-csharp[ClientProxyCodeSample#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/clientproxycodesample/cs/proxycode.cs#1)]    
 [!code-xml[ClientProxyCodeSample#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/clientproxycodesample/cs/client.exe.config#10)]     
 [!code-csharp[ClientProxyCodeSample#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/clientproxycodesample/cs/hostapplication.cs#5)]    
 [!code-xml[ClientProxyCodeSample#20](../../../../samples/snippets/csharp/VS_Snippets_CFX/clientproxycodesample/cs/hostapplication.exe.config#20)]    
  
## <a name="see-also"></a>См. также  
 [Служебная программа для метаданных ServiceModel (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)
