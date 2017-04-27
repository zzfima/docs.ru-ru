---
title: "Как обмениваться сообщениями в рамках надежного сеанса | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 87cd0e75-dd2c-44c1-8da0-7b494bbdeaea
caps.latest.revision: 9
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 9
---
# Как обмениваться сообщениями в рамках надежного сеанса
В этом разделе описываются действия, необходимые, чтобы разрешить надежные сеансы с помощью одной из привязок, предоставляемых системой, которая поддерживает такие сеансы, но не по умолчанию.Надежный сеанс можно разрешить принудительно \(в коде\) или декларативно \(в файле конфигурации\).В этой процедуре с помощью файлов конфигурации клиента и службы разрешаются надежные сеансы, и обеспечивается доставка сообщений в том же порядке, в котором они отправлены.  
  
 Ключевой момент данной процедуры заключается том, что элемент конфигурации конечной точки содержит атрибут `bindingConfiguration`, указывающий конфигурацию привязки с именем "Binding1". Затем можно сослаться на это имя с помощью элемента конфигурации [\<привязка\>](../../../../docs/framework/misc/binding.md), чтобы разрешить надежные сеансы, присвоив атрибуту `enabled` элемента [reliableSession](http://msdn.microsoft.com/ru-ru/9c93818a-7dfa-43d5-b3a1-1aafccf3a00b) значение `true`.Можно обеспечить доставку сообщений в порядке их отправки для надежного сеанса, присвоив атрибуту `ordered` значение `true`.  
  
 Копию исходного кода этого примера см. в разделе [Надежный сеанс WS](../../../../docs/framework/wcf/samples/ws-reliable-session.md).  
  
### Настройка использования надежного сеанса службой с привязкой WSHttpBinding  
  
1.  Определите контракт службы для данного типа службы.  
  
     [!code-csharp[c_HowTo_UseReliableSession#1121](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/cs/service.cs#1121)]  
  
2.  Реализуйте контракт службы в классе службы.Обратите внимание, что информация об адресе или привязке не указывается внутри реализации службы.Кроме того, для извлечения этих сведений из файла конфигурации не требуется писать код.  
  
     [!code-csharp[c_HowTo_UseReliableSession#1122](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/cs/service.cs#1122)]  
  
3.  Создайте файл Web.config для настройки конечной точки службы `CalculatorService`, использующей привязку <xref:System.ServiceModel.WSHttpBinding> с разрешением надежного сеанса и требованием доставки сообщений в порядке их отправления.  
  
     <!-- TODO: review snippet reference [!code[c_HowTo_UseReliableSession#2111](../../../../samples/snippets/common/VS_Snippets_CFX/c_howto_usereliablesession/common/web.config#2111)]  -->  
  
4.  Создайте файл Service.svc, содержащий строку:  
  
    ```  
    <%@ServiceHost language=c# Service="CalculatorService" %>   
    ```  
  
5.  Поместите файл Service.svc в виртуальный каталог IIS.  
  
### Настройка использования надежного сеанса клиентом с привязкой WSHttpBinding  
  
1.  Из командной строки запустите программу [Служебное средство ServiceModel Metadata Utility Tool \(Svcutil.exe\)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md), чтобы создать код из метаданных службы.  
  
    ```  
    Svcutil.exe <service's Metadata Exchange (MEX) address or HTTP GET address>   
    ```  
  
2.  Создаваемый клиент содержит интерфейс `ICalculator`, определяющий контракт службы, которому должна удовлетворять реализация клиента.  
  
     [!code-csharp[C_HowTo_UseReliableSession#1221](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/cs/client.cs#1221)]  
  
3.  Созданное клиентское приложение также содержит реализацию `ClientCalculator`.Обратите внимание, что информация об адресе и привязке нигде внутри реализации службы не указывается.Кроме того, для извлечения этих сведений из файла конфигурации не требуется писать код.  
  
     [!code-csharp[C_HowTo_UseReliableSession#1222](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/cs/client.cs#1222)]  
  
4.  Программа Svcutil.exe также создает конфигурацию для клиента, использующего класс <xref:System.ServiceModel.WSHttpBinding>.Этот файл должен иметь имя App.config, если используется [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)].  
  
     <!-- TODO: review snippet reference [!code[C_HowTo_UseReliableSession#2211](../../../../samples/snippets/common/VS_Snippets_CFX/c_howto_usereliablesession/common/app.config#2211)]  -->  
  
5.  Создайте экземпляр класса `ClientCalculator` в приложении и вызовите операции службы.  
  
     [!code-csharp[C_HowTo_UseReliableSession#1223](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/cs/client.cs#1223)]  
  
6.  Скомпилируйте и запустите клиент.  
  
## Пример  
<!-- TODO: review snippet reference  [!CODE [Microsoft.Win32.RegistryKey#4](Microsoft.Win32.RegistryKey#4)]  -->  
  
 Некоторые привязки, предоставляемые системой, по умолчанию поддерживают надежные сеансы.К ним относятся следующие привязки.  
  
-   <xref:System.ServiceModel.WSDualHttpBinding>  
  
-   <xref:System.ServiceModel.NetNamedPipeBinding>  
  
-   <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding>  
  
 Пример создания пользовательской привязки, поддерживающей надежные сеансы, см. в разделе [Практическое руководство. Создание пользовательской привязки надежного сеанса с использованием HTTPS](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-reliable-session-binding-with-https.md).  
  
## См. также  
 [Надежные сеансы](../../../../docs/framework/wcf/feature-details/reliable-sessions.md)