---
title: Пользовательские записи отслеживания
ms.date: 03/30/2017
ms.assetid: 24284565-c68b-40bf-b7f1-e148d151a6fc
ms.openlocfilehash: 6c68c08e5beacee30b517bf0c2bad3e83785409b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="custom-tracking-records"></a><span data-ttu-id="c0ac1-102">Пользовательские записи отслеживания</span><span class="sxs-lookup"><span data-stu-id="c0ac1-102">Custom Tracking Records</span></span>
<span data-ttu-id="c0ac1-103">В этом разделе описывается создание настраиваемых записей отслеживания и их заполнение данными, создаваемыми вместе с записями.</span><span class="sxs-lookup"><span data-stu-id="c0ac1-103">This topic demonstrates how to create custom tracking records and populate them with data to be emitted along with the records.</span></span>  
  
## <a name="emitting-custom-tracking-records"></a><span data-ttu-id="c0ac1-104">Выдача пользовательских записей отслеживания</span><span class="sxs-lookup"><span data-stu-id="c0ac1-104">Emitting Custom Tracking Records</span></span>  
 <span data-ttu-id="c0ac1-105">Пользовательские записи отслеживания могут выдаваться в действии кода, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="c0ac1-105">Custom tracking records can be emitted from a code activity as shown in the following example.</span></span>  
  
```  
protected override void Execute(CodeActivityContext context)  
{  
…  
            CustomTrackingRecord customRecord = new CustomTrackingRecord("CustomEmailSentEvent");  
            customRecord.Data.Add("SendTime", sendTime);  
            context.Track(customRecord);  
}  
```  
  
 <span data-ttu-id="c0ac1-106"><xref:System.Activities.Tracking.CustomTrackingRecord> выдается в действии кода с помощью вызова метода <xref:System.Activities.NativeActivityContext.Track%2A> в `ActvityContext`.</span><span class="sxs-lookup"><span data-stu-id="c0ac1-106">A <xref:System.Activities.Tracking.CustomTrackingRecord> is emitted in a code activity by invoking the <xref:System.Activities.NativeActivityContext.Track%2A> method on the `ActvityContext`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0ac1-107">См. также</span><span class="sxs-lookup"><span data-stu-id="c0ac1-107">See Also</span></span>  
 [<span data-ttu-id="c0ac1-108">Наблюдение за Windows Server App Fabric</span><span class="sxs-lookup"><span data-stu-id="c0ac1-108">Windows Server App Fabric Monitoring</span></span>](http://go.microsoft.com/fwlink/?LinkId=201273)  
 [<span data-ttu-id="c0ac1-109">Мониторинг приложений с</span><span class="sxs-lookup"><span data-stu-id="c0ac1-109">Monitoring Applications with App Fabric</span></span>](http://go.microsoft.com/fwlink/?LinkId=201275)
