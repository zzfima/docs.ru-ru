---
title: Многопоточность в элементах управления
ms.date: 03/30/2017
helpviewer_keywords:
- BackgroundWorker component
- threading [Windows Forms], controls
ms.assetid: c311d652-0f26-45fa-bdcc-b1615d73ce4e
ms.openlocfilehash: 79832e12a10f02c909d2a28270594bcb4ea68656
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742139"
---
# <a name="multithreading-in-windows-forms-controls"></a>Многопоточность в элементах управления Windows Forms
Во многих приложениях можно сделать пользовательский интерфейс более быстрым, выполняя длительные операции в другом потоке. Для многопоточности можно использовать ряд средств для управления Windows Forms, включая пространство имен <xref:System.Threading>, метод <xref:System.Windows.Forms.Control.BeginInvoke%2A?displayProperty=nameWithType> и компонент `BackgroundWorker`.  
  
> [!NOTE]
> Компонент `BackgroundWorker` заменяет и добавляет функции в пространство имен <xref:System.Threading> и метод <xref:System.Windows.Forms.Control.BeginInvoke%2A?displayProperty=nameWithType>. Однако они сохраняются для обратной совместимости и использования в будущем, если вы решили. Дополнительные сведения см. в разделе [Общие сведения о компоненте BackgroundWorker](backgroundworker-component-overview.md).  
  
## <a name="in-this-section"></a>В этом разделе  
 [Практическое руководство. Осуществление потокобезопасных вызовов элементов управления Windows Forms.](how-to-make-thread-safe-calls-to-windows-forms-controls.md)  
 Показывает, как выполнять потокобезопасные вызовы элементов управления Windows Forms.  
  
 [Практическое руководство. Применение фонового потока для поиска файлов](how-to-use-a-background-thread-to-search-for-files.md)  
 Показывает, как использовать пространство имен <xref:System.Threading> и метод <xref:System.Windows.Forms.Control.BeginInvoke%2A> для асинхронного поиска файлов.  
  
## <a name="reference"></a>Справочные сведения  
 <xref:System.ComponentModel.BackgroundWorker>  
 Документирует компонент, инкапсулирующий рабочий поток для асинхронных операций.  
  
 <xref:System.Media.SoundPlayer.LoadAsync%2A>  
 Документация по асинхронной загрузке звука.  
  
 <xref:System.Windows.Forms.PictureBox.LoadAsync%2A>  
 Документация по асинхронной загрузке изображения.  
  
## <a name="related-sections"></a>Связанные разделы  
 [Практическое руководство. Фоновое выполнение операции](how-to-run-an-operation-in-the-background.md)  
 Показывает, как выполнить трудоемкую операцию с компонентом <xref:System.ComponentModel.BackgroundWorker>.  
  
 [Общие сведения о компоненте BackgroundWorker](backgroundworker-component-overview.md)  
 Содержит разделы, в которых описывается использование компонента <xref:System.ComponentModel.BackgroundWorker> для асинхронных операций.
