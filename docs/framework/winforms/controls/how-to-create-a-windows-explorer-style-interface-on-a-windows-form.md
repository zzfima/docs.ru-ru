---
title: Практическое руководство. Создание интерфейса в стиле проводника в форме Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Explorer [Windows Forms], creating with Windows Forms
- SplitContainer control [Windows Forms], Explorer-style interface
- forms [Windows Forms], Windows Explorer type
ms.assetid: 9a3d5f4f-5dda-4350-9ad5-57ce5976dc47
ms.openlocfilehash: 2d5b79244d867ea4b6134413d42710b2eadc871e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33532390"
---
# <a name="how-to-create-a-windows-explorerstyle-interface-on-a-windows-form"></a>Практическое руководство. Создание интерфейса в стиле проводника в форме Windows Forms
Проводник Windows является распространенным вариантом пользовательского интерфейса для приложений из-за его хорошо знаком всем пользователям.  
  
 Проводник — это, по существу, <xref:System.Windows.Forms.TreeView> управления и <xref:System.Windows.Forms.ListView> на отдельных панелях. С помощью разделителя панели выполняются с раскрывающимися списками. Это упорядочение элементов управления является весьма эффективным для отображения и просмотра информации.  
  
 Следующие шаги показывают, как размещение элементов управления в форме проводника Windows. Они не показано, как добавить функциональные возможности просмотра файла приложение проводника.  
  
> [!NOTE]
>  Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска. Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** . Дополнительные сведения см. в статье [Настройка параметров разработки в Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-create-a-windows-explorer-style-windows-form"></a>Чтобы создать форму Windows Forms стиле проводника Windows  
  
1.  Создайте новый проект приложения Windows. Дополнительные сведения см. в разделе [Практическое руководство. Создание проекта приложения Windows](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa).  
  
2.  Из **элементов**:  
  
    1.  Перетащите <xref:System.Windows.Forms.SplitContainer> управления на форму.  
  
    2.  Перетащите <xref:System.Windows.Forms.TreeView> управления в **SplitterPanel1** (панели <xref:System.Windows.Forms.SplitContainer> управления, помеченных как **Panel1**).  
  
    3.  Перетащите <xref:System.Windows.Forms.ListView> управления в **SplitterPanel2** (панели <xref:System.Windows.Forms.SplitContainer> управления, помеченных как **Panel2**).  
  
3.  Выберите все три элемента управления, нажав клавишу CTRL и щелкая их в свою очередь. При выборе <xref:System.Windows.Forms.SplitContainer> управлять, щелкните вешку разбивки, а не панели.  
  
    > [!NOTE]
    >  Не используйте **выделить все** на **изменить** меню. Если это сделать, свойство, необходимое на следующем шаге будет отсутствовать в **свойства** окна.  
  
4.  В **свойства** задайте <xref:System.Windows.Forms.SplitContainer.Dock%2A> свойства <xref:System.Windows.Forms.DockStyle.Fill>.  
  
5.  Нажмите клавишу F5 для запуска приложения.  
  
     В форме отображаются двух частей пользовательского интерфейса, аналогично проводника Windows.  
  
    > [!NOTE]
    >  При перетаскивании разделителя, изменение панелями размеров строк.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.SplitContainer>  
 [Практическое руководство. Создание пользовательского интерфейса с несколькими областями с помощью Windows Forms](../../../../docs/framework/winforms/controls/how-to-create-a-multipane-user-interface-with-windows-forms.md)  
 [Практическое руководство. Определение способа изменения размеров и позиционирования в окне с перемещаемым разделителем](../../../../docs/framework/winforms/controls/how-to-define-resize-and-positioning-behavior-in-a-split-window.md)  
 [Практическое руководство. Разделение окна по горизонтали](../../../../docs/framework/winforms/controls/how-to-split-a-window-horizontally.md)  
 [Элемент управления SplitContainer](../../../../docs/framework/winforms/controls/splitcontainer-control-windows-forms.md)
