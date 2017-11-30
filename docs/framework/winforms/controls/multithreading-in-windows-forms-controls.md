---
title: "Многопоточность в элементах управления Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BackgroundWorker component
- threading [Windows Forms], controls
ms.assetid: c311d652-0f26-45fa-bdcc-b1615d73ce4e
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: c4651ca9707dcf0fac2edea0f004275cfcf18cf2
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/22/2017
---
# <a name="multithreading-in-windows-forms-controls"></a>Многопоточность в элементах управления Windows Forms
Во многих приложениях можно сделать более быстрого реагирования пользовательского интерфейса (UI), выполнять длительные операции в другом потоке. Доступно несколько средств для многопоточности элементов управления Windows Forms, включая <xref:System.Threading> пространства имен, <xref:System.Windows.Forms.Control.BeginInvoke%2A?displayProperty=nameWithType> метода и `BackgroundWorker` компонента.  
  
> [!NOTE]
>  `BackgroundWorker` Компонент заменяет и расширяет его функциональные возможности <xref:System.Threading> пространства имен и <xref:System.Windows.Forms.Control.BeginInvoke%2A?displayProperty=nameWithType> метода; тем не менее, их можно сохранить для обратной совместимости и использования в будущем, при выборе. Дополнительные сведения см. в разделе [Общие сведения о компоненте BackgroundWorker](../../../../docs/framework/winforms/controls/backgroundworker-component-overview.md).  
  
## <a name="in-this-section"></a>Содержание  
 [Практическое руководство. Осуществление потокобезопасных вызовов элементов управления Windows Forms.](../../../../docs/framework/winforms/controls/how-to-make-thread-safe-calls-to-windows-forms-controls.md)  
 Описание способов обеспечения потокобезопасных вызовов элементов управления Windows Forms.  
  
 [Практическое руководство. Применение фонового потока для поиска файлов](../../../../docs/framework/winforms/controls/how-to-use-a-background-thread-to-search-for-files.md)  
 Показано, как использовать <xref:System.Threading> пространства имен и <xref:System.Windows.Forms.Control.BeginInvoke%2A> метод для поиска файлов асинхронно.  
  
## <a name="reference"></a>Ссылка  
 <xref:System.ComponentModel.BackgroundWorker>  
 Описание компонента, инкапсулирующего рабочий поток для асинхронных операций.  
  
 <xref:System.Media.SoundPlayer.LoadAsync%2A>  
 Описание способа асинхронной загрузки звука.  
  
 <xref:System.Windows.Forms.PictureBox.LoadAsync%2A>  
 Описание способа асинхронной загрузки изображения.  
  
## <a name="related-sections"></a>Связанные разделы  
 [Практическое руководство. Фоновое выполнение операции](../../../../docs/framework/winforms/controls/how-to-run-an-operation-in-the-background.md)  
 Описание способов выполнения длительной операции с <xref:System.ComponentModel.BackgroundWorker> компонента.  
  
 [Общие сведения о компоненте BackgroundWorker](../../../../docs/framework/winforms/controls/backgroundworker-component-overview.md)  
 Разделы, описывающие способы использования <xref:System.ComponentModel.BackgroundWorker> компонента для асинхронных операций.
