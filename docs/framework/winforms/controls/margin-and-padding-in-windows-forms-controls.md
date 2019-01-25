---
title: Поля и заполнение в элементах управления Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- Padding property [Windows Forms]
- layout [Windows Forms], margins and padding
- Windows Forms, layout
- Margin property [Windows Forms]
ms.assetid: 3781b5a1-3085-4072-bed0-44670c23ffdc
ms.openlocfilehash: be5d1ae308b9412f914f1cde91d1cc5834212df8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54570555"
---
# <a name="margin-and-padding-in-windows-forms-controls"></a>Поля и заполнение в элементах управления Windows Forms
Точное расположение элементов управления на форме является важным для многих приложений. Пространство имен <xref:System.Windows.Forms?displayProperty=nameWithType> предоставляет множество возможностей компоновки для решения этой задачи. Свойства <xref:System.Windows.Forms.Control.Margin%2A> и <xref:System.Windows.Forms.Control.Padding%2A> — одни из наиболее важных.  
  
 Свойство <xref:System.Windows.Forms.Control.Margin%2A> определяет поле вокруг элемента управления, благодаря которому обеспечивается определенное расстояние между границами этого элемента и другими элементами.  
  
 Свойство <xref:System.Windows.Forms.Control.Padding%2A> определяет поле внутри элемента управления, благодаря которому обеспечивается определенное расстояние между содержимым элемента управления (например, значением свойства <xref:System.Windows.Forms.Control.Text%2A>) и его границами.  
  
 На рисунке ниже демонстрируется значение свойств <xref:System.Windows.Forms.Control.Padding%2A> и <xref:System.Windows.Forms.Control.Margin%2A> элемента управления.  
  
 ![И заполнение для Windows Forms элементы управления](../../../../docs/framework/winforms/controls/media/vs-winformpadmargin.gif "VS_WinFormPadMargin")  
  
 Эта возможность поддерживается во время разработки в Visual Studio.  Также см. в разделе [Пошаговое руководство: Размещение Windows Forms элементы управления с помощью свойств Padding, Margins и свойство AutoSize](https://msdn.microsoft.com/library/3z3f9e8b\(v=vs.110\)).  
  
## <a name="see-also"></a>См. также
- <xref:System.Windows.Forms.Control.AutoSize%2A>
- <xref:System.Windows.Forms.Control.Margin%2A>
- <xref:System.Windows.Forms.Control.Padding%2A>
- <xref:System.Windows.Forms.Control.LayoutEngine%2A>
- <xref:System.Windows.Forms.TableLayoutPanel>
- <xref:System.Windows.Forms.FlowLayoutPanel>
