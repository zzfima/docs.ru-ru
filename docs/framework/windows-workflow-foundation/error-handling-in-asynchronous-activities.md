---
title: "Ошибка при обработке асинхронных действий | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: e8f8ce2b-50c9-4e44-b187-030e0cf30a5d
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# Ошибка при обработке асинхронных действий
Обеспечение обработки ошибок в <xref:System.Activities.AsyncCodeActivity> включает маршрутизацию ошибки в системе обратного вызова действия.В этом разделе описывается, как возвратить ошибку, вызванную в асинхронной операции, обратно в узел, используя образец действия SendMail.  
  
## Возвращение ошибки, вызванной в асинхронном действии, обратно на узел  
 Маршрутизация ошибки в асинхронной операции обратно на узел в образце действия SendMail включает следующие шаги.  
  
-   Добавьте свойство «Исключение» к классу `SendMailAsyncResult`.  
  
-   Скопируйте вызванную ошибку в это свойство в обработчике события `SendCompleted`.  
  
-   Создайте исключение в обработчике события `EndExecute`.  
  
 Ниже приведен конечный код.  
  
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