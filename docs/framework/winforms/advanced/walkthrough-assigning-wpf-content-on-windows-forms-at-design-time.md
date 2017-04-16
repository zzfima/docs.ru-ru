---
title: "Пошаговое руководство. Назначение содержимого WPF в формах Windows Forms во время разработки | Microsoft Docs"
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
  - "ElementHost - элемент управления, назначение содержимого WPF во время разработки"
  - "взаимодействие [WPF]"
  - "Windows Forms, назначение содержимого"
  - "содержимое WPF [Windows Forms], назначение во время разработки"
  - "пользовательский элемент управления WPF, размещение в Windows Forms"
ms.assetid: b3e9ef93-7e0f-4a2f-8f1e-3437609a1eb7
caps.latest.revision: 18
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 18
---
# Пошаговое руководство. Назначение содержимого WPF в формах Windows Forms во время разработки
В этом пошаговом руководстве показано, как выбрать типы элементов управления Windows Presentation Foundation \(WPF\), которые будут отображаться в форме.  Можно выбрать любые типы элементов управления WPF, включенные в проект.  
  
 В этом пошаговом руководстве выполняются следующие задачи.  
  
-   Создание проекта.  
  
-   Создание типов элементов управления WPF.  
  
-   Выбор элементов управления WPF.  
  
> [!NOTE]
>  Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска.  Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров**.  Дополнительные сведения см. в разделе [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ru-ru/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
## Обязательные компоненты  
 Ниже приведены компоненты, необходимые для выполнения данного пошагового руководства.  
  
-   [!INCLUDE[vs_dev11_long](../../../../includes/vs-dev11-long-md.md)].  
  
## Создание проекта  
 Первым шагом является создание проекта Windows Forms.  
  
> [!NOTE]
>  При размещении содержимого WPF поддерживаются только проекты C\# и Visual Basic.  
  
#### Создание проекта  
  
-   В Visual Basic или Visual C\# создайте проект приложения Windows Forms с именем `SelectingWpfContent`.  
  
## Создание типов элементов управления WPF  
 После добавления типов элементов управления WPF в проект их можно разместить в разных элементах управления <xref:System.Windows.Forms.Integration.ElementHost>.  
  
#### Создание типов элементов управления WPF  
  
1.  Добавьте в решение новый проект WPF <xref:System.Windows.Controls.UserControl>.  Используйте имя по умолчанию для этого типа элемента управления \(`UserControl1.xaml`\).  Подробнее см. в разделе [Пошаговое руководство. Создание нового содержимого WPF для формы Windows Forms во время разработки](../../../../docs/framework/winforms/advanced/walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).  
  
2.  Убедитесь в том, что элемент `UserControl1` выбран в представлении конструирования.  Подробнее см. в разделе [Практическое руководство. Выбор и перемещение элементов в область конструктора](http://msdn.microsoft.com/ru-ru/54cb70b6-b35b-46e4-a0cc-65189399c474).  
  
3.  В окне **Свойства** присвойте свойствам <xref:System.Windows.FrameworkElement.Width%2A> и <xref:System.Windows.FrameworkElement.Height%2A> значение `200`.  
  
4.  Добавьте элемент управления <xref:System.Windows.Controls.TextBox?displayProperty=fullName> в <xref:System.Windows.Controls.UserControl> и присвойте свойству <xref:System.Windows.Controls.TextBox.Text%2A> значение "Hosted Content".  
  
5.  Добавьте в проект второй элемент управления WPF <xref:System.Windows.Controls.UserControl>.  Используйте имя по умолчанию для этого типа элемента управления \(`UserControl2.xaml`\).  
  
6.  В окне **Свойства** присвойте свойствам <xref:System.Windows.FrameworkElement.Width%2A> и <xref:System.Windows.FrameworkElement.Height%2A> значение `200`.  
  
7.  Добавьте элемент управления <xref:System.Windows.Controls.TextBox?displayProperty=fullName> в <xref:System.Windows.Controls.UserControl> и присвойте свойству <xref:System.Windows.Controls.TextBox.Text%2A> значение "Hosted Content 2".  
  
 **Примечание** Как правило, требуется размещать более сложное WPF\-содержимое.  Элемент управления <xref:System.Windows.Controls.TextBox?displayProperty=fullName> используется в данном случае только в иллюстративных целях.  
  
1.  Выполните построение проекта.  
  
## Выбор элементов управления WPF  
 Для элемента управления <xref:System.Windows.Forms.Integration.ElementHost>, в котором уже размещено содержимое, можно назначить различное содержимое WPF.  
  
#### Выбор элементов управления WPF  
  
1.  Откройте `Form1` в конструкторе Windows Forms.  
  
2.  На **панели элементов** дважды щелкните `UserControl1`, чтобы создать экземпляр `UserControl1` на форме.  
  
     Экземпляр `UserControl1` размещается в новом элементе управления <xref:System.Windows.Forms.Integration.ElementHost> с именем `elementHost1`.  
  
3.  В панели смарт\-тега для `elementHost1` откройте раскрывающийся список **Выбрать размещенное содержимое**.  
  
4.  В раскрывающемся поле со списком выберите **UserControl2**.  
  
     В элементе управления `elementHost1` теперь будет размещен экземпляр типа `UserControl2`.  
  
5.  В окне **Свойства** убедитесь, что свойству <xref:System.Windows.Forms.Integration.ElementHost.Child%2A> присвоено значение **UserControl2**.  
  
6.  В **панели инструментов** из группы **Взаимодействие с WPF** перетащите элемент управления <xref:System.Windows.Forms.Integration.ElementHost> на форму.  
  
     Имя по умолчанию для нового элемента управления — `elementHost2`.  
  
7.  В панели смарт\-тега для `elementHost2` откройте раскрывающийся список **Выбрать размещенное содержимое**.  
  
8.  Выберите **UserControl1** из раскрывающегося списка.  
  
9. В элементе управления `elementHost2` теперь будет размещен экземпляр типа `UserControl1`.  
  
## См. также  
 <xref:System.Windows.Forms.Integration.ElementHost>   
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>   
 [Миграция и взаимодействие систем](../../../../docs/framework/wpf/advanced/migration-and-interoperability.md)   
 [Использование элементов управления WPF](../../../../docs/framework/winforms/advanced/using-wpf-controls.md)   
 [Конструктор WPF](http://msdn.microsoft.com/ru-ru/c6c65214-8411-4e16-b254-163ed4099c26)