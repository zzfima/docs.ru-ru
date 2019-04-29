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

## <a name="see-also"></a>См. также

- [Мониторинг Windows Server App Fabric](https://go.microsoft.com/fwlink/?LinkId=201273)
- [Мониторинг приложений с помощью фабрики приложения](https://go.microsoft.com/fwlink/?LinkId=201275)
