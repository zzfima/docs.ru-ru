---
title: "Практическое руководство. Асинхронный вызов веб-службы (Visual Basic)"
ms.date: 2015-07-20
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- asynchronous calls
- Web services, accessing
ms.assetid: ff8046f4-f1f2-4d8b-90b7-95e3f7415418
caps.latest.revision: 14
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: f191ccb5f42f9cfc5dc4e44e58d2338422207aa1
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-call-a-web-service-asynchronously-visual-basic"></a>Практическое руководство. Асинхронный вызов веб-службы (Visual Basic)
В этом примере обработчик присоединяется к асинхронному обработчику событий веб-службы таким образом, чтобы получать результаты вызова асинхронного метода. В этом примере используется веб-служба DemoTemperatureService, которая находится на веб-сайте http://www.xmethods.net.  
  
 При ссылке на веб-службу в проекте интегрированной среды разработки [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] (IDE) она добавляется к объекту `My.WebServices`, а среда IDE создает класс прокси клиента, чтобы получить доступ к указанной веб-службе.  
  
 Класс прокси позволяет синхронно вызывать методы веб-службы в те моменты, когда приложение ожидает завершения выполнения функции. Кроме того, прокси-сервер создает дополнительные элементы для обеспечения асинхронного вызова метода. Для каждой функции веб-службы *NameOfWebServiceFunction* прокси-сервер создает подпрограмму *NameOfWebServiceFunction*`Async`, событие *NameOfWebServiceFunction*`Completed` и класс *NameOfWebServiceFunction*`CompletedEventArgs`. В этом примере демонстрируется использование асинхронных элементов для получения доступа к функции `getTemp` веб-службы DemoTemperatureService.  
  
> [!NOTE]
>  Этот код не работает в веб-приложениях, так как ASP.NET не поддерживает объект `My.WebServices`.  
  
### <a name="to-call-a-web-service-asynchronously"></a>Асинхронный вызов веб-службы  
  
1.  Справочные материалы по веб-службе DemoTemperatureService находятся на веб-сайте http://www.xmethods.net. Адрес:  
  
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
  
     Чтобы асинхронно вызвать веб-метод `getTemp`, вызовите метод `CallGetTempAsync`. После своего завершения веб-метод вернет значение, переданное обработчику событий `getTempCompletedHandler`.  
  
## <a name="see-also"></a>См. также  
 [Доступ к веб-службам приложения](../../../visual-basic/developing-apps/programming/accessing-application-web-services.md)   
 [Объект My.WebServices](../../../visual-basic/language-reference/objects/my-webservices-object.md)

