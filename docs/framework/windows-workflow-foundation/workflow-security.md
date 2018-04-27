---
title: Безопасность рабочих процессов
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- programming [WF], workflow security
ms.assetid: d712a566-f435-44c0-b8c0-49298e84b114
caps.latest.revision: 13
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 90e9d5f3a2cff454ff7892877f012f8679b9ccac
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/27/2018
---
# <a name="workflow-security"></a>Безопасность рабочих процессов
Windows Workflow Foundation (WF) интегрирована с несколькими разными технологиями, например Microsoft SQL Server и [!INCLUDE[indigo1](../../../includes/indigo1-md.md)]. В случае неправильной настройки взаимодействие с этими технологиями может вызвать проблемы безопасности в рабочем процессе.  
  
## <a name="persistence-security-concerns"></a>Вопросы безопасности сохраняемости  
  
1.  Рабочие процессы, которые используют действия <xref:System.Activities.Statements.Delay> и сохраняемость, должны повторно активироваться службой. Windows AppFabric использует службу Workflow Management Service (WMS) для повторной активации рабочих процессов с истекшими таймерами. WMS создает объект <xref:System.ServiceModel.WorkflowServiceHost> для размещения повторно активированного рабочего процесса. Если служба WMS остановлена, сохраненные рабочие процессы не будут активироваться повторно при истечении их таймеров.  
  
2.  Доступ к устойчивым экземплярам должен быть защищен от вредоносных сущностей, внешних относительно домена приложения. Кроме того, разработчики должны гарантировать, что вредоносный код будет невозможно выполнить в том же домене приложения, что и код устойчивого экземпляра.  
  
3.  Устойчивый экземпляр не должен выполняться с разрешениями более высокого уровня (администратора).  
  
4.  Данные, обрабатываемые за пределами домена приложения, должны быть защищены.  
  
5.  Приложения, требующие изоляции безопасности, не должны использовать совместно один и тот же экземпляр абстракции схемы. Такие приложения должны использовать различные поставщики хранилищ или поставщики хранилищ, настроенные на создание разных экземпляров хранилищ.  
  
## <a name="sql-server-security-concerns"></a>Вопросы безопасности SQL Server  
  
-   Если используется большое количество дочерних действий, расположений, закладок, расширений узла и областей или используются закладки с очень большим объемом полезных нагрузок, может быть исчерпана память или во время сохранения будет выделен чрезмерно большой объем пространства базы данных. Избежать этого можно с помощью мер безопасности на уровне объекта и на уровне базы данных.  
  
-   Если используется <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore>, хранилище экземпляров должно быть защищено. [!INCLUDE[crdefault](../../../includes/crdefault-md.md)] [SQL Server Best Practices](http://go.microsoft.com/fwlink/?LinkId=164972).  
  
-   Конфиденциальные данные в хранилище экземпляров должны быть зашифрованы. [!INCLUDE[crdefault](../../../includes/crdefault-md.md)] [Шифрование SQL](http://go.microsoft.com/fwlink/?LinkId=164976).  
  
-   Так как строка подключения базы данных часто содержится в файле конфигурации, следует использовать безопасность уровня Windows (ACL) для обеспечения защиты файла конфигурации (обычно это Web.Config), а также для того, чтобы гарантировать, что сведения об имени входа и пароле не содержатся в строке подключения. В качестве альтернативы между базой данных и веб-сервером можно использовать аутентификацию Windows.  
  
## <a name="considerations-for-workflowservicehost"></a>Рекомендации по WorkflowServiceHost  
  
-   Конечные точки [!INCLUDE[indigo1](../../../includes/indigo1-md.md)], используемые в рабочих процессах, должны быть защищены. [!INCLUDE[crdefault](../../../includes/crdefault-md.md)] [Общие сведения о безопасности WCF](http://go.microsoft.com/fwlink/?LinkID=164975).  
  
-   Авторизацию на уровне узлов можно реализовать с помощью <xref:System.ServiceModel.ServiceAuthorizationManager>. В разделе [How To: Создание пользовательского диспетчера авторизации для службы](http://go.microsoft.com/fwlink/?LinkId=192228) подробные сведения. Это также показано в следующем примере: [Защита служб рабочего процесса](../../../docs/framework/windows-workflow-foundation/samples/securing-workflow-services.md).  
  
-   Кроме того, контекст ServiceSecurityContext для входящего сообщения доступен из рабочего процесса посредством доступа к OperationContext.  В разделе [доступ к OperationContext из службы рабочего процесса](../../../docs/framework/wcf/feature-details/accessing-operationcontext-from-a-workflow-service.md) подробные сведения.  
  
## <a name="wf-security-pack-ctp"></a>Пакет безопасности WF CTP  
 Пакет безопасности Microsoft WF CTP 1 является первой CTP (CTP)-версии набора действий и их реализации на основе [Windows Workflow Foundation](http://msdn.microsoft.com/netframework/aa663328.aspx)в [.NET Framework 4](http://msdn.microsoft.com/netframework/default.aspx) (WF (4) и [Windows Identity Foundation (WIF)](http://msdn.microsoft.com/security/aa570351.aspx).  Пакет безопасности Microsoft WF CTP 1 содержит действия и их конструкторы, которые демонстрируют простое включение различных сценариев обеспечения безопасности с помощью рабочих процессов, в том числе следующие:  
  
1.  Олицетворение удостоверения клиента в рабочем процессе  
  
2.  Авторизация в рабочих процессах, например PrincipalPermission и проверка утверждений  
  
3.  Обмен сообщениями с использованием проверки подлинности (с применением определенных в рабочем процессе ClientCredentials), например с использованием имени пользователя и пароля или токена, полученного от службы токенов безопасности (STS)  
  
4.  Сквозная передача токена безопасности клиента внутренней службе (делегирование на основе утверждений) с помощью WS-Trust ActAs  
  
Дополнительные сведения и загрузить пакет безопасности CTP WF см. раздел: [пакет безопасности WF CTP](http://wf.codeplex.com/releases/view/48114)