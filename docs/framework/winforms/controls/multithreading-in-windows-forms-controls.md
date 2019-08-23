---
title: Многопоточность в элементах управления Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- BackgroundWorker component
- threading [Windows Forms], controls
ms.assetid: c311d652-0f26-45fa-bdcc-b1615d73ce4e
ms.openlocfilehash: cf6790172b7445ad154eead5d17f8efddd78ffee
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69952682"
---
# <a name="multithreading-in-windows-forms-controls"></a>Многопоточность в элементах управления Windows Forms
Во многих приложениях можно сделать пользовательский интерфейс более быстрым, выполняя длительные операции в другом потоке. Существует ряд средств для многопоточности элементов управления Windows Forms, включая <xref:System.Threading> пространство имен <xref:System.Windows.Forms.Control.BeginInvoke%2A?displayProperty=nameWithType> , метод и `BackgroundWorker` компонент.  
  
> [!NOTE]
> Компонент заменяет и добавляет функции <xref:System.Threading> к пространству имен и <xref:System.Windows.Forms.Control.BeginInvoke%2A?displayProperty=nameWithType> методу. Однако они сохраняются для обратной совместимости и использования в будущем, если вы решили. `BackgroundWorker` Дополнительные сведения см. в разделе [Общие сведения о компоненте BackgroundWorker](backgroundworker-component-overview.md).  
  
## <a name="in-this-section"></a>В этом разделе  
 [Практическое руководство. Осуществление потокобезопасных вызовов элементов управления Windows Forms](how-to-make-thread-safe-calls-to-windows-forms-controls.md)  
 Показывает, как выполнять потокобезопасные вызовы элементов управления Windows Forms.  
  
 [Практическое руководство. Использовать фоновый поток для поиска файлов](how-to-use-a-background-thread-to-search-for-files.md)  
 Показывает, как использовать <xref:System.Threading> пространство имен <xref:System.Windows.Forms.Control.BeginInvoke%2A> и метод для асинхронного поиска файлов.  
  
## <a name="reference"></a>Ссылка  
 <xref:System.ComponentModel.BackgroundWorker>  
 Документирует компонент, инкапсулирующий рабочий поток для асинхронных операций.  
  
 <xref:System.Media.SoundPlayer.LoadAsync%2A>  
 Документация по асинхронной загрузке звука.  
  
 <xref:System.Windows.Forms.PictureBox.LoadAsync%2A>  
 Документация по асинхронной загрузке изображения.  
  
## <a name="related-sections"></a>Связанные разделы  
 [Практическое руководство. Фоновое выполнение операции](how-to-run-an-operation-in-the-background.md)  
 Показывает, как выполнить трудоемкую операцию с <xref:System.ComponentModel.BackgroundWorker> компонентом.  
  
 [Общие сведения о компоненте BackgroundWorker](backgroundworker-component-overview.md)  
 Содержит разделы, в которых описывается использование <xref:System.ComponentModel.BackgroundWorker> компонента для асинхронных операций.
