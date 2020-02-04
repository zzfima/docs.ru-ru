---
title: Ограничения свойства интервала компонента Timer
ms.date: 03/30/2017
helpviewer_keywords:
- timers [Windows Forms], event intervals
- Interval property [Windows Forms], limitations
- timers [Windows Forms], Windows-based
- Timer component [Windows Forms], limitations of Interval property
ms.assetid: 7e5fb513-77e7-4046-a8e8-aab94e61ca0f
ms.openlocfilehash: 15626a53f0541ff79e2098377d9dfdb4626ac155
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745230"
---
# <a name="limitations-of-the-windows-forms-timer-components-interval-property"></a>Ограничения свойства Interval компонента Timer в Windows Forms
Компонент Windows Forms <xref:System.Windows.Forms.Timer> имеет свойство <xref:System.Windows.Forms.Timer.Interval%2A>, которое указывает количество миллисекунд, прошедших между одним событием таймера и следующим. Если компонент не отключен, таймер будет продолжать принимать <xref:System.Windows.Forms.Timer.Tick> событие с приблизительно равным интервалом времени.  
  
 Этот компонент предназначен для работы в среде Windows Forms. Если вам требуется таймер, подходящий для серверной среды, см. раздел [Общие сведения о серверных таймерах](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/tb9yt5e6(v=vs.90)).  
  
## <a name="the-interval-property"></a>Свойство Interval  
 Свойство <xref:System.Windows.Forms.Timer.Interval%2A> имеет несколько ограничений, которые следует учитывать при программировании компонента <xref:System.Windows.Forms.Timer>.  
  
- Если приложение или другое приложение выполняет значительные требования к системе (например, длинные циклы, ресурсоемкие вычисления или доступ к диску, сети или портам), приложение может не получить события таймера так часто, как указано в свойстве <xref:System.Windows.Forms.Timer.Interval%2A>.  
  
- Не гарантируется, что интервал будет находиться в точном времени. Для обеспечения точности таймер должен проверять системные часы по мере необходимости, а не пытаться следить за накопленным временем на внутреннем уровне.  
  
- Точность свойства <xref:System.Windows.Forms.Timer.Interval%2A> задается в миллисекундах. Некоторые компьютеры предоставляют счетчик высокого разрешения с разрешением выше миллисекунд. Доступность такого счетчика зависит от аппаратного процессора компьютера.
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Forms.Timer>
- [Компонент Timer](timer-component-windows-forms.md)
- [Общие сведения о компоненте Timer](timer-component-overview-windows-forms.md)
