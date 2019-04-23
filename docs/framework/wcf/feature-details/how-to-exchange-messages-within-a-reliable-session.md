---
title: Практическое руководство. Обмен сообщениями в рамках надежного сеанса
ms.date: 03/30/2017
ms.assetid: 87cd0e75-dd2c-44c1-8da0-7b494bbdeaea
ms.openlocfilehash: aad4eae870e3ba603c56a28a620fe8bc0e31ceb6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59342991"
---
# <a name="how-to-exchange-messages-within-a-reliable-session"></a>Практическое руководство. Обмен сообщениями в рамках надежного сеанса

В этом разделе описываются действия, необходимые, чтобы разрешить надежные сеансы с помощью одной из привязок, предоставляемых системой, которая поддерживает такие сеансы, но не по умолчанию. Включение надежного сеанса императивно с помощью кода или декларативно в файле конфигурации. Эта процедура использует файлы конфигурации клиента и службы для разрешения надежного сеанса и обеспечивается доставка сообщений в том же порядке, в котором они были отправлены.

Ключевой частью этой процедуры является, что элемент конфигурации конечной точки содержит `bindingConfiguration` атрибут, который ссылается на конфигурацию привязки с именем `Binding1`. [  **\<Привязки >** ](../../../../docs/framework/misc/binding.md) элемент конфигурации ссылается на это имя, чтобы разрешить надежные сеансы, задав `enabled` атрибут [  **\<reliableSession >** ](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731302(v=vs.100)) элемент `true`. Можно обеспечить доставку сообщений в порядке их отправки для надежного сеанса, присвоив атрибуту `ordered` значение `true`.

Копию исходного кода в этом примере, см. в разделе [надежный сеанс WS](../../../../docs/framework/wcf/samples/ws-reliable-session.md).

### <a name="configure-the-service-with-a-wshttpbinding-to-use-a-reliable-session"></a>Настройка службы с привязкой WSHttpBinding использования надежного сеанса

1. Определите контракт службы для данного типа службы.

   [!code-csharp[c_HowTo_UseReliableSession#1121](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/cs/service.cs#1121)]

1. Реализуйте контракт службы в классе службы. Обратите внимание на то, что информация об адресе или привязке не указывается внутри реализации службы. Не требуется писать код для извлечения информации адресе или привязке из файла конфигурации.

   [!code-csharp[c_HowTo_UseReliableSession#1122](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/cs/service.cs#1122)]

1. Создание *Web.config* файл, чтобы настроить конечную точку для `CalculatorService` , использующий <xref:System.ServiceModel.WSHttpBinding> с разрешением включен и упорядоченную доставку сообщений, необходимых для надежного сеанса.

   [!code-xml[c_HowTo_UseReliableSession#2111](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/common/web.config#2111)]

1. Создание *Service.svc* файл, содержащий строку:

   ```
   <%@ServiceHost language=c# Service="CalculatorService" %>
   ```

1. Место *Service.svc* файла в виртуальный каталог Internet Information Services (IIS).

### <a name="configure-the-client-with-a-wshttpbinding-to-use-a-reliable-session"></a>Настройка клиента с привязкой WSHttpBinding использования надежного сеанса

1. Используйте [ServiceModel Metadata Utility Tool (*Svcutil.exe*)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) из командной строки для создания кода из метаданных службы:

   ```console
   Svcutil.exe <service's Metadata Exchange (MEX) address or HTTP GET address>
   ```

1. Создаваемый клиент содержит `ICalculator` интерфейс, определяющий контракт службы, должна удовлетворять реализация клиента.

   [!code-csharp[C_HowTo_UseReliableSession#1221](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/cs/client.cs#1221)]

1. Созданное клиентское приложение также содержит реализацию `ClientCalculator`. Обратите внимание на то, что данные адреса и привязки не указан в любом месте внутри реализации службы. Не требуется писать код для извлечения информации адресе или привязке из файла конфигурации.

   [!code-csharp[C_HowTo_UseReliableSession#1222](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/cs/client.cs#1222)]

1. *Svcutil.exe* также создает конфигурацию для клиента, использующего <xref:System.ServiceModel.WSHttpBinding> класса. Назовите файл конфигурации *App.config* при использовании Visual Studio.

   [!code-xml[C_HowTo_UseReliableSession#2211](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/common/app.config#2211)]

1. Создайте экземпляр `ClientCalculator` в приложении и вызовите операции службы.

   [!code-csharp[C_HowTo_UseReliableSession#1223](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/cs/client.cs#1223)]

1. Скомпилируйте и запустите клиент.

## <a name="example"></a>Пример

Некоторые привязки, предоставляемые системой, по умолчанию поддерживают надежные сеансы. Сюда входит следующее.

- <xref:System.ServiceModel.WSDualHttpBinding>

- <xref:System.ServiceModel.NetNamedPipeBinding>

- <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding>

Пример того, как создать пользовательскую привязку, которая поддерживает надежные сеансы, см. в разделе [как: Создание пользовательской привязки надежного сеанса с использованием HTTPS](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-reliable-session-binding-with-https.md).

## <a name="see-also"></a>См. также

- [Надежные сеансы](../../../../docs/framework/wcf/feature-details/reliable-sessions.md)
