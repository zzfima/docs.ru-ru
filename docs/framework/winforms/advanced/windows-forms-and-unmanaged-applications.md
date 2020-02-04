---
title: Неуправляемые приложения
ms.date: 03/30/2017
helpviewer_keywords:
- ActiveX controls [Windows Forms]
- COM interop [Windows Forms], Windows Forms
- COM [Windows Forms]
- Windows Forms, unmanaged
- Windows Forms, interop
ms.assetid: 81bc100c-fa49-4614-85a6-0f7ab59eac8a
ms.openlocfilehash: 17dc20653d1628dfd460a9891e1b0a21c0ebecbd
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746364"
---
# <a name="windows-forms-and-unmanaged-applications"></a>Windows Forms и неуправляемые приложения
Приложения и элементы управления Windows Forms могут взаимодействовать с неуправляемыми приложениями, но с некоторыми оговорками. В следующих разделах описываются сценарии и конфигурации, которые поддерживаются и не поддерживаются элементами управления и приложениями Windows Forms.  
  
## <a name="in-this-section"></a>в этом разделе  
 [Общие сведения о Windows Forms и неуправляемых приложениях](windows-forms-and-unmanaged-applications-overview.md)  
 Общие сведения о том, как использовать и реализовывать элементы управления Windows Forms, которые работают с неуправляемыми приложениями.  
  
 [Практическое руководство. Поддержка COM-взаимодействия путем отображения формы Windows Forms с помощью метода ShowDialog](com-interop-by-displaying-a-windows-form-shadow.md)  
 Пример кода, который демонстрирует использование метода <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> для запуска формы Windows Forms в неуправляемом приложении.  
  
 [How to: Support COM Interop by Displaying Each Windows Form on Its Own Thread](how-to-support-com-interop-by-displaying-each-windows-form-on-its-own-thread.md)  
 Пример кода, демонстрирующий выполнение формы Windows Forms в отдельном потоке.  
  
 См. также [Пошаговое руководство. Поддержка COM-взаимодействия путем отображения каждой формы Windows Forms в отдельном потоке](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms233639(v=vs.100)).  
  
## <a name="reference"></a>Справочник  
 <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType>  
 Используется для создания отдельного потока для формы Windows Forms.  
  
 <xref:System.Windows.Forms.Application.Run%2A?displayProperty=nameWithType>  
 Запускает цикл сообщений для потока.  
  
 <xref:System.Windows.Forms.Control.Invoke%2A>  
 Выполняет маршалинг вызовов из неуправляемого приложения в форму.  
  
## <a name="related-sections"></a>См. также  
 [Предоставление компонентов .NET Framework клиентам COM](../../interop/exposing-dotnet-components-to-com.md)  
 Общие сведения об использовании типов .NET Framework в неуправляемых приложениях.
