---
title: "Пошаговое руководство. Изменение свойств размещенного элемента WPF во время разработки | Microsoft Docs"
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
  - "взаимодействие [WPF]"
  - "Windows Forms, изменение содержимого WPF во время разработки"
  - "содержимое WPF [Windows Forms], изменение свойств во время разработки"
  - "содержимое WPF, размещение в Windows Forms"
ms.assetid: a1f7a90c-0bbb-4781-8c3c-8cc8bef2488d
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Пошаговое руководство. Изменение свойств размещенного элемента WPF во время разработки
В этом пошаговом руководстве показано, как изменить значения свойств элемента управления Windows Presentation Foundation \(WPF\), размещенного на форме Windows Forms.  
  
 В этом пошаговом руководстве будут выполнены следующие задачи.  
  
-   Создание проекта.  
  
-   Создание элемента управления WPF.  
  
-   Размещение элементов управления WPF в форме Windows Forms.  
  
-   Изменение значений свойств с использованием конструктора WPF для Visual Studio.  
  
> [!NOTE]
>  Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска.  Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров**.  Дополнительные сведения см. в разделе [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ru-ru/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
## Обязательные компоненты  
 Ниже приведены компоненты, необходимые для выполнения данного пошагового руководства.  
  
-   [!INCLUDE[vs_dev11_long](../../../../includes/vs-dev11-long-md.md)].  
  
## Создание проекта  
 Первым шагом является создание проекта Windows Forms.  
  
> [!NOTE]
>  Для размещения WPF\-содержимого поддерживаются только проекты C\# и Visual Basic.  
  
#### Создание проекта  
  
-   Создайте новый проект приложения Windows Forms на Visual Basic или Visual C\# с именем `HostingWpf`.  
  
## Создание элемента управления WPF  
 После добавления элемента управления WPF в проект можно разместить его в форме.  
  
#### Создание элементов управления WPF  
  
1.  Добавьте в проект новый элемент управления WPF <xref:System.Windows.Controls.UserControl>.  Используйте имя по умолчанию для данного типа элемента управления – `UserControl1.xaml`.  Дополнительные сведения см. в разделе [Пошаговое руководство. Создание нового содержимого WPF для формы Windows Forms во время разработки](../../../../docs/framework/winforms/advanced/walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).  
  
2.  В окне **Свойства** задайте для свойства <xref:System.Windows.Controls.Control.Background%2A> значение `Blue`.  
  
3.  Выполните построение проекта.  
  
## Изменение значений свойств элемента управления WPF  
 Смарт\-тег <xref:System.Windows.Forms.Integration.ElementHost> упрощает изменение свойств размещенного WPF\-содержимого с помощью конструктора WPF.  
  
#### Размещение элемента управления WPF  
  
1.  Откройте `Form1` в конструкторе Windows Forms.  
  
2.  В **Панели элементов**, на вкладке **Пользовательские элементы управления WPF** дважды щелкните `UserControl1` для создания экземпляра `UserControl1` на форме.  
  
     Экземпляр `UserControl1` размещается в новом элементе управления <xref:System.Windows.Forms.Integration.ElementHost> под именем `elementHost1`.  
  
3.  В панели смарт\-тегов **Задачи ElementHost** выберите пункт **Редактировать содержимое**.  
  
     Файл UserControl1.xaml откроется в конструкторе WPF.  
  
4.  В окне **Свойства** задайте для свойства <xref:System.Windows.Controls.Control.Background%2A> значение `Красный`.  
  
5.  Перестройте проект.  
  
6.  Откройте `Form1` в конструкторе Windows Forms.  
  
     Экземпляр `UserControl1` имеет красный фон.  
  
## См. также  
 <xref:System.Windows.Forms.Integration.ElementHost>   
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>   
 [Практическое руководство. Привязка и закрепление дочерних элементов управления в элементе управления TableLayoutPanel](../../../../docs/framework/winforms/controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)   
 [Практическое руководство. Выравнивание элементов управления по границам формы во время выполнения](../../../../docs/framework/winforms/controls/how-to-align-a-control-to-the-edges-of-forms-at-design-time.md)   
 [Пример. Упорядочение элементов управления в формах Windows Forms с помощью линий привязки](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)   
 [Миграция и взаимодействие систем](../../../../docs/framework/wpf/advanced/migration-and-interoperability.md)   
 [Использование элементов управления WPF](../../../../docs/framework/winforms/advanced/using-wpf-controls.md)   
 [Конструктор WPF](http://msdn.microsoft.com/ru-ru/c6c65214-8411-4e16-b254-163ed4099c26)