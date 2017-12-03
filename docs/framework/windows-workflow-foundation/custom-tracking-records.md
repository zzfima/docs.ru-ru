---
title: "Пользовательские записи отслеживания"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 24284565-c68b-40bf-b7f1-e148d151a6fc
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5202f69ac3f5408091d73f2ae39f92659a991740
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="custom-tracking-records"></a>Пользовательские записи отслеживания
В этом разделе описывается создание настраиваемых записей отслеживания и их заполнение данными, создаваемыми вместе с записями.  
  
## <a name="emitting-custom-tracking-records"></a>Выдача пользовательских записей отслеживания  
 Пользовательские записи отслеживания могут выдаваться в действии кода, как показано в следующем примере.  
  
```  
protected override void Execute(CodeActivityContext context)  
{  
…  
            CustomTrackingRecord customRecord = new CustomTrackingRecord("CustomEmailSentEvent");  
            customRecord.Data.Add("SendTime", sendTime);  
            context.Track(customRecord);  
}  
```  
  
 <xref:System.Activities.Tracking.CustomTrackingRecord> выдается в действии кода с помощью вызова метода <xref:System.Activities.NativeActivityContext.Track%2A> в `ActvityContext`.  
  
## <a name="see-also"></a>См. также  
 [Наблюдение за Windows Server App Fabric](http://go.microsoft.com/fwlink/?LinkId=201273)  
 [Мониторинг приложений с](http://go.microsoft.com/fwlink/?LinkId=201275)
