---
title: "Устранение неполадок, связанных с учебником по началу работы | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 69a21511-0871-4c41-9a53-93110e84d7fd
caps.latest.revision: 14
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 14
---
# Устранение неполадок, связанных с учебником по началу работы
В этом разделе рассматриваются наиболее распространенные проблемы, которые возникают при работе с учебником «Приступая к работе», и описываются способы их решения.  
  
1.  [Не удается найти файлы проекта на жестком диске.](../../../docs/framework/wcf/troubleshooting-the-getting-started-tutorial.md#BKMK_q1)  
  
2.  [Попытка запуска служебного приложения: HTTP не удалось зарегистрировать URL-адрес http://+:8000/ServiceModelSamples/Service/.Процесс не обладает правами доступа к этому пространству имен.](../../../docs/framework/wcf/troubleshooting-the-getting-started-tutorial.md#BKMK_q2)  
  
3.  [Попытка использования средства Svcutil.exe: svcutil не является внутренней или внешней командой, работающей программой или пакетным файлом.](../../../docs/framework/wcf/troubleshooting-the-getting-started-tutorial.md#BKMK_q3)  
  
4.  [Не удается найти файл App.config, созданный средством Svcutil.exe.](../../../docs/framework/wcf/troubleshooting-the-getting-started-tutorial.md#BKMK_q4)  
  
5.  [Компиляция клиентского приложения: CalculatorClient не содержит определение для &lt;имя_метода&gt;, невозможно найти метод расширения &lt;имя_метода&gt;, принимающий первый аргумент типа CalculatorClient (пропущена директива using или ссылка на сборку?)](../../../docs/framework/wcf/troubleshooting-the-getting-started-tutorial.md#BKMK_q5)  
  
6.  [Компиляция клиентского приложения: не удалось найти имя типа или пространства имен CalculatorClient (пропущена директива using или ссылка на сборку?)](../../../docs/framework/wcf/troubleshooting-the-getting-started-tutorial.md#BKMK_q6)  
  
7.  [Выполнение клиента: необработанное исключение: System.ServiceModel.EndpointNotFoundException. Не удается подключиться к http://localhost:8000/ServiceModelSamples/Service/CalculatorService.Код ошибки TCP 10061: подключение не установлено, т. к. конечный компьютер отверг запрос на подключение.](../../../docs/framework/wcf/troubleshooting-the-getting-started-tutorial.md#BKMK_q7)  
  
<a name="BKMK_q1"></a>   
## Не удается найти файлы проекта на жестком диске.  
 [!INCLUDE[vs_current_short](../../../includes/vs-current-short-md.md)] сохраняет файлы проекта в папке c:\\users\\\<user name\\Documents\\\<Visual Studio version\>\\Projects в [!INCLUDE[wv](../../../includes/wv-md.md)] и [!INCLUDE[win7_client_secondref](../../../includes/win7-client-secondref-md.md)], and c:\\Documents and Settings\\\<имя\_пользователя\>\\My Documents\\\<Visual Studio\_версия\>\\Projects в более ранних версиях Windows.  
  
<a name="BKMK_q2"></a>   
## Попытка запуска служебного приложения: HTTP не удалось зарегистрировать URL\-адрес http:\/\/\+:8000\/ServiceModelSamples\/Service\/.Процесс не обладает правами доступа к этому пространству имен.  
 Процесс, в котором размещается служба [!INCLUDE[indigo2](../../../includes/indigo2-md.md)], должен запускаться с правами администратора.При запуске службы из [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] необходимо запускать [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] от имени администратора.Для этого нажмите кнопку **Пуск**, щелкните правой кнопкой мыши пункт [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] и выберите **Запуск от имени администратора**.При запуске службы из командной строки необходимо запустить командную строку от имени администратора указанным выше способом.Нажмите кнопку **Пуск**, щелкните правой кнопкой мыши пункт **Командная строка** и выберите пункт **Запуск от имени администратора**.  
  
<a name="BKMK_q3"></a>   
## Попытка использования средства Svcutil.exe: svcutil не является внутренней или внешней командой, работающей программой или пакетным файлом.  
 Файл Svcutil.exe должен быть расположен в системной папке.Самым простым решением является использование командной строки.Выберите пункт **Пуск**, а затем пункт **Все программы**, [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)], **Инструменты Visual Studio** и **Командная строка**[!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)].Эта команда позволяет задать правильные пути к системным папкам для всех средств, поставляемых с [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)].  
  
<a name="BKMK_q4"></a>   
## Не удается найти файл App.config, созданный средством Svcutil.exe.  
 По умолчанию в диалоговом окне **Добавление существующего элемента** отображаются только файлы со следующими расширениями: CS, RESX, SETTINGS, XSD, WSDL.Для отображения файлов всех типов выберите пункт **Все файлы \(\*.\*\)** из раскрывающегося списка в правом нижнем углу диалогового окна **Добавление существующего элемента**.  
  
<a name="BKMK_q5"></a>   
## Компиляция клиентского приложения: CalculatorClient не содержит определение для \<имя\_метода\>, невозможно найти метод расширения \<имя\_метода\>, принимающий первый аргумент типа CalculatorClient \(пропущена директива using или ссылка на сборку?\)  
 Только методы, отмеченные атрибутом `ServiceOperationAttribute`, доступны для внешнего использования.Если атрибут `ServiceOperationAttribute` для одного из методов в интерфейсе `ICalculator` опущен, при компиляции клиентского приложения, вызывающего операцию, у которой отсутствует данный атрибут, отображается указанное сообщение об ошибке.  
  
<a name="BKMK_q6"></a>   
## Компиляция клиентского приложения: не удалось найти имя типа или пространства имен CalculatorClient \(пропущена директива using или ссылка на сборку?\)  
 Эта ошибка возникает, если в проект клиента не добавлен файл Proxy.cs или Proxy.vb.  
  
<a name="BKMK_q7"></a>   
## Выполнение клиента: необработанное исключение: System.ServiceModel.EndpointNotFoundException. Не удается подключиться к http:\/\/localhost:8000\/ServiceModelSamples\/Service\/CalculatorService.Код ошибки TCP 10061: подключение не установлено, т. к. конечный компьютер отверг запрос на подключение.  
 Эта ошибка возникает в случае запуска клиентского приложения без запуска службы.  
  
<a name="BKMK_q8"></a>   
## Необработанное исключение: System.ServiceModel.Security.SecurityNegotiationException: ошибка согласования безопасности SOAP с http:\/\/localhost:8000\/ServiceModelSamples\/Service\/CalculatorService для цели http:\/\/localhost:8000\/ServiceModelSamples\/Service\/CalculatorService  
 Эта ошибка происходит на присоединенном к домену компьютере, который не подключен к сети.Подключите компьютер к сети или отключите безопасность для клиента и для службы.Для службы замените код, создающий WSHttpBinding, на следующий.  
  
```  
// Step 3 of the hosting procedure: Add a service endpoint  
selfhost.AddServiceEndpoint(typeof(ICalculator), new WSHttpBinding(SecurityMode.None), "CalculatorService");  
  
```  
  
 Для клиента замените элемент **\<security\>**, входящий в элемент **\<binding\>**, на следующий код.  
  
```  
<security mode="Node" />  
```  
  
## См. также  
 [Учебник по началу работы](../../../docs/framework/wcf/getting-started-tutorial.md)   
 [Примеры устранения неполадок WCF](../../../docs/framework/wcf/wcf-troubleshooting-quickstart.md)   
 [Устранение неполадок, связанных с установкой](../../../docs/framework/wcf/troubleshooting-setup-issues.md)