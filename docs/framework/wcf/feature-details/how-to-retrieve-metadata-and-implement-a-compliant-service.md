---
title: Практическое руководство. Извлечение данных и реализация совместимой службы
ms.date: 03/30/2017
ms.assetid: f6f3a2b9-c8aa-4b0b-832c-ec2927bf1163
ms.openlocfilehash: 0a13d504b1c7c38ec13fee58c36913a75119271b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184862"
---
# <a name="how-to-retrieve-metadata-and-implement-a-compliant-service"></a>Практическое руководство. Извлечение данных и реализация совместимой службы
Часто разработку и реализацию служб выполняют разные люди. В средах, в которых приложения с возможностью взаимодействия имеют большое значение, контракты можно разработать или описать на языке WSDL, и разработчик должен реализовать службу, соответствующую предоставляемому контракту. Вы также можете перенести существующую службу в Фонд связи Windows (WCF), но сохранить формат провода. Кроме того, дуплексные контракты требуют, чтобы вызывающие стороны также реализовывали контракт обратного вызова.  
  
 В этих случаях необходимо использовать [инструмент Utility Tool ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) (или эквивалентный инструмент) для создания интерфейса сервисного контракта на управляемом языке, который можно реализовать для выполнения требований контракта. Обычно [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) используется для приобретения сервисного контракта, который используется с фабрикой каналов или типом клиента WCF, а также с файлом конфигурации клиента, который устанавливает правильную привязку и адрес. Чтобы использовать созданный файл конфигурации, следует изменить его на файл конфигурации службы. Также может возникнуть необходимость в изменении контракта службы.  
  
### <a name="to-retrieve-data-and-implement-a-compliant-service"></a>Извлечение данных и реализация совместимой службы  
  
1. Используйте [инструмент Utility Tool ServiceModel Metadata (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) против файлов метаданных или конечную точку метаданных для создания файла кода.  
  
2. Найдите часть выходного файла кода, содержащую требуемый интерфейс (если имеется более одного), отмеченный атрибутом <xref:System.ServiceModel.ServiceContractAttribute?displayProperty=nameWithType>. Следующий пример кода показывает два интерфейса, генерируемых [ServiceModel Metadata Utility Tool (Svcutil.exe).](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) Первый интерфейс (`ISampleService`) представляет собой интерфейс контракта службы, который реализуется, чтобы создать совместимую службу. Второй интерфейс (`ISampleServiceChannel`) представляет собой вспомогательный интерфейс, используемый для клиентов и расширяющий как интерфейс контракта службы, так и канал <xref:System.ServiceModel.IClientChannel?displayProperty=nameWithType>, и используется в клиентском приложении.  
  
     [!code-csharp[ClientProxyCodeSample#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/clientproxycodesample/cs/proxycode.cs#2)]  
  
3. Если в языке WSDL не указано ответное действие для всех операций, свойству <xref:System.ServiceModel.OperationContractAttribute.ReplyAction%2A> созданных контрактов операций может быть присвоено значение подстановочного знака (*). Удалите этот параметр свойства. В противном случае при реализации метаданных контракта службы метаданные невозможно будет экспортировать для этих операций.  
  
4. Реализуйте интерфейс для класса и разместите службу. Например, [см. Как: Реализация контракта на обслуживание](../../../../docs/framework/wcf/how-to-implement-a-wcf-contract.md)или простое выполнение ниже в разделе Пример.  
  
5. В файле конфигурации клиента, генерируемом утилитой [ServiceModel Metadata Tool (Svcutil.exe),](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) изменяйте раздел [ \<конфигурации клиента>](../../../../docs/framework/configure-apps/file-schema/wcf/client.md) на раздел [ \<конфигурации службы>](../../../../docs/framework/configure-apps/file-schema/wcf/services.md) конфигурации. (Пример созданного файла конфигурации клиентского приложения см. в следующем разделе "Пример".)  
  
6. В разделе [ \<конфигурации службы>](../../../../docs/framework/configure-apps/file-schema/wcf/services.md) создать `name` атрибут в разделе [ \<конфигурации>службы](../../../../docs/framework/configure-apps/file-schema/wcf/services.md) для реализации службы.  
  
7. Присвойте атрибуту `name` службы имя конфигурации для реализации службы.  
  
8. Добавьте элементы конфигурации конечной точки, использующие реализованный контракт службы, в раздел конфигурации службы.  
  
## <a name="example"></a>Пример  
 Следующий пример кода показывает большую часть файла кода, генерируемого запуском [инструмента ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) против файлов метаданных.  
  
 В коде демонстрируется следующее.  
  
- Интерфейс контракта службы, который после реализации отвечает требованиям контракта (`ISampleService`).  
  
- Вспомогательный интерфейс, используемый для клиентов и расширяющий как интерфейс контракта службы, так и канал <xref:System.ServiceModel.IClientChannel?displayProperty=nameWithType>. Этот интерфейс используется в клиентском приложении (`ISampleServiceChannel`).  
  
- Вспомогательный класс, расширяющий класс <xref:System.ServiceModel.ClientBase%601?displayProperty=nameWithType> и используемый в клиентском приложении (`SampleServiceClient`).  
  
- Файл конфигурации, созданный из службы.  
  
- Простая реализация службы `ISampleService`.  
  
- Преобразование файла конфигурации на стороне клиента в версию на стороне службы.  
  
[!code-csharp[ClientProxyCodeSample#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/clientproxycodesample/cs/proxycode.cs#1)]

[!code-xml[ClientProxyCodeSample#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/clientproxycodesample/cs/client.exe.config#10)]

[!code-csharp[ClientProxyCodeSample#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/clientproxycodesample/cs/hostapplication.cs#5)]

[!code-xml[ClientProxyCodeSample#20](../../../../samples/snippets/csharp/VS_Snippets_CFX/clientproxycodesample/cs/hostapplication.exe.config#20)]
  
## <a name="see-also"></a>См. также раздел

- [Служебная программа для метаданных ServiceModel (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)
