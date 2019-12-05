---
title: Пользовательские записи отслеживания
ms.date: 03/30/2017
ms.assetid: 24284565-c68b-40bf-b7f1-e148d151a6fc
ms.openlocfilehash: 986f0350c24414d0ff960474445adf6ac3f39734
ms.sourcegitcommit: 32a575bf4adccc901f00e264f92b759ced633379
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/04/2019
ms.locfileid: "74802626"
---
# <a name="custom-tracking-records"></a>Пользовательские записи отслеживания

В этом разделе описывается создание настраиваемых записей отслеживания и их заполнение данными, создаваемыми вместе с записями.

## <a name="emitting-custom-tracking-records"></a>Выдача пользовательских записей отслеживания

Пользовательские записи отслеживания могут выдаваться в действии кода, как показано в следующем примере.

```csharp
protected override void Execute(CodeActivityContext context)
{
…
            CustomTrackingRecord customRecord = new CustomTrackingRecord("CustomEmailSentEvent");
            customRecord.Data.Add("SendTime", sendTime);
            context.Track(customRecord);
}
```

<xref:System.Activities.Tracking.CustomTrackingRecord> выдается в действии кода с помощью вызова метода <xref:System.Activities.NativeActivityContext.Track%2A> в `ActivityContext`.

## <a name="see-also"></a>См. также:

- [Мониторинг Windows Server App Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677251(v=azure.10))
- [Мониторинг приложений с помощью App Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677276(v=azure.10))
