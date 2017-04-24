---
title: "Практическое руководство. Создание пользовательской привязки надежного сеанса с использованием HTTPS | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: fa772232-da1f-4c66-8c94-e36c0584b549
caps.latest.revision: 9
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 9
---
# Практическое руководство. Создание пользовательской привязки надежного сеанса с использованием HTTPS
В этом разделе рассматривается использование механизма обеспечения безопасности транспорта через протокол SSL и надежные сеансы.  Для использования надежных сеансов через протокол HTTPS требуется создать пользовательскую привязку, использующую надежный сеанс и транспорт HTTPS.  Разрешить надежный сеанс можно принудительно \(в коде\) или декларативно \(в файле конфигурации\).  В этой процедуре для разрешения надежного сеанса используются файлы конфигурации клиента и службы и элемент [\<httpsTransport\>](../../../../docs/framework/configure-apps/file-schema/wcf/httpstransport.md).  
  
 Ключевой момент данной процедуры заключается том, что элемент конфигурации `endpoint` содержит атрибут `bindingConfiguration`, ссылающийся на конфигурацию пользовательской привязки с именем "reliableSessionOverHttps".  Элемент конфигурации [\<привязка\>](../../../../docs/framework/misc/binding.md) может затем ссылаться на это имя, чтобы указать, что используются надежный сеанс и транспорт HTTPS, так как включены элементы `reliableSession` и `httpsTransport`.  
  
 Копию исходного кода этого примера см. в разделе [Надежный сеанс по протоколу HTTPS с использованием пользовательской привязки](../../../../docs/framework/wcf/samples/custom-binding-reliable-session-over-https.md).  
  
### Настройка использования надежного сеанса и HTTPS службой с привязкой CustomBinding  
  
1.  Определите контракт службы для данного типа службы.  
  
     [!code-csharp[c_HowTo_CreateReliableSessionHTTPS#1121](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/cs/service.cs#1121)]  
  
2.  Реализуйте контракт службы в классе службы.  Обратите внимание, что информация об адресе или привязке не указывается внутри реализации службы.  Кроме того, для извлечения этих сведений из файла конфигурации не требуется писать код.  
  
     [!code-csharp[c_HowTo_CreateReliableSessionHTTPS#1122](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/cs/service.cs#1122)]  
  
3.  Создайте файл Web.config, чтобы настроить использование пользовательской привязки "reliableSessionOverHttps", использующей надежный сеанс и транспорт HTTPS, с конечной точкой службы `CalculatorService`.  
  
     <!-- TODO: review snippet reference [!code[c_HowTo_CreateReliableSessionHTTPS#2111](../../../../samples/snippets/common/VS_Snippets_CFX/c_howto_createreliablesessionhttps/common/web.config#2111)]  -->  
  
4.  Создайте файл Service.svc, содержащий строку:  
  
    ```  
    <%@ServiceHost language=c# Service="CalculatorService" %>   
    ```  
  
5.  Поместите файл Service.svc в виртуальный каталог IIS.  
  
### Настройка использования надежного сеанса и HTTPS клиентом с привязкой CustomBinding  
  
1.  Из командной строки запустите программу [Служебное средство ServiceModel Metadata Utility Tool \(Svcutil.exe\)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md), чтобы создать код из метаданных службы.  
  
    ```  
    Svcutil.exe <service's Metadata Exchange (MEX) address or HTTP GET address>   
    ```  
  
2.  Создаваемый клиент содержит интерфейс `ICalculator`, определяющий контракт службы, которому должна удовлетворять реализация клиента.  
  
     [!code-csharp[C_HowTo_CreateReliableSessionHTTPS#1221](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/cs/client.cs#1221)]  
  
3.  Созданное клиентское приложение также содержит реализацию `ClientCalculator`.  Обратите внимание, что информация об адресе и привязке нигде внутри реализации службы не указывается.  Кроме того, для извлечения этих сведений из файла конфигурации не требуется писать код.  
  
     [!code-csharp[C_HowTo_CreateReliableSessionHTTPS#1222](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/cs/client.cs#1222)]  
  
4.  Задайте пользовательской привязке "reliableSessionOverHttps" использовать транспорт HTTPS и надежные сеансы.  
  
     <!-- TODO: review snippet reference [!code[C_HowTo_CreateReliableSessionHTTPS#2211](../../../../samples/snippets/common/VS_Snippets_CFX/c_howto_createreliablesessionhttps/common/app.config#2211)]  -->  
  
5.  Создайте экземпляр класса `ClientCalculator` в приложении и вызовите операции службы.  
  
     [!code-csharp[C_HowTo_CreateReliableSessionHTTPS#1223](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/cs/client.cs#1223)]  
  
6.  Скомпилируйте и запустите клиент.  
  
## Пример  
<!-- TODO: review snippet reference  [!CODE [Microsoft.Win32.RegistryKey#4](Microsoft.Win32.RegistryKey#4)]  -->  
  
## Безопасность платформы .NET Framework  
 При попытке доступа к адресу HTTPS, такому как https:\/\/localhost\/servicemodelsamples\/service.svc, через браузер, возникает предупреждение системы безопасности, так как сертификат, используемый в этом примере, является тестовым сертификатом, созданным Makecert.exe.  
  
## См. также  
 [Надежные сеансы](../../../../docs/framework/wcf/feature-details/reliable-sessions.md)