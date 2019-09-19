---
title: Практическое руководство. Запись сведений о службах в журнал
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- AutoLog property
- services, logging information
- Windows Service applications, logging information about
- event logs, service applications
- application event logs, service applications
- logs, service applications
ms.assetid: c0d8140f-c055-4d8e-a2e0-37358a550116
author: ghogen
ms.openlocfilehash: 3c974d5a98f8056e45899b109878e5a28ab2938e
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2019
ms.locfileid: "71053605"
---
# <a name="how-to-log-information-about-services"></a>Практическое руководство. Запись сведений о службах в журнал
По умолчанию все проекты служб Windows могут взаимодействовать с журналом событий приложения и записывать в него сведения и исключения. Чтобы указать, что эта функциональность должна быть в вашем приложении, можно использовать свойство <xref:System.ServiceProcess.ServiceBase.AutoLog%2A> . По умолчанию ведение журнала включено для любой службы, созданной с помощью шаблона проекта службы Windows. Можно использовать статическую форму класса <xref:System.Diagnostics.EventLog> для записи сведений в журнал, и тогда не потребуется создавать экземпляр компонента <xref:System.Diagnostics.EventLog> или вручную регистрировать источник.  
  
 Установщик службы автоматически регистрирует каждую службу в проекте как допустимый источник событий для журнала приложений на компьютере, где установлена служба, если включено ведение журнала. Служба записывает сведения каждый раз, когда служба запускается, останавливается, приостанавливается, возобновляется, устанавливается или удаляется. Она также записывает все возникающие ошибки. Вам не нужно писать никакой код для записи в журнал при использовании этого поведения по умолчанию; служба обрабатывает это автоматически.  
  
 Если вы хотите выполнять запись в другой журнал событий, отличный от журнала приложения, то необходимо задать для свойства <xref:System.ServiceProcess.ServiceBase.AutoLog%2A> значение `false`, создать собственный пользовательский журнал событий в коде службы и зарегистрировать службу в качестве источника записей для этого журнала. Затем вам придется написать код для выполнения записи в журнал всякий раз, когда происходит интересующее вас действие.  
  
> [!NOTE]
> Если вы используете пользовательский журнал событий и настроили службу для записи в этот журнал, не пытайтесь обратиться к этому журналу до установки свойства <xref:System.ServiceProcess.ServiceBase.ServiceName%2A> службы в коде. Журналу событий нужно значение этого свойства, чтобы зарегистрировать службу в качестве допустимого источника событий.  
  
### <a name="to-enable-default-event-logging-for-your-service"></a>Включение ведения журнала событий по умолчанию для службы  
  
- Установите для свойства <xref:System.ServiceProcess.ServiceBase.AutoLog%2A> вашего компонента значение `true`.  
  
    > [!NOTE]
    > По умолчанию для свойства задано значение `true`. Вам не нужно задавать это явно, если только вы не создаете более сложную обработку, такую как оценка условия и последующая установка свойства <xref:System.ServiceProcess.ServiceBase.AutoLog%2A> в зависимости от результата этого условия.  
  
### <a name="to-disable-event-logging-for-your-service"></a>Отключение ведения журнала событий для службы  
  
- Установите для свойства <xref:System.ServiceProcess.ServiceBase.AutoLog%2A> вашего компонента значение `false`.  
  
     [!code-csharp[VbRadconService#17](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#17)]
     [!code-vb[VbRadconService#17](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#17)]  
  
### <a name="to-set-up-logging-to-a-custom-log"></a>Настройка ведения пользовательского журнала  
  
1. Задайте для свойства <xref:System.ServiceProcess.ServiceBase.AutoLog%2A> значение `false`.  
  
    > [!NOTE]
    > Чтобы использовать пользовательский журнал, необходимо задать в свойстве <xref:System.ServiceProcess.ServiceBase.AutoLog%2A> значение false.  
  
2. Настройте экземпляр компонента <xref:System.Diagnostics.EventLog> в приложении службы Windows.  
  
3. Создайте пользовательский журнал, вызвав метод <xref:System.Diagnostics.EventLog.CreateEventSource%2A> и задав исходную строку и имя файла журнала, который хотите создать.  
  
4. Укажите в свойстве <xref:System.Diagnostics.EventLog.Source%2A> компонента <xref:System.Diagnostics.EventLog> исходную строку, созданную на шаге 3.  
  
5. Выполняйте запись в журнал, вызывая метод <xref:System.Diagnostics.EventLog.WriteEntry%2A> в экземпляре компонента <xref:System.Diagnostics.EventLog> .  
  
     Следующий код показывает, как настроить ведение пользовательского журнала.  
  
    > [!NOTE]
    > В этом примере кода экземпляр компонента <xref:System.Diagnostics.EventLog> называется `eventLog1` (`EventLog1` в Visual Basic). Если на шаге 2 вы создали экземпляр с другим именем, измените код соответствующим образом.  
  
     [!code-csharp[VbRadconService#14](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#14)]
     [!code-vb[VbRadconService#14](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#14)]  
    [!code-csharp[VbRadconService#15](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#15)]
    [!code-vb[VbRadconService#15](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#15)]  
  
## <a name="see-also"></a>См. также

- [Знакомство с приложениями служб Windows](introduction-to-windows-service-applications.md)
