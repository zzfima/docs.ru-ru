---
title: Как работает ввод с помощью мыши
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, mouse input
- mouse [Windows Forms], input
ms.assetid: 48fc5240-75a6-44bf-9fce-6aa21b49705a
ms.openlocfilehash: 1164974e65ca1e96c0650569626ad4140baf004e
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76739635"
---
# <a name="how-mouse-input-works-in-windows-forms"></a>Осуществление ввода мышью в Windows Forms
Получение и обработка ввода с помощью мыши является важной частью каждого приложения Windows. Вы можете управлять событиями мыши для выполнения действий в приложении или использовать сведения о расположении мыши для выполнения проверки нажатия или других действий. Кроме того, можно изменить способ, которым элементы управления в приложении будут управлять вводом с помощью мыши. В этом разделе подробно описаны эти события мыши, а также способы получения и изменения системных параметров мыши. Дополнительные сведения о данных, предоставляемых событиями мыши, и порядке, в котором вызываются события щелчка мыши, см. [в разделе события мыши в Windows Forms](mouse-events-in-windows-forms.md).  
  
## <a name="mouse-location-and-hit-testing"></a>Расположение мыши и проверка попадания  
 Когда пользователь перемещает мышь, операционная система перемещает указатель мыши. Указатель мыши содержит один пиксель, называемый «горячей» точкой, которую операционная система отслеживает и распознает как расположение указателя. Когда пользователь перемещает мышь или нажимает кнопку мыши, <xref:System.Windows.Forms.Control>, содержащая <xref:System.Windows.Forms.Cursor.HotSpot%2A>, вызывает соответствующее событие мыши. Текущее расположение мыши можно получить с помощью свойства <xref:System.Windows.Forms.MouseEventArgs.Location%2A> <xref:System.Windows.Forms.MouseEventArgs> при обработке события мыши или с помощью свойства <xref:System.Windows.Forms.Cursor.Position%2A> класса <xref:System.Windows.Forms.Cursor>. Можно впоследствии использовать сведения о расположении мыши для выполнения проверки попадания, а затем выполнить действие на основе расположения мыши. Возможность проверки попадания встроена в несколько элементов управления в Windows Forms таких как <xref:System.Windows.Forms.ListView>, <xref:System.Windows.Forms.TreeView>, <xref:System.Windows.Forms.MonthCalendar> и элементы управления <xref:System.Windows.Forms.DataGridView>. При использовании с соответствующим событием мыши <xref:System.Windows.Forms.Control.MouseHover> например, проверка попадания очень полезна для определения того, когда приложение должно выполнить определенное действие.  
  
## <a name="mouse-events"></a>События мыши  
 Основной способ реагирования на ввод с помощью мыши заключается в обработке событий мыши. В следующей таблице показаны события мыши и описание их возникновения.  
  
|Событие мыши|Description|  
|-----------------|-----------------|  
|<xref:System.Windows.Forms.Control.Click>|Это событие возникает при отпускании кнопки мыши, как правило, перед событием <xref:System.Windows.Forms.Control.MouseUp>. Обработчик этого события принимает аргумент типа <xref:System.EventArgs>. Обрабатывайте это событие, если нужно только определить, когда происходит щелчок.|  
|<xref:System.Windows.Forms.Control.MouseClick>|Это событие возникает, когда пользователь щелкает элемент управления с помощью мыши. Обработчик этого события принимает аргумент типа <xref:System.Windows.Forms.MouseEventArgs>. Обрабатывайте это событие, когда необходимо получить сведения о мыши при нажатии кнопки.|  
|<xref:System.Windows.Forms.Control.DoubleClick>|Это событие возникает при двойном щелчке элемента управления. Обработчик этого события принимает аргумент типа <xref:System.EventArgs>. Обрабатывайте это событие, если нужно только определить, когда происходит двойное нажатие.|  
|<xref:System.Windows.Forms.Control.MouseDoubleClick>|Это событие возникает, когда пользователь дважды щелкает элемент управления с помощью мыши. Обработчик этого события принимает аргумент типа <xref:System.Windows.Forms.MouseEventArgs>. Обрабатывайте это событие, когда необходимо получить сведения о мыши при двойном щелчке.|  
|<xref:System.Windows.Forms.Control.MouseDown>|Это событие возникает, когда указатель мыши находится над элементом управления и пользователь нажимает кнопку мыши. Обработчик этого события принимает аргумент типа <xref:System.Windows.Forms.MouseEventArgs>.|  
|<xref:System.Windows.Forms.Control.MouseEnter>|Это событие возникает, когда указатель мыши попадает в границу или клиентскую область элемента управления в зависимости от типа элемента управления. Обработчик этого события принимает аргумент типа <xref:System.EventArgs>.|  
|<xref:System.Windows.Forms.Control.MouseHover>|Это событие возникает при остановке и помещении указателя мыши на элемент управления. Обработчик этого события принимает аргумент типа <xref:System.EventArgs>.|  
|<xref:System.Windows.Forms.Control.MouseLeave>|Это событие возникает, когда указатель мыши покидает границу или клиентскую область элемента управления в зависимости от типа элемента управления. Обработчик этого события принимает аргумент типа <xref:System.EventArgs>.|  
|<xref:System.Windows.Forms.Control.MouseMove>|Это событие возникает при перемещении указателя мыши на элемент управления. Обработчик этого события принимает аргумент типа <xref:System.Windows.Forms.MouseEventArgs>.|  
|<xref:System.Windows.Forms.Control.MouseUp>|Это событие возникает, когда указатель мыши находится над элементом управления и пользователь отпускает кнопку мыши. Обработчик этого события принимает аргумент типа <xref:System.Windows.Forms.MouseEventArgs>.|  
|<xref:System.Windows.Forms.Control.MouseWheel>|Это событие возникает, когда пользователь вращает колесико мыши, когда элемент управления имеет фокус. Обработчик этого события принимает аргумент типа <xref:System.Windows.Forms.MouseEventArgs>. Можно использовать свойство <xref:System.Windows.Forms.MouseEventArgs.Delta%2A> <xref:System.Windows.Forms.MouseEventArgs>, чтобы определить, насколько прокручена мышь.|  
  
## <a name="changing-mouse-input-and-detecting-system-settings"></a>Изменение ввода с помощью мыши и определение параметров системы  
 Вы можете обнаружить и изменить способ обработки ввода с помощью элемента управления, производного от элемента управления и используя методы <xref:System.Windows.Forms.Control.GetStyle%2A> и <xref:System.Windows.Forms.Control.SetStyle%2A>. Метод <xref:System.Windows.Forms.Control.SetStyle%2A> принимает побитовое сочетание <xref:System.Windows.Forms.ControlStyles> значений, чтобы определить, будет ли элемент управления иметь стандартное поведение щелчка или двойного щелчка или если элемент управления будет обрабатывать свою собственную обработку мыши. Кроме того, класс <xref:System.Windows.Forms.SystemInformation> содержит свойства, описывающие возможности мыши и определяющие взаимодействие мыши с операционной системой. Эти свойства обобщены в следующей таблице.  
  
|Свойство|Description|  
|--------------|-----------------|  
|<xref:System.Windows.Forms.SystemInformation.DoubleClickSize%2A>|Возвращает размеры (в пикселях) области, в которой пользователь должен щелкнуть дважды, чтобы операционная система рассматривала два щелчка мышью.|  
|<xref:System.Windows.Forms.SystemInformation.DoubleClickTime%2A>|Возвращает максимальное число миллисекунд, которое может пройти между первым щелчком и вторым щелчком, чтобы операционная система рассматривала действие мыши двойным щелчком.|  
|<xref:System.Windows.Forms.SystemInformation.MouseButtons%2A>|Возвращает число кнопок мыши.|  
|<xref:System.Windows.Forms.SystemInformation.MouseButtonsSwapped%2A>|Возвращает значение, указывающее, могут ли меняться местами функции левой и правой кнопок мыши.|  
|<xref:System.Windows.Forms.SystemInformation.MouseHoverSize%2A>|Возвращает размеры прямоугольника (в пикселях), в котором должен находиться указатель мыши в течение времени наведения мыши перед тем, как создается сообщение о наведении мыши.|  
|<xref:System.Windows.Forms.SystemInformation.MouseHoverTime%2A>|Возвращает интервал времени (в миллисекундах), в течение которого указатель мыши должен оставаться в прямоугольнике наведения перед тем, как вызывается сообщение о наведении мыши.|  
|<xref:System.Windows.Forms.SystemInformation.MousePresent%2A>|Возвращает значение, указывающее, установлена ли мышь.|  
|<xref:System.Windows.Forms.SystemInformation.MouseSpeed%2A>|Возвращает значение, указывающее текущую скорость мыши от 1 до 20.|  
|<xref:System.Windows.Forms.SystemInformation.MouseWheelPresent%2A>|Возвращает значение, указывающее, установлена ли мышь с колесом прокрутки.|  
|<xref:System.Windows.Forms.SystemInformation.MouseWheelScrollDelta%2A>|Возвращает величину Дельта-значения приращения одного поворота колесика мыши.|  
|<xref:System.Windows.Forms.SystemInformation.MouseWheelScrollLines%2A>|Возвращает число строк, прокручиваемых при вращении колесика мыши.|  
  
## <a name="see-also"></a>См. также раздел

- [Ввод данных мышью в приложении Windows Forms](mouse-input-in-a-windows-forms-application.md)
- [Захват мыши в Windows Forms](mouse-capture-in-windows-forms.md)
- [Указатели мыши в Windows Forms](mouse-pointers-in-windows-forms.md)
