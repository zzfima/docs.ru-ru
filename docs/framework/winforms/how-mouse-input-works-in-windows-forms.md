---
title: "How Mouse Input Works in Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Windows Forms, mouse input"
  - "mouse, input"
ms.assetid: 48fc5240-75a6-44bf-9fce-6aa21b49705a
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# How Mouse Input Works in Windows Forms
Получение и обработка ввода мыши — важная часть каждого приложения Windows.  Можно обработать события мыши для выполнения действий в приложении или использовать положение указателя мыши для проверки нажатия или других действий.  Кроме того, можно изменить способ обработки ввода мыши элементами управления в приложении.  В этом разделе подробно описываются события мыши и способы получения и изменения системных параметров для мыши.  Дополнительные сведения о данных, передаваемых с событиями мыши, и порядке, в котором поступают события щелчка мыши, см. в разделе [Mouse Events in Windows Forms](../../../docs/framework/winforms/mouse-events-in-windows-forms.md).  
  
## Положение указателя мыши и проверка нажатия  
 Когда пользователь перемещает мышь, операционная система перемещает указатель мыши.  Указатель содержит один пиксель, который называется активной точкой указателя мыши; операционная система отслеживает эту точку и распознает ее как положение указателя.  Когда пользователь перемещает мышь или нажимает кнопку мыши, класс <xref:System.Windows.Forms.Control>, который содержит свойство <xref:System.Windows.Forms.Cursor.HotSpot%2A>, вызывает соответствующее событие мыши.  Текущее положение мыши можно получить через свойство <xref:System.Windows.Forms.MouseEventArgs.Location%2A> класса <xref:System.Windows.Forms.MouseEventArgs> при обработке события мыши или с помощью свойства <xref:System.Windows.Forms.Cursor.Position%2A> класса <xref:System.Windows.Forms.Cursor>.  Затем сведения о положении мыши можно использовать для проверки нажатия и последующего выполнения действия, основанного на расположении мыши.  Возможность проверки нажатия встроена в некоторые элементы управления Windows Forms, например в элементы управления <xref:System.Windows.Forms.ListView>, <xref:System.Windows.Forms.TreeView>, <xref:System.Windows.Forms.MonthCalendar> и <xref:System.Windows.Forms.DataGridView>.  При использовании с соответствующими событиями мыши, например с событием <xref:System.Windows.Forms.Control.MouseHover>, проверка нажатия может быть весьма полезной для определения конкретных действий приложения.  
  
## События мыши  
 Основным способом реагирования на ввод мыши является обработка событий мыши.  В следующей таблице перечислены события мыши и указано, когда они вызываются.  
  
|Событие мыши|Описание|  
|------------------|--------------|  
|<xref:System.Windows.Forms.Control.Click>|Это событие происходит при отпускании кнопки мыши, обычно перед событием <xref:System.Windows.Forms.Control.MouseUp>.  Обработчик этого события получает аргумента типа <xref:System.EventArgs>.  Данное событие обрабатывается при необходимости определить, когда происходит щелчок.|  
|<xref:System.Windows.Forms.Control.MouseClick>|Это событие возникает при щелчке элемента управления мышью.  Обработчик этого события получает аргумента типа <xref:System.Windows.Forms.MouseEventArgs>.  Данное событие обрабатывается при необходимости получить сведения о мыши в момент щелчка.|  
|<xref:System.Windows.Forms.Control.DoubleClick>|Это событие возникает при двойном щелчке элемента управления.  Обработчик этого события получает аргумента типа <xref:System.EventArgs>.  Данное событие обрабатывается при необходимости определить, когда происходит двойной щелчок.|  
|<xref:System.Windows.Forms.Control.MouseDoubleClick>|Это событие возникает при двойном щелчке по элементу управления мышью.  Обработчик этого события получает аргумента типа <xref:System.Windows.Forms.MouseEventArgs>.  Данное событие обрабатывается при необходимости получить сведения о мыши в момент двойного щелчка.|  
|<xref:System.Windows.Forms.Control.MouseDown>|Это событие происходит, если пользователь нажимает кнопку мыши в тот момент, когда указатель мыши находится над элементом управления.  Обработчик этого события получает аргумента типа <xref:System.Windows.Forms.MouseEventArgs>.|  
|<xref:System.Windows.Forms.Control.MouseEnter>|Это событие происходит, когда указатель мыши входит в рамку или клиентскую область элемента управления, в зависимости от типа элемента управления.  Обработчик этого события получает аргумента типа <xref:System.EventArgs>.|  
|<xref:System.Windows.Forms.Control.MouseHover>|Это событие происходит, когда указатель мыши останавливается над элементом управления.  Обработчик этого события получает аргумента типа <xref:System.EventArgs>.|  
|<xref:System.Windows.Forms.Control.MouseLeave>|Это событие происходит, когда указатель мыши покидает рамку или клиентскую область элемента управления, в зависимости от типа элемента управления.  Обработчик этого события получает аргумента типа <xref:System.EventArgs>.|  
|<xref:System.Windows.Forms.Control.MouseMove>|Это событие возникает при перемещении указателя мыши над элементом управления.  Обработчик этого события получает аргумента типа <xref:System.Windows.Forms.MouseEventArgs>.|  
|<xref:System.Windows.Forms.Control.MouseUp>|Это событие происходит, если пользователь отпускает кнопку мыши в тот момент, когда указатель мыши находится над элементом управления.  Обработчик этого события получает аргумента типа <xref:System.Windows.Forms.MouseEventArgs>.|  
|<xref:System.Windows.Forms.Control.MouseWheel>|Это событие происходит, когда пользователь прокручивает колесико мыши, в то время как на элементе управления установлен фокус.  Обработчик этого события получает аргумента типа <xref:System.Windows.Forms.MouseEventArgs>.  Для определения, насколько прокручена мышь, можно использовать свойство <xref:System.Windows.Forms.MouseEventArgs.Delta%2A> аргумента <xref:System.Windows.Forms.MouseEventArgs>.|  
  
## Изменение ввода мыши и определение системных параметров  
 Можно определить и изменить способ, которым элемент управления обрабатывает ввод мыши, путем создания производного элемента управления и использования методов <xref:System.Windows.Forms.Control.GetStyle%2A> и <xref:System.Windows.Forms.Control.SetStyle%2A>.  Метод <xref:System.Windows.Forms.Control.SetStyle%2A> принимает битовое сочетание значений <xref:System.Windows.Forms.ControlStyles>, чтобы определить, будет ли элемент управления реализовывать стандартное поведение одинарного или двойного щелчка или обрабатывать события мыши особым образом.  Кроме того, класс <xref:System.Windows.Forms.SystemInformation> включает свойства, которые описывают возможности мыши и указывают способы взаимодействия мыши с операционной системой.  В следующей таблице приведены сводные сведения об этих свойствах.  
  
|Свойство.|Описание|  
|---------------|--------------|  
|<xref:System.Windows.Forms.SystemInformation.DoubleClickSize%2A>|Получает размеры области \(в пикселях\), в которой пользователь должен щелкнуть дважды, чтобы операционная система обработала два щелчка как двойной щелчок.|  
|<xref:System.Windows.Forms.SystemInformation.DoubleClickTime%2A>|Получает максимальное число миллисекунд, которое может пройти между первым и вторым щелчком, чтобы операционная система рассматривала эти действия мыши как двойной щелчок.|  
|<xref:System.Windows.Forms.SystemInformation.MouseButtons%2A>|Получает число кнопок мыши.|  
|<xref:System.Windows.Forms.SystemInformation.MouseButtonsSwapped%2A>|Получает значение, указывающее, могут ли меняться местами функции левой и правой кнопок мыши.|  
|<xref:System.Windows.Forms.SystemInformation.MouseHoverSize%2A>|Получает размеры прямоугольника \(в пикселях\), в котором должен находиться указатель мыши в течении времени наведения мыши перед тем, как генерируется сообщение о наведении мыши.|  
|<xref:System.Windows.Forms.SystemInformation.MouseHoverTime%2A>|Получает интервал времени \(в миллисекундах\), в течение которого указатель мыши должен оставаться в прямоугольнике наведения перед тем, как вызывается сообщение о наведении мыши.|  
|<xref:System.Windows.Forms.SystemInformation.MousePresent%2A>|Получает значение, указывающее, установлена ли мышь.|  
|<xref:System.Windows.Forms.SystemInformation.MouseSpeed%2A>|Получает значение, указывающее текущую скорость мыши, от 1 до 20.|  
|<xref:System.Windows.Forms.SystemInformation.MouseWheelPresent%2A>|Получает значение, указывающее, установлена ли мышь с колесом прокрутки.|  
|<xref:System.Windows.Forms.SystemInformation.MouseWheelScrollDelta%2A>|Получает значение приращения, выполняемого при одном повороте колесика мыши.|  
|<xref:System.Windows.Forms.SystemInformation.MouseWheelScrollLines%2A>|Получает число строк, прокручиваемых при вращении колесика мыши.|  
  
## См. также  
 [Mouse Input in a Windows Forms Application](../../../docs/framework/winforms/mouse-input-in-a-windows-forms-application.md)   
 [Mouse Capture in Windows Forms](../../../docs/framework/winforms/mouse-capture-in-windows-forms.md)   
 [Mouse Pointers in Windows Forms](../../../docs/framework/winforms/mouse-pointers-in-windows-forms.md)