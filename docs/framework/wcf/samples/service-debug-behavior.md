---
title: "Поведение отладки службы | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 9d8fd3fb-dc39-427a-8235-336a7e7162ba
caps.latest.revision: 10
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 10
---
# Поведение отладки службы
В этом образце показано, как могут настраиваться параметры поведения отладки службы.Данный образец основан на образце [Начало работы](../../../../docs/framework/wcf/samples/getting-started-sample.md), который реализует контракт службы `ICalculator`.Этот образец явно определяет поведение отладки службы в файле конфигурации.Это также можно выполнить императивно в коде.  
  
 В этом образце клиентом является консольное приложение \(EXE\), а служба размещается в службах IIS.  
  
> [!NOTE]
>  Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.  
  
 Файл Web.config для сервера определяет поведение отладки службы для включения страницы справки и обработки исключений, как показано в следующем образце.  
  
```  
  
<behaviors>  
     <serviceBehaviors>  
         <behavior name="CalculatorServiceBehavior">  
         <!-- WARNING: Setting includeExceptionDetailInFaults = "True" could result in leaking secured server information to the client.-->  
         <!-- Please set this to false when deploying -->  
             <serviceDebug includeExceptionDetailInFaults="True" httpHelpPageEnabled="True"/>  
         </behavior>  
     </serviceBehaviors>  
</behaviors>  
  
```  
  
 [\<serviceDebug\>](../../../../docs/framework/configure-apps/file-schema/wcf/servicedebug.md) является элементом конфигурации, позволяющим изменять свойства поведения отладки службы.Пользователь может изменять это поведение для достижения следующих целей.  
  
-   Это позволяет службе возвращать любое исключение, вызванное кодом приложения, даже если это исключение не объявлено с помощью атрибута <xref:System.ServiceModel.FaultContractAttribute>.Для этого необходимо присвоить параметру `includeExceptionDetailInFaults` значение `true`.Этот параметр полезен при отладке в тех случаях, когда сервер создает непредвиденное исключение.  
  
    > [!IMPORTANT]
    >  Включать этот параметр в производственной среде небезопасно.В непредвиденном исключении сервера может содержаться информация, не предназначенная для клиента, поэтому присвоение параметру `includeExceptionDetailsInFaults` значения `true` может привести к утечке информации.  
  
-   С помощью [\<serviceDebug\>](../../../../docs/framework/configure-apps/file-schema/wcf/servicedebug.md) пользователь также может включить или отключить страницу справки.Каждая служба может предоставлять страницу справки, которая содержит данные о службе, включая сведения о конечной точке для получения WSDL для службы.Эту возможность можно включить, присвоив параметру `httpHelpPageEnabled` значение `true`.Это позволяет возвращать страницу справки в ответ на запрос GET к базовому адресу службы.Этот адрес можно изменить, задав другой атрибут `httpHelpPageUrl`.Можно сделать этот процесс безопасным, если использовать транспорт HTTPS вместо HTTP.Для этого необходимо задать `httpsHelpPageEnabled` и `httpsHelpPageUrl`.  
  
 При выполнении образца запросы и ответы операций отображаются в окне консоли клиента.Первые три операции \(сложение, вычитание и умножение\) должны выполняться успешно.Последняя операция \(деление\) завершается неудачей — выдается исключение в результате деления на ноль.  
  
### Настройка, построение и выполнение образца  
  
1.  Убедитесь, что выполнены процедуры, описанные в разделе [Процедура однократной настройки образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Чтобы создать выпуск решения на языке C\# или Visual Basic .NET, следуйте инструкциям в разделе [Построение образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3.  Чтобы выполнить образец на одном или нескольких компьютерах, следуйте инструкциям в разделе [Выполнение примеров Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере.Перед продолжением проверьте следующий каталог \(по умолчанию\).  
>   
>  `<диск_установки>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Образцы Windows Communication Foundation \(WCF\) и Windows Workflow Foundation \(WF\) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780), чтобы загрузить все образцы [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)].Этот образец расположен в следующем каталоге.  
>   
>  `<диск_установки>:\WF_WCF_Samples\WCF\Basic\Services\Behaviors\ServiceDebug`  
  
## См. также