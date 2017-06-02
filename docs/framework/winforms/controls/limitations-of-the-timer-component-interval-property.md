---
title: "Ограничения свойства Interval компонента Timer в Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Interval - свойство, ограничения"
  - "Timer - компонент [Windows Forms], ограничения свойства Interval"
  - "таймеры, интервалы событий"
  - "таймеры, для Windows"
ms.assetid: 7e5fb513-77e7-4046-a8e8-aab94e61ca0f
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Ограничения свойства Interval компонента Timer в Windows Forms
Компонент Windows Forms <xref:System.Windows.Forms.Timer> имеет свойство <xref:System.Windows.Forms.Timer.Interval%2A>, указывающее время в миллисекундах, которое проходит между двумя следующими друг за другом событиями таймера.  Если компонент не отключен, таймер получает событие <xref:System.Windows.Forms.Timer.Tick> через приблизительно равные интервалы времени.  
  
 Этот компонент предназначен для среды Windows Forms.  Если требуется таймер для серверной среды, см. раздел [Introduction to Server\-Based Timers](http://msdn.microsoft.com/ru-ru/adc0bc0a-a519-4812-bafc-fb9d1a5801fc).  
  
## Свойство Interval  
 Свойство <xref:System.Windows.Forms.Timer.Interval%2A> имеет несколько ограничений, которые необходимо учитывать при программировании компонента <xref:System.Windows.Forms.Timer>.  
  
-   Если какое\-либо приложение интенсивно потребляет системные ресурсы \(например, использует длинные циклы, выполняет большие объемы вычислений или производит доступ к диску, сети или порту\), события таймера могут поступать не так часто, как указывается свойством <xref:System.Windows.Forms.Timer.Interval%2A>.  
  
-   Нет гарантии, что интервал истечет точно вовремя.  Чтобы обеспечить точность, таймер должен сверяться по мере необходимости с системными часами, а не пытаться отслеживать прошедшее время внутренними средствами.  
  
-   Точность свойства <xref:System.Windows.Forms.Timer.Interval%2A> измеряется миллисекундами.  Некоторые компьютеры имеют счетчики высокого разрешения, обеспечивающие более высокую точность.  Доступность такого счетчика определяется характеристиками компьютерного процессора.  Подробные сведения см. в статье 172338 базы знаний Майкрософт "How To Use QueryPerformanceCounter to Time Code" \(http:\/\/support.microsoft.com\).  
  
## См. также  
 <xref:System.Windows.Forms.Timer>   
 [Компонент Timer](../../../../docs/framework/winforms/controls/timer-component-windows-forms.md)   
 [Общие сведения о компоненте Timer](../../../../docs/framework/winforms/controls/timer-component-overview-windows-forms.md)