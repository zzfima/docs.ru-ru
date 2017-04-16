---
title: "Пошаговое руководство. Упорядочение содержимого WPF для формы Windows Forms во время разработки | Microsoft Docs"
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
  - "Windows Forms, привязка и закрепление содержимого WPF"
  - "Windows Forms, упорядочение WPF во время разработки"
  - "содержимое WPF [Windows Forms], упорядочение во время разработки"
  - "содержимое WPF, размещение в Windows Forms"
  - "пользовательские элементы управления WPF [Windows Forms], размещение в панели макета"
ms.assetid: 5efb1c53-1484-43d6-aa8a-f4861b99bb8a
caps.latest.revision: 20
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 20
---
# Пошаговое руководство. Упорядочение содержимого WPF для формы Windows Forms во время разработки
В этом пошаговом руководстве показано, как использовать функции структуры Windows Forms, такие как закрепление и линии привязки, для размещения элементов управления Windows Presentation Foundation \(WPF\).  
  
 В этом пошаговом руководстве выполняются следующие задачи:  
  
-   создание проекта;  
  
-   создание элемента управления WPF;  
  
-   размещение элементов управления WPF на панели макета;  
  
-   использование линий привязки для выравнивания элементов управления WPF;  
  
-   привязка и закрепление элементов управления WPF.  
  
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
  
-   В Visual Basic или Visual C\# создайте проект приложения Windows Forms с именем `ArrangeElementHost`.  
  
## Создание элемента управления WPF  
 После добавления в проект элемента управления WPF можно разместить его в форме.  
  
#### Создание элементов управления WPF  
  
1.  Добавьте в проект новый элемент управления WPF <xref:System.Windows.Controls.UserControl>.  Используйте имя по умолчанию для этого типа элемента управления \(`UserControl1.xaml`\).  Подробнее см. в разделе [Пошаговое руководство. Создание нового содержимого WPF для формы Windows Forms во время разработки](../../../../docs/framework/winforms/advanced/walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).  
  
2.  Убедитесь в том, что элемент `UserControl1` выбран в представлении конструирования.  Подробнее см. в разделе [Практическое руководство. Выбор и перемещение элементов в область конструктора](http://msdn.microsoft.com/ru-ru/54cb70b6-b35b-46e4-a0cc-65189399c474).  
  
3.  В окне **Свойства** присвойте свойствам <xref:System.Windows.FrameworkElement.Width%2A> и <xref:System.Windows.FrameworkElement.Height%2A> значение `200`.  
  
4.  Присвойте свойству <xref:System.Windows.Controls.Control.Background%2A> значение `Blue`.  
  
5.  Выполните построение проекта.  
  
## Размещение элементов управления WPF на панели макета  
 Элементы управления WPF можно использовать на панели макета так же, как и другие элементы управления Windows Forms.  
  
#### Размещение элементов управления WPF на панели макета  
  
1.  Откройте `Form1` в конструкторе Windows Forms.  
  
2.  Перетащите элемент управления <xref:System.Windows.Forms.TableLayoutPanel> из **панели элементов** на форму.  
  
3.  На панели смарт\-тегов элемента управления <xref:System.Windows.Forms.TableLayoutPanel> выберите **Удалить последнюю строку**.  
  
4.  Увеличьте высоту и ширину элемента управления <xref:System.Windows.Forms.TableLayoutPanel>.  
  
5.  На **панели элементов** дважды щелкните `UserControl1`, чтобы создать экземпляр `UserControl1` в первой ячейке элемента управления <xref:System.Windows.Forms.TableLayoutPanel>.  
  
     Экземпляр `UserControl1` размещается в новом элементе управления <xref:System.Windows.Forms.Integration.ElementHost> с именем `elementHost1`.  
  
6.  На **панели элементов** дважды щелкните `UserControl1`, чтобы создать во второй ячейке еще один экземпляр элемента управления <xref:System.Windows.Forms.TableLayoutPanel>.  
  
7.  В окне **Структура документа** выберите `tableLayoutPanel1`.  Подробнее см. в разделе [Document Outline Window](http://msdn.microsoft.com/ru-ru/9054f2bc-f6f8-4242-9fe0-be71089b12f8).  
  
8.  В окне **Свойства** присвойте свойству <xref:System.Windows.Forms.Control.Padding%2A> значение `10, 10, 10, 10`.  
  
     Размер обоих элементов управления <xref:System.Windows.Forms.Integration.ElementHost> изменится в соответствии с новой структурой.  
  
## Выравнивание элементов управления WPF с помощью линий привязки  
 Линии привязки позволяют легко выравнивать элементы управления в форме.  Линии привязки также можно использовать для выравнивания элементов управления WPF.  Подробнее см. в разделе [Пример. Упорядочение элементов управления в формах Windows Forms с помощью линий привязки](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md).  
  
#### Выравнивание элементов управления WPF с помощью линий привязки  
  
1.  Из **панели элементов** перетащите экземпляр `UserControl1` на форму и поместите его под элементом управления <xref:System.Windows.Forms.TableLayoutPanel>.  
  
     Экземпляр `UserControl1` разместится в новом элементе управления <xref:System.Windows.Forms.Integration.ElementHost> с именем `elementHost3`.  
  
2.  С помощью линий привязки выровняйте левый край `elementHost3` относительно левого края элемента управления <xref:System.Windows.Forms.TableLayoutPanel>.  
  
3.  С помощью линий привязки установите для `elementHost3` ту же ширину, что и для элемента управления <xref:System.Windows.Forms.TableLayoutPanel>.  
  
4.  Перемещайте `elementHost3` в сторону элемента управления <xref:System.Windows.Forms.TableLayoutPanel> до тех пор, пока между элементами управления не появится центральная линия привязки.  
  
5.  В окне **Свойства** присвойте свойству Margin значение `20, 20, 20, 20`.  
  
6.  Перемещайте `elementHost3` от элемента управления <xref:System.Windows.Forms.TableLayoutPanel> до тех пор, пока между элементами управления снова не появится центральная линия привязки.  Теперь центральная линия привязки указывает на поле шириной в 20 точек.  
  
7.  Перемещайте элемент управления `elementHost3` вправо до тех пор, пока его левый край не будет выровнен относительно левого края элемента управления `elementHost1`.  
  
8.  Изменяйте ширину элемента `elementHost3` до тех пор, пока его правый край не будет выровнен относительно правого края элемента управления `elementHost2`.  
  
## Привязка и закрепление элементов управления WPF  
 Поведение размещенного в форме элемента управления WPF при привязке и закреплении не отличается от поведения других элементов управления Windows Forms.  
  
#### Привязка и закрепление элементов управления WPF  
  
1.  Выберите `elementHost1`.  
  
2.  В окне **Свойства** задайте для свойства <xref:System.Windows.Forms.Control.Anchor%2A> значение **Top, Bottom, Left, Right**.  
  
3.  Увеличьте размер элемента управления <xref:System.Windows.Forms.TableLayoutPanel>.  
  
     Элемент управления `elementHost1` заполнит всю ячейку.  
  
4.  Выберите `elementHost2`.  
  
5.  В окне **Свойства** присвойте свойству <xref:System.Windows.Forms.Control.Dock%2A> значение <xref:System.Windows.Forms.DockStyle>.  
  
     Элемент управления `elementHost2` заполнит всю ячейку.  
  
6.  Выберите элемент управления <xref:System.Windows.Forms.TableLayoutPanel>.  
  
7.  Задайте для его свойства <xref:System.Windows.Forms.Control.Dock%2A> значение <xref:System.Windows.Forms.DockStyle>.  
  
8.  Выберите `elementHost3`.  
  
9. Задайте для его свойства <xref:System.Windows.Forms.Control.Dock%2A> значение <xref:System.Windows.Forms.DockStyle>.  
  
     Элемент управления `elementHost3` заполнит все оставшееся пространство в форме.  
  
10. Измените размер формы.  
  
     Размер всех трех элементов управления <xref:System.Windows.Forms.Integration.ElementHost> изменится соответствующим образом.  
  
     Подробнее см. в разделе [Практическое руководство. Привязка и закрепление дочерних элементов управления в элементе управления TableLayoutPanel](../../../../docs/framework/winforms/controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md).  
  
## См. также  
 <xref:System.Windows.Forms.Integration.ElementHost>   
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>   
 [Практическое руководство. Привязка и закрепление дочерних элементов управления в элементе управления TableLayoutPanel](../../../../docs/framework/winforms/controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)   
 [Практическое руководство. Выравнивание элементов управления по границам формы во время выполнения](../../../../docs/framework/winforms/controls/how-to-align-a-control-to-the-edges-of-forms-at-design-time.md)   
 [Пример. Упорядочение элементов управления в формах Windows Forms с помощью линий привязки](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)   
 [Миграция и взаимодействие систем](../../../../docs/framework/wpf/advanced/migration-and-interoperability.md)   
 [Использование элементов управления WPF](../../../../docs/framework/winforms/advanced/using-wpf-controls.md)   
 [Конструктор WPF](http://msdn.microsoft.com/ru-ru/c6c65214-8411-4e16-b254-163ed4099c26)