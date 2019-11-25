---
title: Практическое руководство. Обмен сообщениями в рамках надежного сеанса
ms.date: 03/30/2017
ms.assetid: 87cd0e75-dd2c-44c1-8da0-7b494bbdeaea
ms.openlocfilehash: 58a392fc6295e82f41e08c80a3343b4059afad7e
ms.sourcegitcommit: fbb8a593a511ce667992502a3ce6d8f65c594edf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/16/2019
ms.locfileid: "74141675"
---
# <a name="how-to-exchange-messages-within-a-reliable-session"></a>Практическое руководство. Обмен сообщениями в рамках надежного сеанса

В этом разделе описываются действия, необходимые, чтобы разрешить надежные сеансы с помощью одной из привязок, предоставляемых системой, которая поддерживает такие сеансы, но не по умолчанию. Надежный сеанс можно включить принудительно с помощью кода или декларативно в файле конфигурации. В этой процедуре используются файлы конфигурации клиента и службы для включения надежного сеанса и указания того, что сообщения поступают в том же порядке, в котором они были отправлены.

Основная часть этой процедуры состоит в том, что элемент конфигурации конечной точки содержит атрибут `bindingConfiguration`, который ссылается на конфигурацию привязки с именем `Binding1`. Элемент конфигурации [ **> привязки\<** ](../../configure-apps/file-schema/wcf/bindings.md) ссылается на это имя, чтобы включить надежные сеансы, установив атрибут `enabled` элемента [ **\<ReliableSession >** ](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731302(v=vs.100)) в значение `true`. Можно обеспечить доставку сообщений в порядке их отправки для надежного сеанса, присвоив атрибуту `ordered` значение `true`.

Исходный экземпляр этого примера см. в разделе [WS надежный сеанс](../../../../docs/framework/wcf/samples/ws-reliable-session.md).

### <a name="configure-the-service-with-a-wshttpbinding-to-use-a-reliable-session"></a>Настройка службы с помощью WSHttpBinding для использования надежного сеанса

1. Определите контракт службы для данного типа службы.

   [!code-csharp[c_HowTo_UseReliableSession#1121](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/cs/service.cs#1121)]

1. Реализуйте контракт службы в классе службы. Обратите внимание, что адрес или сведения о привязке не указываются внутри реализации службы. Вам не нужно писать код для получения адреса или сведений о привязке из файла конфигурации.

   [!code-csharp[c_HowTo_UseReliableSession#1122](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/cs/service.cs#1122)]

1. Создайте файл *Web. config* , чтобы настроить конечную точку для `CalculatorService`, которая использует <xref:System.ServiceModel.WSHttpBinding> с включенным надежным сеансом и упорядоченной доставкой требуемых сообщений.

   [!code-xml[c_HowTo_UseReliableSession#2111](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/common/web.config#2111)]

1. Создайте файл *Service. svc* , содержащий строку:

   ```
   <%@ServiceHost language=c# Service="CalculatorService" %>
   ```

1. Поместите файл *Service. svc* в виртуальный каталог службы IIS (IIS).

### <a name="configure-the-client-with-a-wshttpbinding-to-use-a-reliable-session"></a>Настройка клиента с помощью WSHttpBinding для использования надежного сеанса

1. Используйте [средство служебной программы метаданных ServiceModel (*Svcutil. exe*)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) из командной строки для создания кода из метаданных службы.

   ```console
   Svcutil.exe <service's Metadata Exchange (MEX) address or HTTP GET address>
   ```

1. Созданный клиент содержит интерфейс `ICalculator`, определяющий контракт службы, которому должна соответствовать реализация клиента.

   [!code-csharp[C_HowTo_UseReliableSession#1221](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/cs/client.cs#1221)]

1. Созданное клиентское приложение также содержит реализацию `ClientCalculator`. Обратите внимание, что адрес и сведения о привязке не указываются ни в одном месте внутри реализации службы. Вам не нужно писать код для получения адреса или сведений о привязке из файла конфигурации.

   [!code-csharp[C_HowTo_UseReliableSession#1222](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/cs/client.cs#1222)]

1. *Svcutil. exe* также создает конфигурацию для клиента, использующего класс <xref:System.ServiceModel.WSHttpBinding>. Назовите файл конфигурации *app. config* при использовании Visual Studio.

   [!code-xml[C_HowTo_UseReliableSession#2211](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/common/app.config#2211)]

1. Создайте экземпляр `ClientCalculator` в приложении и вызовите операции службы.

   [!code-csharp[C_HowTo_UseReliableSession#1223](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/cs/client.cs#1223)]

1. Скомпилируйте и запустите клиент.

## <a name="example"></a>Пример

Некоторые привязки, предоставляемые системой, по умолчанию поддерживают надежные сеансы. Сюда входит следующее.

- <xref:System.ServiceModel.WSDualHttpBinding>

- <xref:System.ServiceModel.NetNamedPipeBinding>

- <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding>

Пример создания пользовательской привязки, поддерживающей надежные сеансы, см. [в разделе как создать настраиваемую привязку надежного сеанса с помощью протокола HTTPS](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-reliable-session-binding-with-https.md).

## <a name="see-also"></a>См. также

- [Надежные сеансы](../../../../docs/framework/wcf/feature-details/reliable-sessions.md)
