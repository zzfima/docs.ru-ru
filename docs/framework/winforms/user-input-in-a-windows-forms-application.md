---
title: Ввод данных пользователем в приложении Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, user input
ms.assetid: 9d61fa96-70f7-4754-885a-49a4a6316bdb
ms.openlocfilehash: 4f1b96ab53b30d045a315b43abd0e38157e26c07
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="user-input-in-a-windows-forms-application"></a>Ввод данных пользователем в приложении Windows Forms
Ввод данных пользователем в Windows Forms, отправляется приложений в виде сообщения Windows. Серии переопределяемые методы обрабатывают эти сообщения в приложения, формы и уровень. Когда эти методы получают сообщения клавиатуры и мыши, они вызывают события, которые могут обрабатываться для получения сведения о мыши или клавиатуры входных данных. Во многих случаях приложения Windows Forms будут обрабатывать все входные данные пользователя путем обработки этих событий. В других случаях приложению может потребоваться переопределить один из методов, которые обрабатывают сообщения, чтобы перехватить конкретное сообщение перед его получением приложением, формы или элемента управления.  
  
## <a name="mouse-and-keyboard-events"></a>События мыши и клавиатуры  
 Все элементы управления Windows Forms наследуют набор событий, связанных с клавиатуры и мыши. Например, элемент управления может обрабатывать <xref:System.Windows.Forms.Control.KeyPress> событие, чтобы определить код символа нажатой клавиши или элемент управления может обрабатывать <xref:System.Windows.Forms.Control.MouseClick> событие, чтобы определить положение указателя мыши, нажмите кнопку. Дополнительные сведения о событиях мыши и клавиатуры см. в разделе [с помощью событий клавиатуры](../../../docs/framework/winforms/using-keyboard-events.md) и [события мыши в формах Windows Forms](../../../docs/framework/winforms/mouse-events-in-windows-forms.md).  
  
## <a name="methods-that-process-user-input-messages"></a>Методы, которые обрабатывают сообщения ввода пользователя  
 Формы и элементы управления имеют доступ к <xref:System.Windows.Forms.IMessageFilter> интерфейс и набор переопределяемых методов, которые обрабатывают сообщения Windows в различных местах очереди сообщений. Все эти методы имеют <xref:System.Windows.Forms.Message> параметр, который инкапсулирует сведения низкого уровня сообщений Windows. Можно реализовать или переопределить эти методы для Проверьте сообщение и сообщение или передать его к следующему получателю в очереди сообщений. В следующей таблице представлены методы, которые обрабатывают все сообщения Windows в Windows Forms.  
  
|Метод|Примечания|  
|------------|-----------|  
|<xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A>|Данный метод перехватывает обновляемых посредством очередей сообщений Windows (также известный как отправленное) на уровне приложения.|  
|<xref:System.Windows.Forms.Control.PreProcessMessage%2A>|Данный метод перехватывает сообщения Windows на уровне формы и элемента управления, прежде чем они будут обработаны.|  
|<xref:System.Windows.Forms.Control.WndProc%2A>|Этот метод обрабатывает сообщения Windows на уровне формы и элемента управления.|  
|<xref:System.Windows.Forms.Control.DefWndProc%2A>|Этот метод выполняет обработку сообщения Windows на уровне формы и элемента управления по умолчанию. Это обеспечивает минимальные функциональные возможности окна.|  
|<xref:System.Windows.Forms.Control.OnNotifyMessage%2A>|Данный метод перехватывает сообщения на уровне формы и элемента управления после их обработки. <xref:System.Windows.Forms.ControlStyles.EnableNotifyMessage> Для вызова этого метода необходимо установить бит стиля.|  
  
 Сообщения клавиатуры и мыши обрабатываются также дополнительный набор переопределяемых методов, характерных для этих типов сообщений. Дополнительные сведения см. в разделе [принцип работы ввода с клавиатуры](../../../docs/framework/winforms/how-keyboard-input-works.md) и [принцип работы мыши ввода в Windows Forms](../../../docs/framework/winforms/how-mouse-input-works-in-windows-forms.md).  
  
## <a name="see-also"></a>См. также  
 [Ввод данных пользователем в Windows Forms](../../../docs/framework/winforms/user-input-in-windows-forms.md)  
 [Ввод с клавиатуры в приложении Windows Forms](../../../docs/framework/winforms/keyboard-input-in-a-windows-forms-application.md)  
 [Ввод данных мышью в приложении Windows Forms](../../../docs/framework/winforms/mouse-input-in-a-windows-forms-application.md)
