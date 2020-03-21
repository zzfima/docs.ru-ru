---
title: Ошибка при обработке асинхронных действий
ms.date: 03/30/2017
ms.assetid: e8f8ce2b-50c9-4e44-b187-030e0cf30a5d
ms.openlocfilehash: c63ce231687b03bdba57edd38c32270eabeff834
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182954"
---
# <a name="error-handling-in-asynchronous-activities"></a><span data-ttu-id="62042-102">Ошибка при обработке асинхронных действий</span><span class="sxs-lookup"><span data-stu-id="62042-102">Error handling in asynchronous activities</span></span>
<span data-ttu-id="62042-103">Обеспечение обработки ошибок в <xref:System.Activities.AsyncCodeActivity> включает маршрутизацию ошибки в системе обратного вызова действия.</span><span class="sxs-lookup"><span data-stu-id="62042-103">Providing error handling in an <xref:System.Activities.AsyncCodeActivity> involves routing the error through the activity’s callback system.</span></span> <span data-ttu-id="62042-104">В этом разделе описывается, как возвратить ошибку, вызванную в асинхронной операции, обратно в узел, используя образец действия SendMail.</span><span class="sxs-lookup"><span data-stu-id="62042-104">This topic describes how to get an error that is thrown in an asynchronous operation back to the host, using the SendMail activity sample.</span></span>  
  
## <a name="returning-an-error-thrown-in-an-asynchronous-activity-back-to-the-host"></a><span data-ttu-id="62042-105">Возвращение ошибки, вызванной в асинхронном действии, обратно на узел</span><span class="sxs-lookup"><span data-stu-id="62042-105">Returning an error thrown in an asynchronous activity back to the host</span></span>  
 <span data-ttu-id="62042-106">Маршрутизация ошибки в асинхронной операции обратно на узел в образце действия SendMail включает следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="62042-106">Routing an error in an asynchronous operation back to the host in the SendMail activity sample involves the following steps:</span></span>  
  
- <span data-ttu-id="62042-107">Добавьте свойство Exception к классу `SendMailAsyncResult`.</span><span class="sxs-lookup"><span data-stu-id="62042-107">Add an Exception property to the `SendMailAsyncResult` class.</span></span>  
  
- <span data-ttu-id="62042-108">Скопируйте вызванную ошибку в это свойство в обработчике событий `SendCompleted`.</span><span class="sxs-lookup"><span data-stu-id="62042-108">Copy the thrown error to that property in the `SendCompleted` event handler.</span></span>  
  
- <span data-ttu-id="62042-109">Создайте исключение в обработчике событий `EndExecute`.</span><span class="sxs-lookup"><span data-stu-id="62042-109">Throw the exception in the `EndExecute` event handler.</span></span>  
  
 <span data-ttu-id="62042-110">Ниже приведен конечный код.</span><span class="sxs-lookup"><span data-stu-id="62042-110">The resulting code is as follows.</span></span>  
  
```csharp  
class SendMailAsyncResult : IAsyncResult  
        {  
            …  
            public Exception Error { get; set; }
            …  
            void SendCompleted(object sender, AsyncCompletedEventArgs e)  
            {  
                Error = e.Error;  
                this.asyncWaitHandle.Set();  
                callback(this);  
            }  
         }  
  
    public sealed class SendMail: AsyncCodeActivity  
    {  
         …  
        protected override void EndExecute(AsyncCodeActivityContext context, IAsyncResult result)  
        {  
            SendMailAsyncResult sendMailResult = result as SendMailAsyncResult;  
            if (sendMailResult != null && sendMailResult.Error != null)  
                throw sendMailResult.Error;
        }  
    }  
```
