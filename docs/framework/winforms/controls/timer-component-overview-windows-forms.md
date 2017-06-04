---
title: "Общие сведения о компоненте Timer (Windows Forms) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "Timer"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Timer - компонент [Windows Forms], сведения о компонентах Timer"
  - "таймеры, о таймерах"
ms.assetid: e672c05b-a8b6-4b26-9e4d-9223aa9e3873
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Общие сведения о компоненте Timer (Windows Forms)
Компонент Windows Forms <xref:System.Windows.Forms.Timer> вызывает событие через определенные интервалы времени.  Этот компонент предназначен для среды Windows Forms.  Если требуется таймер для серверной среды, см. раздел [Introduction to Server\-Based Timers](http://msdn.microsoft.com/ru-ru/adc0bc0a-a519-4812-bafc-fb9d1a5801fc).  
  
## Ключевые свойства, методы и события  
 Длина интервалов определяется свойством <xref:System.Windows.Forms.Timer.Interval%2A>, значение которого исчисляется в миллисекундах.  Когда компонент включен, событие <xref:System.Windows.Forms.Timer.Tick> вызывается через каждый интервал.  В этом месте следует добавить выполняемый код.  Дополнительные сведения см. в разделе [Выполнение операций с заданной периодичностью с помощью компонента Timer в Windows Forms](../../../../docs/framework/winforms/controls/run-procedures-at-set-intervals-with-wf-timer-component.md).  \<\]Ключевыми методами компонента <xref:System.Windows.Forms.Timer> являются <xref:System.Windows.Forms.Timer.Start%2A> и <xref:System.Windows.Forms.Timer.Stop%2A>, которые включают и выключают таймер.  При выключении таймера его параметры сбрасываются; приостановить компонент <xref:System.Windows.Forms.Timer> нельзя.  
  
## См. также  
 <xref:System.Windows.Forms.Timer>   
 [Компонент Timer](../../../../docs/framework/winforms/controls/timer-component-windows-forms.md)   
 [Ограничения свойства Interval компонента Timer в Windows Forms](../../../../docs/framework/winforms/controls/limitations-of-the-timer-component-interval-property.md)