---
title: "Практическое руководство. Создание пользовательской привязки надежного сеанса с использованием HTTPS"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fa772232-da1f-4c66-8c94-e36c0584b549
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 87a27bb3e33b0dd78fdb2dfa206bbde098c8b769
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-create-a-custom-reliable-session-binding-with-https"></a>Практическое руководство. Создание пользовательской привязки надежного сеанса с использованием HTTPS

В этом разделе рассматривается использование механизма обеспечения безопасности транспорта через протокол SSL и надежные сеансы. Для использования надежных сеансов через протокол HTTPS требуется создать пользовательскую привязку, использующую надежный сеанс и транспорт HTTPS. Разрешить надежный сеанс можно принудительно с помощью кода или декларативно в файле конфигурации. Эта процедура использует файлы конфигурации клиента и службы для включения надежного сеанса и [  **\<httpsTransport >** ](../../../../docs/framework/configure-apps/file-schema/wcf/httpstransport.md) элемента.

Ключевой момент данной процедуры заключается том  **\<endpoint >** элемент конфигурации содержит `bindingConfiguration` атрибут, ссылающийся на конфигурацию пользовательской привязки с именем `reliableSessionOverHttps`. [  **\<Привязки >** ](../../../../docs/framework/misc/binding.md) элемент конфигурации ссылается на это имя, чтобы указать, использовать надежный сеанс и транспорт HTTPS, включая  **\< reliableSession >** и  **\<httpsTransport >** элементов.

Исходная копия в этом примере в разделе [пользовательские привязки надежного сеанса через протокол HTTPS](../../../../docs/framework/wcf/samples/custom-binding-reliable-session-over-https.md).

### <a name="configure-the-service-with-a-custombinding-to-use-a-reliable-session-with-https"></a>Настройка службы с привязкой CustomBinding использования надежного сеанса и HTTPS

1. Определите контракт службы для данного типа службы.

   [!code-csharp[c_HowTo_CreateReliableSessionHTTPS#1121](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/cs/service.cs#1121)]

1. Реализуйте контракт службы в классе службы. Обратите внимание, что информация об адресе или привязке не указывается внутри реализации службы. Не требуется писать код, чтобы получить сведения о адресе или привязке в файле конфигурации.

   [!code-csharp[c_HowTo_CreateReliableSessionHTTPS#1122](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/cs/service.cs#1122)]

1. Создание *Web.config* файл, чтобы настроить конечную точку для `CalculatorService` для пользовательской привязки с именем `reliableSessionOverHttps` , использующий надежный сеанс и транспорт HTTPS.

   [!code-xml[c_HowTo_CreateReliableSessionHTTPS#2111](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/common/web.config#2111)]

1. Создание *Service.svc* файл, содержащий строку:

   ```
   <%@ServiceHost language=c# Service="CalculatorService" %>
   ```

1. Место *Service.svc* файл в виртуальный каталог Internet Information Services (IIS).

### <a name="configure-the-client-with-a-custombinding-to-use-a-reliable-session-with-https"></a>Настройка клиента с привязкой CustomBinding использования надежного сеанса и HTTPS

1. Используйте [ServiceModel Metadata Utility Tool (*Svcutil.exe*)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) из командной строки для создания кода из метаданных службы.

   ```console
   Svcutil.exe <Metadata Exchange (MEX) address or HTTP GET address>
   ```

1. Создаваемый клиент содержит `ICalculator` интерфейс, определяющий контракт службы, которому должна удовлетворять реализация клиента.

   [!code-csharp[C_HowTo_CreateReliableSessionHTTPS#1221](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/cs/client.cs#1221)]

1. Созданное клиентское приложение также содержит реализацию `ClientCalculator`. Обратите внимание, что информация об адресе и привязке не указывается внутри реализации службы. Не требуется писать код для извлечения информации адрес и привязку из файла конфигурации.

   [!code-csharp[C_HowTo_CreateReliableSessionHTTPS#1222](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/cs/client.cs#1222)]

1. Настроить пользовательскую привязку с именем `reliableSessionOverHttps` использовать транспорт HTTPS и надежные сеансы.

   [!code-xml[C_HowTo_CreateReliableSessionHTTPS#2211](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/common/app.config#2211)]

1. Создайте экземпляр класса `ClientCalculator` в приложении и вызовите операции службы.

   [!code-csharp[C_HowTo_CreateReliableSessionHTTPS#1223](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/cs/client.cs#1223)]

1. Скомпилируйте и запустите клиент.  

## <a name="net-framework-security"></a>безопасность платформы .NET Framework

Так как сертификат, используемый в этом примере является тестовый сертификат, созданный с *Makecert.exe*, появляется предупреждение системы безопасности при попытке доступа к адресу HTTPS, такие как `https://localhost/servicemodelsamples/service.svc`, через браузер.

## <a name="see-also"></a>См. также

[Надежные сеансы](../../../../docs/framework/wcf/feature-details/reliable-sessions.md)
