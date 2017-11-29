---
title: "Осуществление ввода мышью в Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Forms, mouse input
- mouse [Windows Forms], input
ms.assetid: 48fc5240-75a6-44bf-9fce-6aa21b49705a
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 20de05b5df3737ccc525cb50c81b51bcba766287
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-mouse-input-works-in-windows-forms"></a>Осуществление ввода мышью в Windows Forms
Получение и обработка ввода мыши является важной частью каждого приложения Windows. Обработка событий мыши для выполнения действий в приложении или использовать сведения о положении мыши для проверки нажатия или других действий. Кроме того можно изменить способ, элементы управления в приложении обработки ввода мыши. В этом разделе описываются события мыши в подробные сведения и способы получения и изменения системных параметров для мыши. Дополнительные сведения о данных, передаваемых с помощью мыши вызываются события и порядок, в котором события щелчка мыши см. в разделе [события мыши в формах Windows Forms](../../../docs/framework/winforms/mouse-events-in-windows-forms.md).  
  
## <a name="mouse-location-and-hit-testing"></a>Положение указателя мыши и попадания  
 Когда пользователь перемещает мышь, операционная система перемещает указатель мыши. Указатель содержит один пиксель, называется активной точкой, который отслеживает операционной системы и распознает как положение указателя. Когда пользователь перемещает мышь или нажимает кнопку мыши, <xref:System.Windows.Forms.Control> , содержащий <xref:System.Windows.Forms.Cursor.HotSpot%2A> вызывает соответствующее событие мыши. Вы можете получить текущее положение мыши <xref:System.Windows.Forms.MouseEventArgs.Location%2A> свойство <xref:System.Windows.Forms.MouseEventArgs> при обработке события мыши или с помощью <xref:System.Windows.Forms.Cursor.Position%2A> свойство <xref:System.Windows.Forms.Cursor> класса. Можно впоследствии использовать сведения о положении мыши для проверки нажатия и последующего выполнения действия на основе расположения указателя мыши. Возможность проверки нажатия встроена в несколько элементов управления в формах Windows Forms например <xref:System.Windows.Forms.ListView>, <xref:System.Windows.Forms.TreeView>, <xref:System.Windows.Forms.MonthCalendar> и <xref:System.Windows.Forms.DataGridView> элементов управления. При использовании соответствующее событие мыши, <xref:System.Windows.Forms.Control.MouseHover> к примеру, попадания очень полезно для определения, когда приложение должно выполнить определенное действие.  
  
## <a name="mouse-events"></a>События мыши  
 Основным способом реагирования на ввод мыши является обработка событий мыши. В следующей таблице перечислены события мыши и описывается, когда они возникают.  
  
|Событие мыши|Описание|  
|-----------------|-----------------|  
|<xref:System.Windows.Forms.Control.Click>|Это событие происходит при отпускании кнопки мыши, обычно перед <xref:System.Windows.Forms.Control.MouseUp> событий. Обработчик этого события принимает аргумент типа <xref:System.EventArgs>. Обрабатываете, если необходимо определить, когда происходит щелчок.|  
|<xref:System.Windows.Forms.Control.MouseClick>|Это событие возникает, когда пользователь щелкает элемент управления с помощью мыши. Обработчик этого события принимает аргумент типа <xref:System.Windows.Forms.MouseEventArgs>. Обрабатываете, если нужно получить сведения о мыши, когда происходит щелчок.|  
|<xref:System.Windows.Forms.Control.DoubleClick>|Это событие возникает при двойном щелчке элемента управления. Обработчик этого события принимает аргумент типа <xref:System.EventArgs>. Обрабатываете, если необходимо определить, когда происходит двойной щелчок.|  
|<xref:System.Windows.Forms.Control.MouseDoubleClick>|Это событие возникает при двойном щелчке мышью элемента управления. Обработчик этого события принимает аргумент типа <xref:System.Windows.Forms.MouseEventArgs>. Обрабатываете, если нужно получить сведения о мыши, когда происходит двойной щелчок.|  
|<xref:System.Windows.Forms.Control.MouseDown>|Это событие возникает, когда указатель мыши находится над элементом управления, и пользователь нажимает кнопку мыши. Обработчик этого события принимает аргумент типа <xref:System.Windows.Forms.MouseEventArgs>.|  
|<xref:System.Windows.Forms.Control.MouseEnter>|Это событие возникает, когда указатель мыши входит в рамку или клиентскую область элемента управления, в зависимости от типа элемента управления. Обработчик этого события принимает аргумент типа <xref:System.EventArgs>.|  
|<xref:System.Windows.Forms.Control.MouseHover>|Это событие возникает, когда указатель мыши останавливается и наводится на элемент управления. Обработчик этого события принимает аргумент типа <xref:System.EventArgs>.|  
|<xref:System.Windows.Forms.Control.MouseLeave>|Это событие происходит, когда указатель мыши покидает рамку или клиентскую область элемента управления, в зависимости от типа элемента управления. Обработчик этого события принимает аргумент типа <xref:System.EventArgs>.|  
|<xref:System.Windows.Forms.Control.MouseMove>|Это событие возникает при перемещении указателя мыши, когда оно находится над элементом управления. Обработчик этого события принимает аргумент типа <xref:System.Windows.Forms.MouseEventArgs>.|  
|<xref:System.Windows.Forms.Control.MouseUp>|Это событие возникает, когда указатель мыши находится над элементом управления, и пользователь отпускает кнопку мыши. Обработчик этого события принимает аргумент типа <xref:System.Windows.Forms.MouseEventArgs>.|  
|<xref:System.Windows.Forms.Control.MouseWheel>|Это событие происходит при вращении колесика мыши в момент, когда элемент управления имеет фокус. Обработчик этого события принимает аргумент типа <xref:System.Windows.Forms.MouseEventArgs>. Можно использовать <xref:System.Windows.Forms.MouseEventArgs.Delta%2A> свойство <xref:System.Windows.Forms.MouseEventArgs> для определения того, насколько далеко прокрутка мыши.|  
  
## <a name="changing-mouse-input-and-detecting-system-settings"></a>Изменение ввода мыши и определение системных параметров  
 Можно определить и изменить способ, элемент управления обрабатывает ввод мыши путем создания производного элемента управления и использования <xref:System.Windows.Forms.Control.GetStyle%2A> и <xref:System.Windows.Forms.Control.SetStyle%2A> методы. <xref:System.Windows.Forms.Control.SetStyle%2A> Метод принимает побитовое сочетание <xref:System.Windows.Forms.ControlStyles> значения, чтобы определить, имеют ли элемент управления стандартного щелкните или дважды щелкните поведение или если элемент управления будет обрабатывать обработку. Кроме того <xref:System.Windows.Forms.SystemInformation> класс включает свойства, которые описывают возможности мыши и указать способы взаимодействия мыши с операционной системой. В следующей таблице перечислены эти свойства.  
  
|Свойство|Описание|  
|--------------|-----------------|  
|<xref:System.Windows.Forms.SystemInformation.DoubleClickSize%2A>|Возвращает размеры, в пикселях, области, в которой пользователь должен щелкнуть дважды, чтобы операционная система обработала два щелчка как двойной щелчок.|  
|<xref:System.Windows.Forms.SystemInformation.DoubleClickTime%2A>|Получает максимальное число миллисекунд, которое может пройти между первым и вторым щелчком, чтобы операционная система рассматривала эти действия мыши как двойной щелчок.|  
|<xref:System.Windows.Forms.SystemInformation.MouseButtons%2A>|Возвращает число кнопок мыши.|  
|<xref:System.Windows.Forms.SystemInformation.MouseButtonsSwapped%2A>|Возвращает значение, указывающее, могут ли меняться местами функции левой и правой кнопок мыши.|  
|<xref:System.Windows.Forms.SystemInformation.MouseHoverSize%2A>|Возвращает размеры прямоугольника (в пикселях), в котором должен находиться указатель мыши в течение времени наведения мыши перед тем, как создается сообщение о наведении мыши.|  
|<xref:System.Windows.Forms.SystemInformation.MouseHoverTime%2A>|Возвращает интервал времени (в миллисекундах), в течение которого указатель мыши должен оставаться в прямоугольнике наведения перед тем, как вызывается сообщение о наведении мыши.|  
|<xref:System.Windows.Forms.SystemInformation.MousePresent%2A>|Возвращает значение, указывающее, установлена ли мышь.|  
|<xref:System.Windows.Forms.SystemInformation.MouseSpeed%2A>|Возвращает значение, указывающее текущую скорость мыши от 1 до 20.|  
|<xref:System.Windows.Forms.SystemInformation.MouseWheelPresent%2A>|Возвращает значение, указывающее, установлена ли мышь с колесом прокрутки.|  
|<xref:System.Windows.Forms.SystemInformation.MouseWheelScrollDelta%2A>|Возвращает значение приращения одном повороте колесика мыши.|  
|<xref:System.Windows.Forms.SystemInformation.MouseWheelScrollLines%2A>|Возвращает число строк, прокручиваемых при вращении колесика мыши.|  
  
## <a name="see-also"></a>См. также  
 [Ввод данных мышью в приложении Windows Forms](../../../docs/framework/winforms/mouse-input-in-a-windows-forms-application.md)  
 [Захват мыши в Windows Forms](../../../docs/framework/winforms/mouse-capture-in-windows-forms.md)  
 [Указатели мыши в Windows Forms](../../../docs/framework/winforms/mouse-pointers-in-windows-forms.md)
