---
title: Практическое руководство. Создание пользовательской привязки надежного сеанса с использованием HTTPS
ms.date: 03/30/2017
ms.assetid: fa772232-da1f-4c66-8c94-e36c0584b549
ms.openlocfilehash: f39325829cf4b548482a6a570a5aa1fd65e61a1d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62039537"
---
# <a name="how-to-create-a-custom-reliable-session-binding-with-https"></a>Практическое руководство. Создание пользовательской привязки надежного сеанса с использованием HTTPS

В этом разделе рассматривается использование механизма обеспечения безопасности транспорта через протокол SSL и надежные сеансы. Для использования надежных сеансов через протокол HTTPS требуется создать пользовательскую привязку, использующую надежный сеанс и транспорт HTTPS. Как разрешить надежный сеанс можно принудительно с помощью кода или декларативно в файле конфигурации. Эта процедура использует файлы конфигурации клиента и службы для разрешения надежного сеанса и [  **\<httpsTransport >** ](../../../../docs/framework/configure-apps/file-schema/wcf/httpstransport.md) элемент.

Ключевой частью этой процедуры является то, что  **\<конечной точки >** элемент конфигурации содержит `bindingConfiguration` атрибут, который ссылается на пользовательскую конфигурацию привязки с именем `reliableSessionOverHttps`. [  **\<Привязки >** ](../../../../docs/framework/misc/binding.md) элемент конфигурации ссылается на это имя, чтобы указать, надежный сеанс и транспорт HTTPS используются в том числе  **\< reliableSession >** и  **\<httpsTransport >** элементов.

Копию исходного кода в этом примере, см. в разделе [пользовательские привязки надежного сеанса по протоколу HTTPS](../../../../docs/framework/wcf/samples/custom-binding-reliable-session-over-https.md).

### <a name="configure-the-service-with-a-custombinding-to-use-a-reliable-session-with-https"></a>Настройка службы с привязкой CustomBinding использования надежного сеанса с помощью протокола HTTPS

1. Определите контракт службы для данного типа службы.

   [!code-csharp[c_HowTo_CreateReliableSessionHTTPS#1121](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/cs/service.cs#1121)]

1. Реализуйте контракт службы в классе службы. Обратите внимание на то, что информация об адресе или привязке не указывается внутри реализации службы. Не требуется писать код для извлечения информации адресе или привязке из файла конфигурации.

   [!code-csharp[c_HowTo_CreateReliableSessionHTTPS#1122](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/cs/service.cs#1122)]

1. Создание *Web.config* файл, чтобы настроить конечную точку для `CalculatorService` с пользовательской привязки с именем `reliableSessionOverHttps` , использующий надежный сеанс и транспорт HTTPS.

   [!code-xml[c_HowTo_CreateReliableSessionHTTPS#2111](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/common/web.config#2111)]

1. Создание *Service.svc* файл, содержащий строку:

   ```
   <%@ServiceHost language=c# Service="CalculatorService" %>
   ```

1. Место *Service.svc* файла в виртуальный каталог Internet Information Services (IIS).

### <a name="configure-the-client-with-a-custombinding-to-use-a-reliable-session-with-https"></a>Настройка клиента с привязкой CustomBinding использования надежного сеанса с помощью протокола HTTPS

1. Используйте [ServiceModel Metadata Utility Tool (*Svcutil.exe*)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) из командной строки для создания кода из метаданных службы.

   ```console
   Svcutil.exe <Metadata Exchange (MEX) address or HTTP GET address>
   ```

1. Создаваемый клиент содержит `ICalculator` интерфейс, определяющий контракт службы, должна удовлетворять реализация клиента.

   [!code-csharp[C_HowTo_CreateReliableSessionHTTPS#1221](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/cs/client.cs#1221)]

1. Созданное клиентское приложение также содержит реализацию `ClientCalculator`. Обратите внимание на то, что сведения об адресе и привязке не указывается внутри реализации службы. Не требуется писать код, чтобы получить адрес и сведения о привязке из файла конфигурации.

   [!code-csharp[C_HowTo_CreateReliableSessionHTTPS#1222](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/cs/client.cs#1222)]

1. Настроить пользовательскую привязку с именем `reliableSessionOverHttps` использовать транспорт HTTPS и надежные сеансы.

   [!code-xml[C_HowTo_CreateReliableSessionHTTPS#2211](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/common/app.config#2211)]

1. Создайте экземпляр класса `ClientCalculator` в приложении и вызовите операции службы.

   [!code-csharp[C_HowTo_CreateReliableSessionHTTPS#1223](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/cs/client.cs#1223)]

1. Скомпилируйте и запустите клиент.  

## <a name="net-framework-security"></a>безопасность платформы .NET Framework

Так как сертификат, используемый в этом примере является тестовым сертификатом, созданным с помощью *Makecert.exe*, появляется предупреждение системы безопасности, при попытке доступа к адресу HTTPS, таким как `https://localhost/servicemodelsamples/service.svc`, в браузере.

## <a name="see-also"></a>См. также

- [Надежные сеансы](../../../../docs/framework/wcf/feature-details/reliable-sessions.md)
