---
title: Ограничения компонента Timer в Windows Forms&#39;свойства Interval s
ms.date: 03/30/2017
helpviewer_keywords:
- timers [Windows Forms], event intervals
- Interval property [Windows Forms], limitations
- timers [Windows Forms], Windows-based
- Timer component [Windows Forms], limitations of Interval property
ms.assetid: 7e5fb513-77e7-4046-a8e8-aab94e61ca0f
ms.openlocfilehash: e5b9e7e43369913f0cdc9c7f2111bd4fe58675e6
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/02/2018
ms.locfileid: "43465659"
---
# <a name="limitations-of-the-windows-forms-timer-component39s-interval-property"></a>Ограничения компонента Timer в Windows Forms&#39;свойства Interval s
Windows Forms <xref:System.Windows.Forms.Timer> компонент имеет <xref:System.Windows.Forms.Timer.Interval%2A> свойство, которое указывает количество миллисекунд, которые проходят между событие одного таймера, а также следующие. Если компонент отключен, таймер для получения <xref:System.Windows.Forms.Timer.Tick> событий через приблизительно равные интервалы времени.  
  
 Этот компонент предназначен для работы в среде Windows Forms. Если вам требуется таймер, подходящий для серверной среды, см. раздел [Общие сведения о серверных таймерах](https://msdn.microsoft.com/library/adc0bc0a-a519-4812-bafc-fb9d1a5801fc).  
  
## <a name="the-interval-property"></a>Свойство «интервал»  
 <xref:System.Windows.Forms.Timer.Interval%2A> Свойство имеет несколько ограничений, которые следует учитывать при программировании <xref:System.Windows.Forms.Timer> компонента:  
  
-   Если приложение или другое приложение интенсивно потребляет системы — например длинные циклы, с большим объемом вычислений, или диска, сети или доступа к портам — приложение не может получить события таймера так часто, как <xref:System.Windows.Forms.Timer.Interval%2A> указывает свойство.  
  
-   Интервал истечет точно вовремя не гарантируется. Для обеспечения точности, таймер следует проверить системные часы, при необходимости, а не повторите для отслеживания накопленные временные внутренним образом.  
  
-   Точность <xref:System.Windows.Forms.Timer.Interval%2A> свойство указывается в миллисекундах. Некоторые компьютеры имеют счетчик высокого разрешения, более высокую точность разрешение. Доступность такого счетчика зависит от оборудования процессора компьютера. Дополнительные сведения см. в статье 172338 «Как для использования QueryPerformanceCounter для кода,» в базе знаний Майкрософт в http://support.microsoft.com.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.Timer>  
 [Компонент Timer](../../../../docs/framework/winforms/controls/timer-component-windows-forms.md)  
 [Общие сведения о компоненте Timer](../../../../docs/framework/winforms/controls/timer-component-overview-windows-forms.md)
