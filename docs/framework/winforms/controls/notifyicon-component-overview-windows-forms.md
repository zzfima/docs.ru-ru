---
title: "Общие сведения о компоненте NotifyIcon (Windows Forms) | Microsoft Docs"
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
  - "NotifyIcon"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "NotifyIcon - компонент, сведения о компоненте NotifyIcon"
  - "значки в панели задач, сведения о значках в панели задач"
  - "значки в панели задач, использование в Windows Forms"
ms.assetid: 5b9189fa-d4ae-41a6-9b97-eb1f44bb1a69
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Общие сведения о компоненте NotifyIcon (Windows Forms)
Компонент <xref:System.Windows.Forms.NotifyIcon> Windows Forms обычно используется для отображения значков процессов, выполняемых в фоновом режиме и большую часть времени не выводящих пользовательский интерфейс.  Примером такого процесса является антивирусная программа, доступ к которой можно получить, щелкнув значок в области уведомлений о состоянии на панели задач.  
  
## Основные свойства компонентов NotifyIcon  
 Каждый компонент <xref:System.Windows.Forms.NotifyIcon> выводит один значок в области состояния.  Если для каждого из трех процессов, выполняемых в фоновом режиме, нужно показывать значок, добавьте три компонента <xref:System.Windows.Forms.NotifyIcon> в форму.  Основные свойства компонента <xref:System.Windows.Forms.NotifyIcon> — это <xref:System.Windows.Forms.NotifyIcon.Icon%2A> и <xref:System.Windows.Forms.NotifyIcon.Visible%2A>.  Свойство <xref:System.Windows.Forms.NotifyIcon.Icon%2A> определяет значок, отображающийся в области состояния.  Чтобы значок отображался, необходимо присвоить свойству <xref:System.Windows.Forms.NotifyIcon.Visible%2A> значение `true`.  
  
 При использовании [!INCLUDE[vsprvslong](../../../../includes/vsprvslong-md.md)] вы получаете доступ к большой библиотеке стандартных изображений, которые можно использовать с элементом управления <xref:System.Windows.Forms.NotifyIcon>.  
  
## Параметры компонентов NotifyIcon  
 Для упрощения работы пользователя можно связать всплывающие подсказки, сообщения и контекстные меню с <xref:System.Windows.Forms.NotifyIcon>.  
  
 Чтобы показать всплывающую подсказку для <xref:System.Windows.Forms.NotifyIcon>, вызовите метод <xref:System.Windows.Forms.NotifyIcon.ShowBalloonTip%2A>, указав длительность отображения подсказки.  Также можно указать текст, значок и заголовок подсказки с помощью свойств <xref:System.Windows.Forms.NotifyIcon.BalloonTipText%2A>, <xref:System.Windows.Forms.NotifyIcon.BalloonTipIcon%2A> и <xref:System.Windows.Forms.NotifyIcon.BalloonTipTitle%2A> соответственно.  Компоненты <xref:System.Windows.Forms.NotifyIcon> также могут иметь связанные всплывающие подсказки и контекстные меню.  Подробнее см. в разделах [Общие сведения об элементе управления ToolTip](../../../../docs/framework/winforms/controls/tooltip-component-overview-windows-forms.md) и [Общие сведения об элементе управления ContextMenu](../../../../docs/framework/winforms/controls/contextmenu-component-overview-windows-forms.md).  
  
## См. также  
 <xref:System.Windows.Forms.NotifyIcon>   
 [Компонент NotifyIcon](../../../../docs/framework/winforms/controls/notifyicon-component-windows-forms.md)