---
title: "Практическое руководство. Асинхронный вызов веб-службы (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "асинхронные вызовы"
  - "веб-службы, доступ"
ms.assetid: ff8046f4-f1f2-4d8b-90b7-95e3f7415418
caps.latest.revision: 14
caps.handback.revision: 14
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Практическое руководство. Асинхронный вызов веб-службы (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

В этом примере обработчик присоединяется к асинхронному обработчику событий веб\-службы таким образом, чтобы получать результаты вызова асинхронного метода.  В этом примере используется веб\-служба DemoTemperatureService, которая находится на веб\-сайте http:\/\/www.xmethods.  net.  
  
 При ссылке на веб\-службу в проекте интегрированной среды разработки [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] \(IDE\) она добавляется к объекту `My.WebServices`, а среда IDE создает класс прокси клиента, чтобы получить доступ к указанной веб\-службе.  
  
 Класс прокси позволяет синхронно вызывать методы веб\-службы в те моменты, когда приложение ожидает завершения выполнения функции.  Кроме того, прокси\-сервер создает дополнительные элементы для обеспечения асинхронного вызова метода.  Для каждой функции веб\-службы *NameOfWebServiceFunction* прокси\-сервер создает подпрограмму *NameOfWebServiceFunction*`Async`, событие *NameOfWebServiceFunction*`Completed` и класс *NameOfWebServiceFunction*`CompletedEventArgs`.  В этом примере демонстрируется использование асинхронных элементов для получения доступа к функции `getTemp` веб\-службы DemoTemperatureService.  
  
> [!NOTE]
>  Этот код не работает в веб\-приложениях, так как ASP.NET не поддерживает объект `My.WebServices`.  
  
### Асинхронный вызов веб\-службы  
  
1.  Справочные материалы по веб\-службе DemoTemperatureService находятся на веб\-сайте http:\/\/www.xmethods.  net.  Адрес:  
  
    ```  
    http://www.xmethods.net/sd/2001/DemoTemperatureService.wsdl  
    ```  
  
2.  Добавьте обработчик событий для события `getTempCompleted`.  
  
    ```  
    Private Sub getTempCompletedHandler(ByVal sender As Object,   
        ByVal e As net.xmethods.www.getTempCompletedEventArgs)  
  
        MsgBox("Temperature: " & e.Result)  
    End Sub  
    ```  
  
    > [!NOTE]
    >  Оператор `Handles` нельзя использовать для сопоставления обработчика событий с событиями объекта `My.WebServices`.  
  
3.  Добавьте поле, которое будет отслеживать добавление к событию `getTempCompleted` обработчика событий.  
  
    ```  
    Private handlerAttached As Boolean = False  
    ```  
  
4.  При необходимости добавьте метод, который будет добавлять обработчик для события `getTempCompleted` и вызывать метод `getTempAsynch`.  
  
    ```  
    Sub CallGetTempAsync(ByVal zipCode As Integer)  
        If Not handlerAttached Then  
            AddHandler My.WebServices.  
                TemperatureService.getTempCompleted,   
                AddressOf Me.TS_getTempCompleted  
            handlerAttached = True  
        End If  
        My.WebServices.TemperatureService.getTempAsync(zipCode)  
    End Sub  
    ```  
  
     Чтобы асинхронно вызвать веб\-метод `getTemp`, вызовите метод `CallGetTempAsync`.  После своего завершения веб\-метод вернет значение, переданное обработчику событий `getTempCompletedHandler`.  
  
## См. также  
 [Доступ к веб\-службам приложения](../../../visual-basic/developing-apps/programming/accessing-application-web-services.md)   
 [Объект My.WebServices](../../../visual-basic/language-reference/objects/my-webservices-object.md)