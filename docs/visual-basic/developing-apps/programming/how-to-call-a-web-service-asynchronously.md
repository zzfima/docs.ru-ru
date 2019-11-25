---
title: Практическое руководство. Асинхронный вызов веб-службы
ms.date: 07/20/2015
helpviewer_keywords:
- asynchronous calls [Visual Basic]
- Web services [Visual Basic], accessing
ms.assetid: ff8046f4-f1f2-4d8b-90b7-95e3f7415418
ms.openlocfilehash: 0eeb358ba38836ba6302f98f9e3e0314b83510f0
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352124"
---
# <a name="how-to-call-a-web-service-asynchronously-visual-basic"></a><span data-ttu-id="93b7a-102">Практическое руководство. Асинхронный вызов веб-службы (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="93b7a-102">How to: Call a Web Service Asynchronously (Visual Basic)</span></span>

<span data-ttu-id="93b7a-103">В этом примере обработчик присоединяется к асинхронному обработчику событий веб-службы таким образом, чтобы получать результаты вызова асинхронного метода.</span><span class="sxs-lookup"><span data-stu-id="93b7a-103">This example attaches a handler to a Web service's asynchronous handler event, so that it can retrieve the result of an asynchronous method call.</span></span> <span data-ttu-id="93b7a-104">В этом примере используется веб-служба DemoTemperatureService, которая находится на веб-сайте `http://www.xmethods.net`.</span><span class="sxs-lookup"><span data-stu-id="93b7a-104">This example used the DemoTemperatureService Web service at `http://www.xmethods.net`.</span></span>

<span data-ttu-id="93b7a-105">При ссылке на веб-службу в проекте в интегрированной среде разработки Visual Studio (IDE) она добавляется к объекту `My.WebServices`, а среда IDE создает класс прокси клиента, чтобы получить доступ к указанной веб-службе.</span><span class="sxs-lookup"><span data-stu-id="93b7a-105">When you reference a Web service in your project in the Visual Studio Integrated Development Environment (IDE), it is added to the `My.WebServices` object, and the IDE generates a client proxy class to access a specified Web service</span></span>

<span data-ttu-id="93b7a-106">Класс прокси позволяет синхронно вызывать методы веб-службы в те моменты, когда приложение ожидает завершения выполнения функции.</span><span class="sxs-lookup"><span data-stu-id="93b7a-106">The proxy class allows you to call the Web service methods synchronously, where your application waits for the function to complete.</span></span> <span data-ttu-id="93b7a-107">Кроме того, прокси-сервер создает дополнительные элементы для обеспечения асинхронного вызова метода.</span><span class="sxs-lookup"><span data-stu-id="93b7a-107">In addition, the proxy creates additional members to help call the method asynchronously.</span></span> <span data-ttu-id="93b7a-108">Для каждой функции веб-службы *NameOfWebServiceFunction* прокси-сервер создает подпрограмму *NameOfWebServiceFunction*`Async`, событие *NameOfWebServiceFunction*`Completed` и класс *NameOfWebServiceFunction*`CompletedEventArgs`.</span><span class="sxs-lookup"><span data-stu-id="93b7a-108">For each Web service function, *NameOfWebServiceFunction*, the proxy creates a *NameOfWebServiceFunction*`Async` subroutine, a *NameOfWebServiceFunction*`Completed` event, and a *NameOfWebServiceFunction*`CompletedEventArgs` class.</span></span> <span data-ttu-id="93b7a-109">В этом примере демонстрируется использование асинхронных элементов для получения доступа к функции `getTemp` веб-службы DemoTemperatureService.</span><span class="sxs-lookup"><span data-stu-id="93b7a-109">This example demonstrates how to use the asynchronous members to access the `getTemp` function of the DemoTemperatureService Web service.</span></span>

> [!NOTE]
> <span data-ttu-id="93b7a-110">Этот код не работает в веб-приложениях, так как ASP.NET не поддерживает объект `My.WebServices`.</span><span class="sxs-lookup"><span data-stu-id="93b7a-110">This code does not work in Web applications, because ASP.NET does not support the `My.WebServices` object.</span></span>

### <a name="to-call-a-web-service-asynchronously"></a><span data-ttu-id="93b7a-111">Асинхронный вызов веб-службы</span><span class="sxs-lookup"><span data-stu-id="93b7a-111">To call a Web service asynchronously</span></span>

1. <span data-ttu-id="93b7a-112">Справочные материалы по веб-службе DemoTemperatureService находятся на веб-сайте `http://www.xmethods.net`.</span><span class="sxs-lookup"><span data-stu-id="93b7a-112">Reference the DemoTemperatureService Web service at `http://www.xmethods.net`.</span></span> <span data-ttu-id="93b7a-113">Адрес:</span><span class="sxs-lookup"><span data-stu-id="93b7a-113">The address is</span></span>

    ```
    http://www.xmethods.net/sd/2001/DemoTemperatureService.wsdl
    ```

2. <span data-ttu-id="93b7a-114">Добавьте обработчик событий для события `getTempCompleted`.</span><span class="sxs-lookup"><span data-stu-id="93b7a-114">Add an event handler for the `getTempCompleted` event:</span></span>

    ```vb
    Private Sub getTempCompletedHandler(ByVal sender As Object,
        ByVal e As net.xmethods.www.getTempCompletedEventArgs)

        MsgBox("Temperature: " & e.Result)
    End Sub
    ```

    > [!NOTE]
    > <span data-ttu-id="93b7a-115">Оператор `Handles` нельзя использовать для сопоставления обработчика событий с событиями объекта `My.WebServices`.</span><span class="sxs-lookup"><span data-stu-id="93b7a-115">You cannot use the `Handles` statement to associate an event handler with the `My.WebServices` object's events.</span></span>

3. <span data-ttu-id="93b7a-116">Добавьте поле, которое будет отслеживать добавление к событию `getTempCompleted` обработчика событий.</span><span class="sxs-lookup"><span data-stu-id="93b7a-116">Add a field to track if the event handler has been added to the `getTempCompleted` event:</span></span>

    ```vb
    Private handlerAttached As Boolean = False
    ```

4. <span data-ttu-id="93b7a-117">При необходимости добавьте метод, который будет добавлять обработчик для события `getTempCompleted` и вызывать метод `getTempAsync`.</span><span class="sxs-lookup"><span data-stu-id="93b7a-117">Add a method to add the event handler to the `getTempCompleted` event, if necessary, and to call the `getTempAsync` method:</span></span>

    ```vb
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

    <span data-ttu-id="93b7a-118">Чтобы асинхронно вызвать веб-метод `getTemp`, вызовите метод `CallGetTempAsync`.</span><span class="sxs-lookup"><span data-stu-id="93b7a-118">To call the `getTemp` Web method asynchronously, call the `CallGetTempAsync` method.</span></span> <span data-ttu-id="93b7a-119">После своего завершения веб-метод вернет значение, переданное обработчику событий `getTempCompletedHandler`.</span><span class="sxs-lookup"><span data-stu-id="93b7a-119">When the Web method finishes, its return value is passed to the `getTempCompletedHandler` event handler.</span></span>

## <a name="see-also"></a><span data-ttu-id="93b7a-120">См. также</span><span class="sxs-lookup"><span data-stu-id="93b7a-120">See also</span></span>

- [<span data-ttu-id="93b7a-121">Доступ к веб-службам приложения</span><span class="sxs-lookup"><span data-stu-id="93b7a-121">Accessing Application Web Services</span></span>](../../../visual-basic/developing-apps/programming/accessing-application-web-services.md)
- [<span data-ttu-id="93b7a-122">Объект My.WebServices</span><span class="sxs-lookup"><span data-stu-id="93b7a-122">My.WebServices Object</span></span>](../../../visual-basic/language-reference/objects/my-webservices-object.md)
