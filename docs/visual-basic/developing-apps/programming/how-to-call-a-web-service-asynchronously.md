---
title: Практическое руководство. Асинхронный вызов веб-службы
ms.date: 07/20/2015
helpviewer_keywords:
- asynchronous calls [Visual Basic]
- Web services [Visual Basic], accessing
ms.assetid: ff8046f4-f1f2-4d8b-90b7-95e3f7415418
ms.openlocfilehash: d288cc1f2991a8f504dc9f1b206bba76fa378b75
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794553"
---
# <a name="how-to-call-a-web-service-asynchronously-visual-basic"></a>Практическое руководство. Асинхронный вызов веб-службы (Visual Basic)

В этом примере обработчик присоединяется к асинхронному обработчику событий веб-службы таким образом, чтобы получать результаты вызова асинхронного метода. В этом примере используется веб-служба DemoTemperatureService, которая находится на веб-сайте `http://www.xmethods.net`.

При ссылке на веб-службу в проекте в интегрированной среде разработки Visual Studio (IDE) она добавляется к объекту `My.WebServices`, а среда IDE создает класс прокси клиента, чтобы получить доступ к указанной веб-службе.

Класс прокси позволяет синхронно вызывать методы веб-службы в те моменты, когда приложение ожидает завершения выполнения функции. Кроме того, прокси-сервер создает дополнительные элементы для обеспечения асинхронного вызова метода. Для каждой функции веб-службы *NameOfWebServiceFunction* прокси-сервер создает подпрограмму *NameOfWebServiceFunction*`Async`, событие *NameOfWebServiceFunction*`Completed` и класс *NameOfWebServiceFunction*`CompletedEventArgs`. В этом примере демонстрируется использование асинхронных элементов для получения доступа к функции `getTemp` веб-службы DemoTemperatureService.

> [!NOTE]
> Этот код не работает в веб-приложениях, так как ASP.NET не поддерживает объект `My.WebServices`.

## <a name="call-a-web-service-asynchronously"></a>Асинхронный вызов веб-службы

1. Справочные материалы по веб-службе DemoTemperatureService находятся на веб-сайте `http://www.xmethods.net`. Адрес:

    ```http
    http://www.xmethods.net/sd/2001/DemoTemperatureService.wsdl
    ```

2. Добавьте обработчик событий для события `getTempCompleted`.

    ```vb
    Private Sub getTempCompletedHandler(ByVal sender As Object,
        ByVal e As net.xmethods.www.getTempCompletedEventArgs)

        MsgBox("Temperature: " & e.Result)
    End Sub
    ```

    > [!NOTE]
    > Оператор `Handles` нельзя использовать для сопоставления обработчика событий с событиями объекта `My.WebServices`.

3. Добавьте поле, которое будет отслеживать добавление к событию `getTempCompleted` обработчика событий.

    ```vb
    Private handlerAttached As Boolean = False
    ```

4. При необходимости добавьте метод, который будет добавлять обработчик для события `getTempCompleted` и вызывать метод `getTempAsync`.

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

    Чтобы асинхронно вызвать веб-метод `getTemp`, вызовите метод `CallGetTempAsync`. После своего завершения веб-метод вернет значение, переданное обработчику событий `getTempCompletedHandler`.

## <a name="see-also"></a>См. также

- [Доступ к веб-службам приложения](accessing-application-web-services.md)
- [Объект My.WebServices](../../language-reference/objects/my-webservices-object.md)
