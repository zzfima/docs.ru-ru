---
title: Пользовательские записи отслеживания
ms.date: 03/30/2017
ms.assetid: 24284565-c68b-40bf-b7f1-e148d151a6fc
ms.openlocfilehash: d4733b4ffc0d866cf90fd5a5e7d649de261c45fb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61945838"
---
# <a name="custom-tracking-records"></a><span data-ttu-id="f9f19-102">Пользовательские записи отслеживания</span><span class="sxs-lookup"><span data-stu-id="f9f19-102">Custom Tracking Records</span></span>

<span data-ttu-id="f9f19-103">В этом разделе описывается создание настраиваемых записей отслеживания и их заполнение данными, создаваемыми вместе с записями.</span><span class="sxs-lookup"><span data-stu-id="f9f19-103">This topic demonstrates how to create custom tracking records and populate them with data to be emitted along with the records.</span></span>

## <a name="emitting-custom-tracking-records"></a><span data-ttu-id="f9f19-104">Выдача пользовательских записей отслеживания</span><span class="sxs-lookup"><span data-stu-id="f9f19-104">Emitting Custom Tracking Records</span></span>

<span data-ttu-id="f9f19-105">Пользовательские записи отслеживания могут выдаваться в действии кода, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="f9f19-105">Custom tracking records can be emitted from a code activity as shown in the following example.</span></span>

```csharp
protected override void Execute(CodeActivityContext context)
{
…
            CustomTrackingRecord customRecord = new CustomTrackingRecord("CustomEmailSentEvent");
            customRecord.Data.Add("SendTime", sendTime);
            context.Track(customRecord);
}
```

<span data-ttu-id="f9f19-106"><xref:System.Activities.Tracking.CustomTrackingRecord> выдается в действии кода с помощью вызова метода <xref:System.Activities.NativeActivityContext.Track%2A> в `ActivityContext`.</span><span class="sxs-lookup"><span data-stu-id="f9f19-106">A <xref:System.Activities.Tracking.CustomTrackingRecord> is emitted in a code activity by invoking the <xref:System.Activities.NativeActivityContext.Track%2A> method on the `ActivityContext`.</span></span>

## <a name="see-also"></a><span data-ttu-id="f9f19-107">См. также</span><span class="sxs-lookup"><span data-stu-id="f9f19-107">See also</span></span>

- [<span data-ttu-id="f9f19-108">Мониторинг Windows Server App Fabric</span><span class="sxs-lookup"><span data-stu-id="f9f19-108">Windows Server App Fabric Monitoring</span></span>](https://go.microsoft.com/fwlink/?LinkId=201273)
- [<span data-ttu-id="f9f19-109">Мониторинг приложений с помощью фабрики приложения</span><span class="sxs-lookup"><span data-stu-id="f9f19-109">Monitoring Applications with App Fabric</span></span>](https://go.microsoft.com/fwlink/?LinkId=201275)
