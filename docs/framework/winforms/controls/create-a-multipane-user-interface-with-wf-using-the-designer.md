---
title: Практическое руководство. Создание пользовательского интерфейса с несколькими областями с использованием форм Windows Forms с помощью конструктора
ms.date: 03/30/2017
helpviewer_keywords:
- user interface [Windows Forms], multipane
- SplitContainer control [Windows Forms], using the designer
- multipane user interface
ms.assetid: c3f9294d-a26c-4198-9242-f237f55f7573
ms.openlocfilehash: d0faf86ce31dad6bc053b5af8902e500d2b1c75b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33529872"
---
# <a name="how-to-create-a-multipane-user-interface-with-windows-forms-using-the-designer"></a>Практическое руководство. Создание пользовательского интерфейса с несколькими областями с использованием форм Windows Forms с помощью конструктора
В следующей процедуре вы создадите с несколькими областями пользовательского интерфейса, которая аналогична той, которая используется в Microsoft Outlook с **папки** списка, **сообщений** области и **предварительногопросмотра** области. Такое расположение элементов достигается главным образом за счет закрепления элементов управления формы.  
  
 При закреплении элемента управления, вы можете определить, какие края родительский контейнер элемента управления он прикреплен к. Таким образом Если задать <xref:System.Windows.Forms.SplitContainer.Dock%2A> свойства <xref:System.Windows.Forms.DockStyle.Right>, правый край элемента управления будет прикреплен к правым краем родительского элемента управления. Кроме того закрепленной края элемента управления изменяется в соответствии с элементом управления контейнера. Дополнительные сведения о том, как <xref:System.Windows.Forms.SplitContainer.Dock%2A> работает, в разделе [как: закрепление элементов управления Windows Forms](../../../../docs/framework/winforms/controls/how-to-dock-controls-on-windows-forms.md).  
  
 Эта процедура предназначена для расположения <xref:System.Windows.Forms.SplitContainer> и других элементов управления в форме, а не на добавление функциональности для имитации Microsoft Outlook.  
  
 Для создания пользовательского интерфейса, поместите все элементы управления внутри <xref:System.Windows.Forms.SplitContainer> управления, который содержит <xref:System.Windows.Forms.TreeView> управления на левой панели. На правой панели <xref:System.Windows.Forms.SplitContainer> содержит второй элемент управления <xref:System.Windows.Forms.SplitContainer> управления <xref:System.Windows.Forms.ListView> управления выше <xref:System.Windows.Forms.RichTextBox> элемента управления. Эти <xref:System.Windows.Forms.SplitContainer> элементы управления позволяют независимо изменять размер других элементов управления в форме. Вы можете адаптировать в этой процедуре для создания пользовательских интерфейсов собственные методы.  
  
> [!NOTE]
>  Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска. Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** . Дополнительные сведения см. в статье [Настройка параметров разработки в Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-create-an-outlook-style-user-interface-at-design-time"></a>Чтобы создать пользовательский интерфейс типа Outlook во время разработки  
  
1.  Создайте новый проект приложения Windows. Дополнительные сведения см. в разделе [Практическое руководство. Создание проекта приложения Windows](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa).  
  
2.  Перетащите <xref:System.Windows.Forms.SplitContainer> управления из **элементов** в форму. В **свойства** задайте <xref:System.Windows.Forms.SplitContainer.Dock%2A> свойства <xref:System.Windows.Forms.DockStyle.Fill>.  
  
3.  Перетащите <xref:System.Windows.Forms.TreeView> управления из **элементов** к левой панели <xref:System.Windows.Forms.SplitContainer> элемента управления. В **свойства** задайте <xref:System.Windows.Forms.SplitContainer.Dock%2A> свойства <xref:System.Windows.Forms.DockStyle.Left> , щелкнув по левой панели редактора значений, открывается при нажатии кнопки со стрелкой вниз.  
  
4.  Перетащите еще одно <xref:System.Windows.Forms.SplitContainer> управления из **элементов**; поместите его в правой панели <xref:System.Windows.Forms.SplitContainer> элемент управления, добавленный в форму. В **свойства** задайте <xref:System.Windows.Forms.SplitContainer.Dock%2A> свойства <xref:System.Windows.Forms.DockStyle.Fill> и <xref:System.Windows.Forms.SplitContainer.Orientation%2A> свойства <xref:System.Windows.Forms.Orientation.Horizontal>.  
  
5.  Перетащите <xref:System.Windows.Forms.ListView> управления из **элементов** на верхнюю панель второго <xref:System.Windows.Forms.SplitContainer> элемент управления, добавленный в форму. Задайте для свойства <xref:System.Windows.Forms.SplitContainer.Dock%2A> элемента управления <xref:System.Windows.Forms.ListView> значение <xref:System.Windows.Forms.DockStyle.Fill>.  
  
6.  Перетащите <xref:System.Windows.Forms.RichTextBox> управления из **элементов** в нижнюю панель второго <xref:System.Windows.Forms.SplitContainer> элемента управления. Задайте для свойства <xref:System.Windows.Forms.SplitContainer.Dock%2A> элемента управления <xref:System.Windows.Forms.RichTextBox> значение <xref:System.Windows.Forms.DockStyle.Fill>.  
  
     На этом этапе Если нажать клавишу F5 для запуска приложения, в форме отображаются трех частей пользовательского интерфейса, аналогичного тому, который Microsoft Outlook.  
  
    > [!NOTE]
    >  При переводе указатель мыши над любой из разделителей в <xref:System.Windows.Forms.SplitContainer> элементов управления, вы можете изменить размер внутреннего измерений.  
  
     На этом этапе разработки приложения сконструированных сложного пользовательского интерфейса. Следующим шагом будет переходить к программированию самого приложения, возможно, подключившись <xref:System.Windows.Forms.TreeView> управления и <xref:System.Windows.Forms.ListView> элементов управления, к какому-либо из источника данных. Дополнительные сведения о подключении элементов управления к данным см. в разделе [привязка данных и Windows Forms](../../../../docs/framework/winforms/data-binding-and-windows-forms.md).  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.SplitContainer>  
 [Элемент управления SplitContainer](../../../../docs/framework/winforms/controls/splitcontainer-control-windows-forms.md)
