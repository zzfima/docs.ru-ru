---
title: "Многопоточность в элементах управления Windows Forms | Microsoft Docs"
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
  - "BackgroundWorker - компонент"
  - "BeginInvoke - метод"
  - "работа с потоками [Windows Forms], элементы управления"
ms.assetid: c311d652-0f26-45fa-bdcc-b1615d73ce4e
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# Многопоточность в элементах управления Windows Forms
Во многих приложениях можно добиться лучшей реакции пользовательского интерфейса, если выполнять длительные операции в отдельном потоке.  Для разделения элементов управления Windows Forms на потоки существует несколько средств, среди которых пространство имен <xref:System.Threading>, метод <xref:System.Windows.Forms.Control.BeginInvoke%2A?displayProperty=fullName> и компонент `BackgroundWorker`.  
  
> [!NOTE]
>  Компонент `BackgroundWorker` заменяет пространство имен <xref:System.Threading> и метод <xref:System.Windows.Forms.Control.BeginInvoke%2A?displayProperty=fullName> и расширяет их функциональные возможности; однако при необходимости это пространство имен и метод можно сохранить для обратной совместимости и использования в будущем.  Дополнительные сведения см. в разделе [Общие сведения о компоненте BackgroundWorker](../../../../docs/framework/winforms/controls/backgroundworker-component-overview.md).  
  
## В этом подразделе  
 [Практическое руководство. Осуществление потокобезопасных вызовов элементов управления Windows Forms.](../../../../docs/framework/winforms/controls/how-to-make-thread-safe-calls-to-windows-forms-controls.md)  
 Показано, как осуществлять потокобезопасные вызовы элементов управления Windows Forms.  
  
 [Практическое руководство. Применение фонового потока для поиска файлов](../../../../docs/framework/winforms/controls/how-to-use-a-background-thread-to-search-for-files.md)  
 Показано, как использовать пространство имен <xref:System.Threading> и метод <xref:System.Windows.Forms.Control.BeginInvoke%2A> для асинхронного поиска файлов.  
  
## Ссылка  
 <xref:System.ComponentModel.BackgroundWorker>  
 Описание компонента, инкапсулирующего рабочий поток для асинхронных операций.  
  
 <xref:System.Media.SoundPlayer.LoadAsync%2A>  
 Описание способа асинхронной загрузки звукового объекта.  
  
 <xref:System.Windows.Forms.PictureBox.LoadAsync%2A>  
 Описание способа асинхронной загрузки изображения.  
  
## Связанные подразделы  
 [Практическое руководство. Фоновое выполнение операции](../../../../docs/framework/winforms/controls/how-to-run-an-operation-in-the-background.md)  
 Показано, как выполнять длительную операцию с компонентом <xref:System.ComponentModel.BackgroundWorker>.  
  
 [Общие сведения о компоненте BackgroundWorker](../../../../docs/framework/winforms/controls/backgroundworker-component-overview.md)  
 Разделы по использованию компонента <xref:System.ComponentModel.BackgroundWorker> для асинхронных операций.