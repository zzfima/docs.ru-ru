---
title: Другой журнал событий уже зарегистрировал источник с таким именем
ms.date: 07/20/2015
ms.assetid: e6f5cd95-bb3f-4845-84fb-ae623a9bd44e
ms.openlocfilehash: d932869504b2d8a5f3a948b190e5528bfcfa664f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61940619"
---
# <a name="another-event-log-has-already-registered-a-source-with-this-name"></a>Другой журнал событий уже зарегистрировал источник с таким именем
Предпринята попытка выполнить запись в журнал событий, когда указанный источник уже зарегистрирован другим журналом событий.  
  
 Перед внесением компонента записи в журнал необходимо задать свойство <xref:System.Diagnostics.EventLog.Source%2A> вашего экземпляра компонента <xref:System.Diagnostics.EventLog> . В этом случае система проверяет, что указанный источник зарегистрирован в журнале событий, в который компонент осуществляет запись, и при необходимости вызывает <xref:System.Diagnostics.EventLog.CreateEventSource%2A> .  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1. Удалите связь источника с первым журналом с помощью метода <xref:System.Diagnostics.EventLog.DeleteEventSource%2A> или <xref:System.Diagnostics.EventLog.DeleteEventSource%2A> .  
  
2. Зарегистрируйте источник для нового журнала.  
  
## <a name="see-also"></a>См. также

- [My.Application.Log](xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.Log)
