---
title: "Практическое руководство. Защита службы с использованием учетных данных Windows | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "WCF, безопасность"
ms.assetid: d171b5ca-96ef-47ff-800c-c138023cf76e
caps.latest.revision: 26
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 26
---
# Практическое руководство. Защита службы с использованием учетных данных Windows
В этом разделе описывается включение режима обеспечения безопасности передачи данных для службы [!INCLUDE[indigo1](../../../includes/indigo1-md.md)], которая находится в домене Windows и вызывается клиентами того же домена. [!INCLUDE[crabout](../../../includes/crabout-md.md)]Этот сценарий в разделе [безопасность транспорта с проверкой подлинности Windows](../../../docs/framework/wcf/feature-details/transport-security-with-windows-authentication.md). Пример приложения см. в разделе [WSHttpBinding](../../../docs/framework/wcf/samples/wshttpbinding.md) образца.  
  
 Начинать изучение этого раздела рекомендуется только после определения существующего интерфейса контракта и его реализации. Также можно изменять существующие службу и клиент.  
  
 Обеспечить безопасность службы с помощью учетных данных Windows можно полностью в коде. Кроме того, можно опустить часть кода, воспользовавшись файлом конфигурации. В этом разделе описаны оба метода. Тем не менее, оба метода нельзя использовать одновременно, необходимо выбрать один из них.  
  
 Первые три процедуры показывают, как защитить службу с помощью кода. Четвертая и пятая процедуры показывают, как сделать это с помощью файла конфигурации.  
  
## <a name="using-code"></a>Использование кода  
 Полный код для службы и клиента приводится в подразделе "Примеры" в конце данного раздела.  
  
 Первая процедура указания по созданию и настройке <xref:System.ServiceModel.WSHttpBinding> класса в коде. Привязка использует транспорт HTTP. Та же привязка используется в клиенте.  
  
#### <a name="to-create-a-wshttpbinding-that-uses-windows-credentials-and-message-security"></a>Создание привязки WSHttpBinding, использующей учетные данные Windows и безопасность сообщений  
  
1.  Код этой процедуры вставлен в начало кода метода `Run` класса `Test` в коде службы, приведенном в подразделе "Примеры".  
  
2.  Создайте экземпляр <xref:System.ServiceModel.WSHttpBinding> класса.  
  
3.  Задайте <xref:System.ServiceModel.WsHttpSecurity.Mode%2A> свойство <xref:System.ServiceModel.WsHttpSecurity> класса <xref:System.ServiceModel.SecurityMode>.  
  
4.  Задайте <xref:System.ServiceModel.MessageSecurityOverHttp.ClientCredentialType%2A> свойство <xref:System.ServiceModel.MessageSecurityOverHttp> класса <xref:System.ServiceModel.MessageCredentialType>.  
  
5.  Для данной процедуры используется следующий код.  
  
     [!code-csharp[c_SecureWindowsService#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewindowsservice/cs/secureservice.cs#1)]
     [!code-vb[c_SecureWindowsService#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securewindowsservice/vb/secureservice.vb#1)]  
  
### <a name="using-the-binding-in-a-service"></a>Использование привязки в службе  
 Это вторая процедура, в которой показано, как использовать привязку в резидентной службе. [!INCLUDE[crabout](../../../includes/crabout-md.md)]Размещение служб см. в разделе [размещение служб](../../../docs/framework/wcf/hosting-services.md).  
  
##### <a name="to-use-a-binding-in-a-service"></a>Использование привязки в службе  
  
1.  Вставьте код этой процедуры после кода предыдущей процедуры  
  
2.  Создание <xref:System.Type> переменной с именем `contractType` и присвойте ей тип интерфейса (`ICalculator`). При работе с [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] следует использовать оператор `GetType`, при использовании C# следует применить ключевое слово `typeof`.  
  
3.  Создайте вторую переменную `Type` с именем `serviceType` и присвойте ей тип реализованного контракта (`Calculator`).  
  
4.  Создайте экземпляр <xref:System.Uri> класс с именем `baseAddress` с базовым адресом службы. Базовый адрес должен иметь схему, которая сочетается с транспортом. В данном случае схема транспорта - HTTP, и адрес включает специальный универсальный код ресурса (URI) "localhost" и номер порта (8036), а также базовый адрес конечной точки ("serviceModelSamples/): http://localhost:8036/serviceModelSamples/.  
  
5.  Создайте экземпляр <xref:System.ServiceModel.ServiceHost> класса `serviceType` и `baseAddress` переменные.  
  
6.  Добавьте в службу конечную точку с использованием `contractType`, привязки и имени конечной точки (secureCalculator). При инициировании вызова службы клиент должен объединять базовый адрес и имя конечной точки.  
  
7.  Вызов <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A> метод для запуска службы. Код для данной процедуры показан далее.  
  
     [!code-csharp[c_SecureWindowsService#2](../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewindowsservice/cs/secureservice.cs#2)]
     [!code-vb[c_SecureWindowsService#2](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securewindowsservice/vb/secureservice.vb#2)]  
  
### <a name="using-the-binding-in-a-client"></a>Использование привязки в клиенте  
 Эта процедура показывает, как создать прокси, взаимодействующий со службой. Прокси создается с [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) использующий метаданные службы для создания прокси.  
  
 Эта процедура также создает экземпляр <xref:System.ServiceModel.WSHttpBinding> для взаимодействия со службой, а затем вызывает службу.  
  
 В этом примере для создания клиента используется только код. В качестве альтернативы можно использовать файл конфигурации, показанный в следующем после этой процедуры разделе.  
  
##### <a name="to-use-a-binding-in-a-client-with-code"></a>Использование привязки в клиенте с кодом  
  
1.  Используйте средство SvcUtil.exe, чтобы создать код прокси из метаданных службы. [!INCLUDE[crdefault](../../../includes/crdefault-md.md)][Практическое руководство: создание клиента](../../../docs/framework/wcf/how-to-create-a-wcf-client.md). Созданный код прокси наследуется от <xref:System.ServiceModel.ClientBase%601> класс, который гарантирует, что каждый клиент имеет необходимые конструкторы, методы и свойства для взаимодействия с [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] службы. В данном примере созданный код включает класс `CalculatorClient`, который реализует интерфейс `ICalculator`, тем самым обеспечивая совместимость с кодом службы.  
  
2.  Код этой процедуры вставляется в начало метода `Main` программы клиента.  
  
3.  Создайте экземпляр <xref:System.ServiceModel.WSHttpBinding> класса и задайте для него режим безопасности `Message` и его типу учетных данных клиента `Windows`. В примере называется переменная `clientBinding`.  
  
4.  Создайте экземпляр <xref:System.ServiceModel.EndpointAddress> класс с именем `serviceAddress`. Инициализируйте экземпляр с базовым адресом, объединенным с именем конечной точки.  
  
5.  Создайте экземпляр созданного класса клиента с переменными `serviceAddress` и `clientBinding`.  
  
6.  Вызов <xref:System.ServiceModel.ClientBase%601.Open%2A> метода, как показано в следующем коде.  
  
7.  Вызовите службу и отобразите результаты.  
  
     [!code-csharp[c_secureWindowsClient#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewindowsclient/cs/secureclient.cs#1)]
     [!code-vb[c_secureWindowsClient#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securewindowsclient/vb/secureclient.vb#1)]  
  
## <a name="using-the-configuration-file"></a>Использование файла конфигурации.  
 Вместо создания привязки с процедурным кодом можно использовать следующий код, приведенный для раздела привязок файла конфигурации.  
  
 Если служба определение еще нет в разделе [проектирование и реализация служб](../../../docs/framework/wcf/designing-and-implementing-services.md), и [Настройка службы](../../../docs/framework/wcf/configuring-services.md).  
  
 **Примечание** этот код конфигурации используется в файлах конфигурации клиента и службы.  
  
#### <a name="to-enable-transfer-security-on-a-service-in-a-windows-domain-using-configuration"></a>Включение безопасности передачи в службе в домене Windows с использованием конфигурации  
  
1.  Добавить [ <> \> ](../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) элемент [ <> \> ](../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) элемент раздела файла конфигурации.  
  
2.  Добавьте элемент <`binding`> в элемент <`WSHttpBinding`> и присвойте атрибуту `configurationName` значение, подходящее для используемого приложения.  
  
3.  Добавьте элемент <`security`> и присвойте атрибуту `mode` значение Message.  
  
4.  Добавьте элемент <`message`> и присвойте атрибуту `clientCredentialType` значение Windows.  
  
5.  В файле конфигурации службы замените раздел `<bindings>` с помощью следующего кода. Если вы еще нет файла конфигурации службы, см. раздел [с помощью привязок для настройки служб и клиентов](../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md).  
  
    ```  
    <bindings>  
      <wsHttpBinding>  
       <binding name = "wsHttpBinding_Calculator">  
         <security mode="Message">  
           <message clientCredentialType="Windows"/>  
         </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    ```  
  
### <a name="using-the-binding-in-a-client"></a>Использование привязки в клиенте  
 Эта процедура показывает, как создать два файла: прокси, взаимодействующий со службой, и файл конфигурации. В этой процедуре также описаны изменения программы клиента, которая является третьим файлом, используемым в клиенте.  
  
##### <a name="to-use-a-binding-in-a-client-with-configuration"></a>Использование привязки в клиенте с конфигурацией  
  
1.  Используйте средство SvcUtil.exe, чтобы создать код прокси и файл конфигурации из метаданных службы. [!INCLUDE[crdefault](../../../includes/crdefault-md.md)][Практическое руководство: создание клиента](../../../docs/framework/wcf/how-to-create-a-wcf-client.md).  
  
2.  Замените [ <> \> ](../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) раздел в созданном файле конфигурации на код конфигурации из предыдущего раздела.  
  
3.  Процедурный код вставлен в начало метода `Main` программы клиента.  
  
4.  Создайте экземпляр созданного класса клиента, передав имя привязки в файле конфигурации в качестве входного параметра.  
  
5.  Вызов <xref:System.ServiceModel.ClientBase%601.Open%2A> метода, как показано в следующем коде.  
  
6.  Вызовите службу и отобразите результаты.  
  
     [!code-csharp[c_secureWindowsClient#2](../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewindowsclient/cs/secureclient.cs#2)]  
  
## <a name="example"></a>Пример  
 [!code-csharp[c_SecureWindowsService#0](../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewindowsservice/cs/secureservice.cs#0)]  
  
 [!code-csharp[c_SecureWindowsClient#0](../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewindowsclient/cs/secureclient.cs#0)]
 <!-- TODO: review snippet reference [!code-vb[c_SecureWindowsClient#0](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securewindowsclient/vb/secureclient.vb#0)]  -->  
  
## <a name="see-also"></a>См. также  
 <xref:System.ServiceModel.WSHttpBinding>   
 [Средство ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)   
 [Практическое руководство: создание клиента](../../../docs/framework/wcf/how-to-create-a-wcf-client.md)   
 [Защита служб](../../../docs/framework/wcf/securing-services.md)   
 [Общие сведения о безопасности](../../../docs/framework/wcf/feature-details/security-overview.md)