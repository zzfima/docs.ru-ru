---
title: Практическое руководство. Установка фона панели формы Windows Forms с помощью конструктора
ms.date: 03/30/2017
helpviewer_keywords:
- background colors [Windows Forms], Windows Forms Panel controls
- background images [Windows Forms], Windows Forms Panel controls
- Panel control [Windows Forms], background
- colors [Windows Forms], Windows Forms Panel controls
ms.assetid: db83cf54-3c69-4b08-ac6c-25b9b5abb1b0
ms.openlocfilehash: 896aa61f3f0900760dffd09bcab6a08bbc01628d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-set-the-background-of-a-windows-forms-panel-using-the-designer"></a>Практическое руководство. Установка фона панели формы Windows Forms с помощью конструктора
Windows Forms <xref:System.Windows.Forms.Panel> элемент управления может отображать цвет фона и фоновое изображение. <xref:System.Windows.Forms.Control.BackColor%2A> Свойство задает цвет фона для элементов управления, содержащихся в панели, например, метки и переключатели. Если <xref:System.Windows.Forms.Control.BackgroundImage%2A> свойство не задано, <xref:System.Windows.Forms.Control.BackColor%2A> выбора заполнит все панели. Если <xref:System.Windows.Forms.Control.BackgroundImage%2A> имеет значение, изображение отображается позади элементов, содержащихся в палитре.  
  
 В следующей процедуре требуется **приложения Windows** проект с формой, содержащей <xref:System.Windows.Forms.Panel> элемента управления. Сведения о настройке такого проекта см. в разделе [как: Создание проекта приложения Windows](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa) и [как: Добавление элементов управления в Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).  
  
> [!NOTE]
>  Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска. Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** . Дополнительные сведения см. в статье [Настройка параметров разработки в Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-set-the-background-in-the-windows-forms-designer"></a>Чтобы задать фон в конструкторе Windows Forms  
  
1.  Выберите элемент управления <xref:System.Windows.Forms.Panel>.  
  
2.  В **свойства** щелкните стрелку рядом с полем <xref:System.Windows.Forms.Control.BackColor%2A> свойство для отображения окна с тремя вкладками.  
  
3.  Выберите **настраиваемый** вкладку, чтобы отобразить палитру цветов.  
  
4.  Выберите **Web** или **системы** вкладку для отображения списка предопределенных имен цветов, а затем выберите цвет.  
  
5.  В **свойства** щелкните стрелку рядом с полем <xref:System.Windows.Forms.Control.BackgroundImage%2A> свойство.  
  
6.  В **откройте** диалоговом окне выберите файл, который требуется отобразить.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.Control.BackColor%2A>  
 <xref:System.Windows.Forms.Control.BackgroundImage%2A>  
 [Элемент управления Panel](../../../../docs/framework/winforms/controls/panel-control-windows-forms.md)  
 [Общие сведения об элементе управления Panel](../../../../docs/framework/winforms/controls/panel-control-overview-windows-forms.md)  
 [Практическое руководство. Группирование элементов управления с элементом управления Panel в формах Windows Forms с помощью конструктора](../../../../docs/framework/winforms/controls/group-controls-with-wf-panel-control-using-the-designer.md)
