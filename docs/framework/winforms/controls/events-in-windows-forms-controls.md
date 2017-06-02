---
title: "События элементов управления Windows Forms | Microsoft Docs"
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
  - "пользовательские элементы управления [Windows Forms], общие сведения о событиях (с использованием кода)"
  - "события [Windows Forms], пользовательские элементы управления (с использованием кода)"
ms.assetid: 7e3d1379-87aa-437c-afce-c99454eff30e
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# События элементов управления Windows Forms
Элемент управления Windows Forms наследует более шестидесяти событий элемента управления <xref:System.Windows.Forms.Control?displayProperty=fullName>.  Это такие события как <xref:System.Windows.Forms.Control.Paint>, которое отвечает за рисование элемента управления; события, связанные с отображением окна, например <xref:System.Windows.Forms.Control.Resize> и <xref:System.Windows.Forms.Control.Layout>, а также события мыши и клавиатуры низкого уровня.  Некоторые низкоуровневые события синтезируются элементом управления <xref:System.Windows.Forms.Control> в семантические события, такие как <xref:System.Windows.Forms.Control.Click> и <xref:System.Windows.Forms.Control.DoubleClick>.  Подробные сведения о наследуемых событиях см. в разделе <xref:System.Windows.Forms.Control>.  
  
 Если для пользовательского элемента управления требуется переопределение функциональности наследуемых событий, переопределите наследуемый метод `On`*EventName* вместо прикрепления делегата.  Сведения о модели событий в платформе .NET Framework см. в разделе [Raising Events from a Component](../Topic/Raising%20Events%20from%20a%20Component.md).  
  
## См. также  
 [Переопределение метода OnPaint](../../../../docs/framework/winforms/controls/overriding-the-onpaint-method.md)   
 [Обработка введенных пользователем данных](../../../../docs/framework/winforms/controls/handling-user-input.md)   
 [Определение событий](../../../../docs/framework/winforms/controls/defining-an-event-in-windows-forms-controls.md)   
 [События](../../../../docs/standard/events/index.md)