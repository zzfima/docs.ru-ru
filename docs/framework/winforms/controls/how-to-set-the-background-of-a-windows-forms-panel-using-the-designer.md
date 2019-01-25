---
title: Как выполнить Меняем цвет фона панели формы Windows Forms с помощью конструктора
ms.date: 03/30/2017
helpviewer_keywords:
- background colors [Windows Forms], Windows Forms Panel controls
- background images [Windows Forms], Windows Forms Panel controls
- Panel control [Windows Forms], background
- colors [Windows Forms], Windows Forms Panel controls
ms.assetid: db83cf54-3c69-4b08-ac6c-25b9b5abb1b0
ms.openlocfilehash: be0359e13bcab868374189c6b42df392327b8eb8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54645077"
---
# <a name="how-to-set-the-background-of-a-windows-forms-panel-using-the-designer"></a>Как выполнить Меняем цвет фона панели формы Windows Forms с помощью конструктора
Windows Forms <xref:System.Windows.Forms.Panel> может отображать элемент управления цветом фона и фоновое изображение. <xref:System.Windows.Forms.Control.BackColor%2A> Свойство задает цвет фона для элементов управления, содержащихся в панели, например, метки и переключатели. Если <xref:System.Windows.Forms.Control.BackgroundImage%2A> свойство не задано, <xref:System.Windows.Forms.Control.BackColor%2A> выбора будет заполнить все панели. Если <xref:System.Windows.Forms.Control.BackgroundImage%2A> свойство задано, элементы управления, содержащихся на панели отображается изображение.  
  
 Следующая процедура требуется **приложения Windows** проект с формой, содержащей <xref:System.Windows.Forms.Panel> элемента управления. Сведения о настройке такого проекта см. в разделе [как: Создайте проект приложения Windows](https://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa) и [как: Добавление элементов управления в Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).  
  
> [!NOTE]
>  Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска. Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** . Дополнительные сведения см. в разделе [Персонализация интегрированной среды разработки Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-set-the-background-in-the-windows-forms-designer"></a>Для установки фона в конструкторе Windows Forms  
  
1.  Выберите элемент управления <xref:System.Windows.Forms.Panel>.  
  
2.  В **свойства** окно, нажмите стрелку, расположенную рядом с полем <xref:System.Windows.Forms.Control.BackColor%2A> свойство для отображения окна с тремя вкладками.  
  
3.  Выберите **Custom** вкладку, чтобы отобразить палитру цветов.  
  
4.  Выберите **Web** или **системы** вкладку для отображения списка предопределенных имен цветов, а затем выберите цвет.  
  
5.  В **свойства** окно, нажмите стрелку, расположенную рядом с полем <xref:System.Windows.Forms.Control.BackgroundImage%2A> свойство.  
  
6.  В **откройте** диалоговом окне выберите файл, который вы хотите отобразить.  
  
## <a name="see-also"></a>См. также
- <xref:System.Windows.Forms.Control.BackColor%2A>
- <xref:System.Windows.Forms.Control.BackgroundImage%2A>
- [Элемент управления Panel](../../../../docs/framework/winforms/controls/panel-control-windows-forms.md)
- [Общие сведения об элементе управления Panel](../../../../docs/framework/winforms/controls/panel-control-overview-windows-forms.md)
- [Практическое руководство. Группа элементов управления с помощью панели управления Windows Forms с помощью конструктора](../../../../docs/framework/winforms/controls/group-controls-with-wf-panel-control-using-the-designer.md)
