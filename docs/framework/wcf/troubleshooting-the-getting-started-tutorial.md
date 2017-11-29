---
title: "Устранение неполадок, связанных с руководством по началу работы"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 69a21511-0871-4c41-9a53-93110e84d7fd
caps.latest.revision: "14"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 71a78650cc430068b2ecf27174140f27e7193ae6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="troubleshooting-the-getting-started-tutorial"></a>Устранение неполадок, связанных с руководством по началу работы
В этом разделе рассматриваются наиболее распространенные проблемы, которые возникают при работе с учебником «Приступая к работе», и описываются способы их решения.  
  
1.  [Не удается найти файлы проекта на жестком диске.](../../../docs/framework/wcf/troubleshooting-the-getting-started-tutorial.md#BKMK_q1)  
  
2.  [Попытка запуска служебного приложения: HTTP не удалось зарегистрировать URL-адрес http://+:8000/ServiceModelSamples/Service/. Процесс не обладает правами доступа к этому пространству имен.](../../../docs/framework/wcf/troubleshooting-the-getting-started-tutorial.md#BKMK_q2)  
  
3.  [Попытка использования средства Svcutil.exe: «svcutil» не распознается как внутренняя или внешняя команда, исполняемая программа или пакетный файл.](../../../docs/framework/wcf/troubleshooting-the-getting-started-tutorial.md#BKMK_q3)  
  
4.  [Не удалось найти файл App.config, созданный Svcutil.exe.](../../../docs/framework/wcf/troubleshooting-the-getting-started-tutorial.md#BKMK_q4)  
  
5.  [Компиляция клиентского приложения: «CalculatorClient» не содержит определение для "&lt;имя метода&gt;«и метод расширения»&lt;имя метода&gt;" принимающий первый аргумент типа «CalculatorClient» может быть найден (возможно, отсутствует с помощью директивы или ссылка на сборку?)](../../../docs/framework/wcf/troubleshooting-the-getting-started-tutorial.md#BKMK_q5)  
  
6.  [Компиляция клиентского приложения: «CalculatorClient» не удалось найти имя типа или пространства имен (возможно, отсутствует с помощью директивы или ссылка на сборку?)](../../../docs/framework/wcf/troubleshooting-the-getting-started-tutorial.md#BKMK_q6)  
  
7.  [Выполнение клиента: необработанное исключение: System.ServiceModel.EndpointNotFoundException: не удалось подключиться к http://localhost: 8000/ServiceModelSamples/Service/CalculatorService. Код ошибки TCP 10061: не удалось подключиться, так как конечный компьютер отверг.](../../../docs/framework/wcf/troubleshooting-the-getting-started-tutorial.md#BKMK_q7)  
  
<a name="BKMK_q1"></a>   
## <a name="i-am-unable-to-find-the-project-files-on-my-hard-drive"></a>Не удается найти файлы проекта на жестком диске.  
 [!INCLUDE[vs_current_short](../../../includes/vs-current-short-md.md)]сохраняет файлы проекта в c:\users\\< пользователя name\Documents\\< версия Visual Studio\>\Projects в [!INCLUDE[wv](../../../includes/wv-md.md)] и [!INCLUDE[win7_client_secondref](../../../includes/win7-client-secondref-md.md)]и c:\Documents and Settings\\< имя пользователя\>\My documents\\< версия Visual Studio\>\Projects в более ранних версиях Windows.  
  
<a name="BKMK_q2"></a>   
## <a name="attempting-to-run-the-service-application-http-could-not-register-url-http8000servicemodelsamplesservice-your-process-does-not-have-access-rights-to-this-namespace"></a>Попытка запуска служебного приложения: HTTP не удалось зарегистрировать URL-адрес http://+:8000/ServiceModelSamples/Service/. Процесс не обладает правами доступа к этому пространству имен.  
 Процесс, в котором размещается служба [!INCLUDE[indigo2](../../../includes/indigo2-md.md)], должен запускаться с правами администратора. При запуске службы из [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] необходимо запускать [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] от имени администратора. Для этого выберите **запустить**, щелкните правой кнопкой мыши [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] и выберите **Запуск от имени администратора**. При запуске службы из командной строки необходимо запустить командную строку от имени администратора указанным выше способом. Нажмите кнопку **запустить**, щелкните правой кнопкой мыши **командной строки** и выберите **Запуск от имени администратора**.  
  
<a name="BKMK_q3"></a>   
## <a name="attempting-to-use-the-svcutilexe-tool-svcutil-is-not-recognized-as-an-internal-or-external-command-operable-program-or-batch-file"></a>Попытка использования средства Svcutil.exe: svcutil не является внутренней или внешней командой, работающей программой или пакетным файлом.  
 Файл Svcutil.exe должен быть расположен в системной папке. Самым простым решением является использование командной строки. Нажмите кнопку **запустить**выберите **все программы**, [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)], **набора средств Visual Studio**, и [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] **командной строки**. Эта командная строка позволяет задать правильные пути к системным папкам для всех средств, поставляемых с [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)].  
  
<a name="BKMK_q4"></a>   
## <a name="unable-to-find-the-appconfig-file-generated-by-svcutilexe"></a>Не удается найти файл App.config, созданный средством Svcutil.exe.  
 **Добавление существующего элемента** диалогового окна отображаются только файлы со следующими расширениями по умолчанию: .cs, .resx, с расширением Settings, XSD-файл, .wsdl. Можно указать, что вы хотите просмотреть все типы файлов, выберите **все файлы (\*.\*)**  в раскрывающемся списке в правом нижнем углу **Добавление существующего элемента** диалоговое окно.  
  
<a name="BKMK_q5"></a>   
## <a name="compiling-the-client-application-calculatorclient-does-not-contain-a-definition-for-method-name-and-no-extension-method-method-name-accepting-a-first-argument-of-type-calculatorclient-could-be-found-are-you-missing-a-using-directive-or-an-assembly-reference"></a>Компиляция клиентского приложения: «CalculatorClient» не содержит определение для "\<имя_метода >" и метод расширения "\<имя метода >" принимающий первый аргумент типа «CalculatorClient» может быть найден (вы отсутствует в с помощью директивы или ссылка на сборку?)  
 Только методы, отмеченные атрибутом `ServiceOperationAttribute`, доступны для внешнего использования. Если атрибут `ServiceOperationAttribute` для одного из методов в интерфейсе `ICalculator` опущен, при компиляции клиентского приложения, вызывающего операцию, у которой отсутствует данный атрибут, отображается указанное сообщение об ошибке.  
  
<a name="BKMK_q6"></a>   
## <a name="compiling-the-client-application-the-type-or-namespace-name-calculatorclient-could-not-be-found-are-you-missing-a-using-directive-or-an-assembly-reference"></a>Компиляция клиентского приложения: не удалось найти имя типа или пространства имен CalculatorClient (пропущена директива using или ссылка на сборку?)  
 Эта ошибка возникает, если в проект клиента не добавлен файл Proxy.cs или Proxy.vb.  
  
<a name="BKMK_q7"></a>   
## <a name="running-the-client-unhandled-exception-systemservicemodelendpointnotfoundexception-could-not-connect-to-httplocalhost8000servicemodelsamplesservicecalculatorservice-tcp-error-code-10061-no-connection-could-be-made-because-the-target-machine-actively-refused-it"></a>Выполнение клиента: необработанное исключение: System.ServiceModel.EndpointNotFoundException. Не удается подключиться к http://localhost:8000/ServiceModelSamples/Service/CalculatorService. Код ошибки TCP 10061: подключение не установлено, т. к. конечный компьютер отверг запрос на подключение.  
 Эта ошибка возникает в случае запуска клиентского приложения без запуска службы.  
  
<a name="BKMK_q8"></a>   
## <a name="unhandled-exception-systemservicemodelsecuritysecuritynegotiationexception-soap-security-negotiation-with-httplocalhost8000servicemodelsamplesservicecalculatorservice-for-target-httplocalhost8000servicemodelsamplesservicecalculatorservice-failed"></a>Необработанное исключение: System.ServiceModel.Security.SecurityNegotiationException: ошибка согласования безопасности SOAP с http://localhost:8000/ServiceModelSamples/Service/CalculatorService для цели http://localhost:8000/ServiceModelSamples/Service/CalculatorService  
 Эта ошибка происходит на присоединенном к домену компьютере, который не подключен к сети. Подключите компьютер к сети или отключите безопасность для клиента и для службы. Для службы замените код, создающий WSHttpBinding, на следующий.  
  
```  
// Step 3 of the hosting procedure: Add a service endpoint  
selfhost.AddServiceEndpoint(typeof(ICalculator), new WSHttpBinding(SecurityMode.None), "CalculatorService");  
```  
  
 Клиент, измените  **\<безопасности >** элемента под  **\<привязки >** элемент на следующий:  
  
```xml  
<security mode="Node" />  
```  
  
## <a name="see-also"></a>См. также  
 [Руководство по началу работы](../../../docs/framework/wcf/getting-started-tutorial.md)  
 [Примеры устранения неполадок WCF](../../../docs/framework/wcf/wcf-troubleshooting-quickstart.md)  
 [Устранение неполадок с установкой](../../../docs/framework/wcf/troubleshooting-setup-issues.md)
