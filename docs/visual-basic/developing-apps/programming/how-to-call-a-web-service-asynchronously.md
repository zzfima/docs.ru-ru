---
title: "Практическое руководство. Асинхронный вызов веб-службы (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- asynchronous calls [Visual Basic]
- Web services [Visual Basic], accessing
ms.assetid: ff8046f4-f1f2-4d8b-90b7-95e3f7415418
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 6410ef93a706c047047aa24b3d47f8915e928015
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-call-a-web-service-asynchronously-visual-basic"></a><span data-ttu-id="4826f-102">Практическое руководство. Асинхронный вызов веб-службы (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4826f-102">How to: Call a Web Service Asynchronously (Visual Basic)</span></span>
<span data-ttu-id="4826f-103">В этом примере обработчик присоединяется к асинхронному обработчику событий веб-службы таким образом, чтобы получать результаты вызова асинхронного метода.</span><span class="sxs-lookup"><span data-stu-id="4826f-103">This example attaches a handler to a Web service's asynchronous handler event, so that it can retrieve the result of an asynchronous method call.</span></span> <span data-ttu-id="4826f-104">В этом примере используется веб-служба DemoTemperatureService, которая находится на веб-сайте http://www.xmethods.net.</span><span class="sxs-lookup"><span data-stu-id="4826f-104">This example used the DemoTemperatureService Web service at http://www.xmethods.net.</span></span>  
  
 <span data-ttu-id="4826f-105">При ссылке на веб-службу в проекте интегрированной среды разработки [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] (IDE) она добавляется к объекту `My.WebServices`, а среда IDE создает класс прокси клиента, чтобы получить доступ к указанной веб-службе.</span><span class="sxs-lookup"><span data-stu-id="4826f-105">When you reference a Web service in your project in the [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] Integrated Development Environment (IDE), it is added to the `My.WebServices` object, and the IDE generates a client proxy class to access a specified Web service</span></span>  
  
 <span data-ttu-id="4826f-106">Класс прокси позволяет синхронно вызывать методы веб-службы в те моменты, когда приложение ожидает завершения выполнения функции.</span><span class="sxs-lookup"><span data-stu-id="4826f-106">The proxy class allows you to call the Web service methods synchronously, where your application waits for the function to complete.</span></span> <span data-ttu-id="4826f-107">Кроме того, прокси-сервер создает дополнительные элементы для обеспечения асинхронного вызова метода.</span><span class="sxs-lookup"><span data-stu-id="4826f-107">In addition, the proxy creates additional members to help call the method asynchronously.</span></span> <span data-ttu-id="4826f-108">Для каждой функции веб-службы *NameOfWebServiceFunction* прокси-сервер создает подпрограмму *NameOfWebServiceFunction*`Async`, событие *NameOfWebServiceFunction*`Completed` и класс *NameOfWebServiceFunction*`CompletedEventArgs`.</span><span class="sxs-lookup"><span data-stu-id="4826f-108">For each Web service function, *NameOfWebServiceFunction*, the proxy creates a *NameOfWebServiceFunction*`Async` subroutine, a *NameOfWebServiceFunction*`Completed` event, and a *NameOfWebServiceFunction*`CompletedEventArgs` class.</span></span> <span data-ttu-id="4826f-109">В этом примере демонстрируется использование асинхронных элементов для получения доступа к функции `getTemp` веб-службы DemoTemperatureService.</span><span class="sxs-lookup"><span data-stu-id="4826f-109">This example demonstrates how to use the asynchronous members to access the `getTemp` function of the DemoTemperatureService Web service.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4826f-110">Этот код не работает в веб-приложениях, так как ASP.NET не поддерживает объект `My.WebServices`.</span><span class="sxs-lookup"><span data-stu-id="4826f-110">This code does not work in Web applications, because ASP.NET does not support the `My.WebServices` object.</span></span>  
  
### <a name="to-call-a-web-service-asynchronously"></a><span data-ttu-id="4826f-111">Асинхронный вызов веб-службы</span><span class="sxs-lookup"><span data-stu-id="4826f-111">To call a Web service asynchronously</span></span>  
  
1.  <span data-ttu-id="4826f-112">Справочные материалы по веб-службе DemoTemperatureService находятся на веб-сайте http://www.xmethods.net.</span><span class="sxs-lookup"><span data-stu-id="4826f-112">Reference the DemoTemperatureService Web service at http://www.xmethods.net.</span></span> <span data-ttu-id="4826f-113">Адрес:</span><span class="sxs-lookup"><span data-stu-id="4826f-113">The address is</span></span>  
  
    ```  
    http://www.xmethods.net/sd/2001/DemoTemperatureService.wsdl  
    ```  
  
2.  <span data-ttu-id="4826f-114">Добавьте обработчик событий для события `getTempCompleted`.</span><span class="sxs-lookup"><span data-stu-id="4826f-114">Add an event handler for the `getTempCompleted` event:</span></span>  
  
    ```  
    Private Sub getTempCompletedHandler(ByVal sender As Object,   
        ByVal e As net.xmethods.www.getTempCompletedEventArgs)  
  
        MsgBox("Temperature: " & e.Result)  
    End Sub  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="4826f-115">Оператор `Handles` нельзя использовать для сопоставления обработчика событий с событиями объекта `My.WebServices`.</span><span class="sxs-lookup"><span data-stu-id="4826f-115">You cannot use the `Handles` statement to associate an event handler with the `My.WebServices` object's events.</span></span>  
  
3.  <span data-ttu-id="4826f-116">Добавьте поле, которое будет отслеживать добавление к событию `getTempCompleted` обработчика событий.</span><span class="sxs-lookup"><span data-stu-id="4826f-116">Add a field to track if the event handler has been added to the `getTempCompleted` event:</span></span>  
  
    ```  
    Private handlerAttached As Boolean = False  
    ```  
  
4.  <span data-ttu-id="4826f-117">При необходимости добавьте метод, который будет добавлять обработчик для события `getTempCompleted` и вызывать метод `getTempAsynch`.</span><span class="sxs-lookup"><span data-stu-id="4826f-117">Add a method to add the event handler to the `getTempCompleted` event, if necessary, and to call the `getTempAsynch` method:</span></span>  
  
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
  
     <span data-ttu-id="4826f-118">Чтобы асинхронно вызвать веб-метод `getTemp`, вызовите метод `CallGetTempAsync`.</span><span class="sxs-lookup"><span data-stu-id="4826f-118">To call the `getTemp` Web method asynchronously, call the `CallGetTempAsync` method.</span></span> <span data-ttu-id="4826f-119">После своего завершения веб-метод вернет значение, переданное обработчику событий `getTempCompletedHandler`.</span><span class="sxs-lookup"><span data-stu-id="4826f-119">When the Web method finishes, its return value is passed to the `getTempCompletedHandler` event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4826f-120">См. также</span><span class="sxs-lookup"><span data-stu-id="4826f-120">See Also</span></span>  
 [<span data-ttu-id="4826f-121">Доступ к веб-службам приложения</span><span class="sxs-lookup"><span data-stu-id="4826f-121">Accessing Application Web Services</span></span>](../../../visual-basic/developing-apps/programming/accessing-application-web-services.md)  
 [<span data-ttu-id="4826f-122">Объект My.WebServices</span><span class="sxs-lookup"><span data-stu-id="4826f-122">My.WebServices Object</span></span>](../../../visual-basic/language-reference/objects/my-webservices-object.md)
