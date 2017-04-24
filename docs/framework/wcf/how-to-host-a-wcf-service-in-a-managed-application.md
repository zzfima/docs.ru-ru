---
title: "Как разместить службу WCF в управляемом приложении | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
ms.assetid: 5eb29db0-b6dc-4e77-8c68-0a62f79d743b
caps.latest.revision: 42
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 42
---
# Как разместить службу WCF в управляемом приложении
Для размещения службы внутри управляемого приложения внедрите код службы внутрь кода управляемого приложения, определите конечную точку для службы императивно в коде, декларативно с помощью конфигурации или посредством конечных точек по умолчанию, а затем создайте экземпляр класса <xref:System.ServiceModel.ServiceHost>.  
  
 Чтобы начать принимать сообщения, вызовите метод <xref:System.ServiceModel.ICommunicationObject.Open%2A> для <xref:System.ServiceModel.ServiceHost>.При этом создается и открывается прослушиватель для этой службы.Такое размещение службы часто называется "резидентным", так как управляемое приложение самостоятельно выполняет функции ведущего приложения.Чтобы закрыть службу, вызовите метод <xref:System.ServiceModel.Channels.CommunicationObject.Close%2A?displayProperty=fullName> для <xref:System.ServiceModel.ServiceHost>.  
  
 Служба может также размещаться в управляемой службе Windows, в службах IIS или в службе активации процесса Windows \(WAS\).[!INCLUDE[crabout](../../../includes/crabout-md.md)] вариантах размещения службы см. в разделе [Размещение служб](../../../docs/framework/wcf/hosting-services.md).  
  
 Размещение служб в управляемом приложении — самый гибкий вариант размещения, так как в этом случае требуется минимальное развертывание инфраструктуры.[!INCLUDE[crabout](../../../includes/crabout-md.md)] размещении службы в управляемых приложениях см. в разделе [Размещение в управляемом приложении](../../../docs/framework/wcf/feature-details/hosting-in-a-managed-application.md).  
  
 В следующей процедуре показано, как реализовать резидентную службу в консольном приложения.  
  
### Создание резидентной службы  
  
1.  Откройте среду [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] и в меню **Файл** выберите пункт **Создать**, а затем выберите пункт **Проект**.  
  
2.  В списке **Установленные шаблоны** выберите пункты **Visual C\#**, **Windows** или **Visual Basic**, **Windows**.В зависимости от параметров [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] в узле **Другие языки** в списке **Установленные шаблоны** может присутствовать один из этих языков или оба языка.  
  
3.  Выберите пункт **Консольное приложение** из списка **Windows**.Введите `SelfHost` в поле **Имя** и нажмите кнопку **ОК**.  
  
4.  Щелкните правой кнопкой мыши файл **SelfHost** в окне **Обозреватель решений** и выберите команду **Добавить ссылку**.Выберите сборку **System.ServiceModel** на вкладке **.NET** и нажмите кнопку **ОК**.  
  
    > [!TIP]
    >  Если окно **Обозреватель решений** не отображается, в меню **Вид** выберите пункт **Обозреватель решений**.  
  
5.  Дважды щелкните файл **Program.cs** или **Module1.vb** в окне **Обозреватель решений**, чтобы открыть его в окне кода, если он еще не открыт.Добавьте следующие инструкции в начало файла.  
  
     [!code-csharp[CFX_SelfHost4#1](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#1)]
     [!code-vb[CFX_SelfHost4#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#1)]  
  
6.  Определите и реализуйте контракт службы.В этом примере определяется служба `HelloWorldService`, которая возвращает сообщение на основании входных данных, передаваемых службе.  
  
     [!code-csharp[CFX_SelfHost4#2](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#2)]
     [!code-vb[CFX_SelfHost4#2](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#2)]  
  
    > [!NOTE]
    >  [!INCLUDE[crabout](../../../includes/crabout-md.md)] об определении и реализации интерфейса службы см. в разделах [Как определить контракт службы](../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md) и [Практическое руководство. Реализация контракта службы](../../../docs/framework/wcf/how-to-implement-a-wcf-contract.md).  
  
7.  В начале метода `Main` создайте экземпляр класса <xref:System.Uri> с базовым адресом для службы.  
  
     [!code-csharp[CFX_SelfHost4#3](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#3)]
     [!code-vb[CFX_SelfHost4#3](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#3)]  
  
8.  Создайте экземпляр класса <xref:System.ServiceModel.ServiceHost>, передав <xref:System.Type>, представляющий тип службы, и универсальный код ресурса \(URI\) базового адреса в метод [ServiceHost\(Type, Uri\<xref:System.ServiceModel.ServiceHost.%23ctor%28System.Type%2CSystem.Uri%5B%5D%29>.Включите публикацию метаданных и вызовите метод <xref:System.ServiceModel.ICommunicationObject.Open%2A> в <xref:System.ServiceModel.ServiceHost>, чтобы инициализировать службу и подготовить ее к приему сообщений.  
  
     [!code-csharp[CFX_SelfHost4#4](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#4)]
     <!-- TODO: review snippet reference [!code-vb[CFX_SelfHost4#4](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#4)]  -->  
  
    > [!NOTE]
    >  В этом примере используются конечные точки по умолчанию, и для данной службы не требуется файл конфигурации.Если конечные точки не настроены, то среда выполнения создает одну конечную точку для каждого базового адреса в каждом контракте службы, реализованном в службе.[!INCLUDE[crabout](../../../includes/crabout-md.md)] о конечных точках по умолчанию см. в разделах [Упрощенная конфигурация](../../../docs/framework/wcf/simplified-configuration.md) и [Упрощенная конфигурация служб WCF](../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).  
  
9. Чтобы построить решение, нажмите CTRL\+SHIFT\+B.  
  
### Проверка службы  
  
1.  Нажмите клавиши Ctrl \+ F5, чтобы запустить службу.  
  
2.  Откройте окно **WCF Test Client**.  
  
    > [!TIP]
    >  Чтобы открыть **тестовый клиент WCF**, откройте командную строку [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] и введите **WcfTestClient.exe**.  
  
3.  Выберите команду **Add Service** из меню **File**.  
  
4.  Введите в поле адреса `http://localhost:8080/hello` и нажмите кнопку **ОК**.  
  
    > [!TIP]
    >  Убедитесь, что служба запущена. В противном случае проверка дает отрицательный результат на этом этапе.Если базовый адрес в коде был изменен, используйте на этом этапе измененный базовый адрес.  
  
5.  Дважды щелкните элемент **SayHello** в узле **My Service Projects**.Введите имя в столбце **Value** в списке **Request** и нажмите кнопку **Invoke**.В списке **Response** появится ответное сообщение.  
  
## Пример  
 В следующем примере создается объект <xref:System.ServiceModel.ServiceHost> для размещения службы типа `HelloWorldService`, затем вызывается метод <xref:System.ServiceModel.ICommunicationObject.Open%2A> для <xref:System.ServiceModel.ServiceHost>.Базовый адрес предоставляется в коде, включена публикация метаданных и используются конечные точки по умолчанию.  
  
 [!code-csharp[CFX_SelfHost4#5](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#5)]
 [!code-vb[CFX_SelfHost4#5](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#5)]  
  
## См. также  
 <xref:System.Uri>   
 <xref:System.Configuration.ConfigurationManager.AppSettings%2A>   
 <xref:System.Configuration.ConfigurationManager>   
 [Как разместить службу WCF в IIS](../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-iis.md)   
 [Резидентное размещение](../../../docs/framework/wcf/samples/self-host.md)   
 [Размещение служб](../../../docs/framework/wcf/hosting-services.md)   
 [Как определить контракт службы](../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md)   
 [Практическое руководство. Реализация контракта службы](../../../docs/framework/wcf/how-to-implement-a-wcf-contract.md)   
 [Служебное средство ServiceModel Metadata Utility Tool \(Svcutil.exe\)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)   
 [Использование привязок для настройки служб и клиентов](../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)   
 [Привязки, предоставляемые системой](../../../docs/framework/wcf/system-provided-bindings.md)