---
title: Пошаговое руководство. Изменение свойств размещенного элемента WPF во время разработки
ms.date: 03/30/2017
helpviewer_keywords:
- WPF content [Windows Forms], changing properties at design time
- Windows Forms, changing properties of WPF content at design time
- WPF content [Windows Forms], hosting in Windows Forms
- interoperability [WPF]
ms.assetid: a1f7a90c-0bbb-4781-8c3c-8cc8bef2488d
ms.openlocfilehash: d17273f52d0cef118b79fef03af72522f6677073
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="walkthrough-changing-properties-of-a-hosted-wpf-element-at-design-time"></a>Пошаговое руководство. Изменение свойств размещенного элемента WPF во время разработки
В этом пошаговом руководстве показано, как изменить значения свойств элемента управления Windows Presentation Foundation (WPF), размещенного на форме Windows Forms.  
  
 В этом пошаговом руководстве будут выполнены следующие задачи.  
  
-   создание проекта;  
  
-   Создание элемента управления WPF.  
  
-   Размещение элементов управления WPF в форме Windows Forms.  
  
-   Изменение значений свойств с использованием конструктора WPF для Visual Studio.  
  
> [!NOTE]
>  Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска. Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** . Дополнительные сведения см. в статье [Настройка параметров разработки в Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
## <a name="prerequisites"></a>Предварительные требования  
 Ниже приведены компоненты, необходимые для выполнения данного пошагового руководства.  
  
-   [!INCLUDE[vs_dev11_long](../../../../includes/vs-dev11-long-md.md)].  
  
## <a name="creating-the-project"></a>Создание проекта  
 Первым шагом является создание проекта Windows Forms.  
  
> [!NOTE]
>  При размещении содержимого WPF поддерживаются только проекты C# и Visual Basic.  
  
#### <a name="to-create-the-project"></a>Создание проекта  
  
-   Создайте новый проект приложения Windows Forms в Visual Basic или Visual C# с именем `WpfHost`.  
  
## <a name="creating-the-wpf-control"></a>Создание элемента управления WPF  
 После добавления в проект элемента управления WPF можно разместить его в форме.  
  
#### <a name="to-create-wpf-controls"></a>Создание элементов управления WPF  
  
1.  Добавьте в проект новый элемент управления WPF <xref:System.Windows.Controls.UserControl>. Используйте имя по умолчанию для этого типа элемента управления (`UserControl1.xaml`). Дополнительные сведения см. в разделе [Пошаговое руководство: Создание нового WPF содержимого в формах Windows Forms во время разработки](../../../../docs/framework/winforms/advanced/walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).  
  
2.  В **свойства** задайте значение <xref:System.Windows.Controls.Control.Background%2A> свойства `Blue`.  
  
3.  Выполните построение проекта.  
  
## <a name="changing-property-values-on-the-wpf-control"></a>Изменение значений свойств элемента управления WPF  
 Смарт-тег <xref:System.Windows.Forms.Integration.ElementHost> упрощает изменение свойств размещенного WPF-содержимого с помощью конструктора WPF.  
  
#### <a name="to-host-a-wpf-control"></a>Размещение элемента управления WPF  
  
1.  Откройте `Form1` в конструкторе Windows Forms.  
  
2.  В **элементов**в **пользовательские элементы управления WPF** дважды щелкните `UserControl1` для создания экземпляра `UserControl1` в форме.  
  
     Экземпляр `UserControl1` размещается в новом элементе управления <xref:System.Windows.Forms.Integration.ElementHost> под именем `elementHost1`.  
  
3.  В **задачи ElementHost** смарт-тега, выберите **редактировать содержимое**.  
  
     Файл UserControl1.xaml откроется в конструкторе WPF.  
  
4.  В **свойства** задайте значение <xref:System.Windows.Controls.Control.Background%2A> свойства `Red`.  
  
5.  Перестройте проект.  
  
6.  Откройте `Form1` в конструкторе Windows Forms.  
  
     Экземпляр `UserControl1` имеет красный фон.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [Практическое руководство. Привязка и закрепление дочерних элементов управления в элементе управления TableLayoutPanel](../../../../docs/framework/winforms/controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)  
 [Практическое руководство. Выравнивание элементов управления по границам формы во время выполнения](../../../../docs/framework/winforms/controls/how-to-align-a-control-to-the-edges-of-forms-at-design-time.md)  
 [Пример. Упорядочение элементов управления в формах Windows Forms с помощью линий привязки](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)  
 [Миграция и взаимодействие систем](../../../../docs/framework/wpf/advanced/migration-and-interoperability.md)  
 [Использование элементов управления WPF](../../../../docs/framework/winforms/advanced/using-wpf-controls.md)  
 [Конструктор WPF](http://msdn.microsoft.com/library/c6c65214-8411-4e16-b254-163ed4099c26)
