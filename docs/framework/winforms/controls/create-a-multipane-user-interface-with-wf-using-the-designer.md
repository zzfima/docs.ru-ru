---
title: Практическое руководство. Создание пользовательского интерфейса с несколькими областями с использованием форм Windows Forms с помощью конструктора
ms.date: 03/30/2017
helpviewer_keywords:
- user interface [Windows Forms], multipane
- SplitContainer control [Windows Forms], using the designer
- multipane user interface
ms.assetid: c3f9294d-a26c-4198-9242-f237f55f7573
ms.openlocfilehash: 97888a77dfc731be591d5f0284e87f45ef7dc437
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69930166"
---
# <a name="how-to-create-a-multipane-user-interface-with-windows-forms-using-the-designer"></a>Практическое руководство. Создание пользовательского интерфейса с несколькими областями с использованием форм Windows Forms с помощью конструктора
В следующей процедуре будет создан пользовательский интерфейс с несколькими панелями, аналогичный тому, который используется в Microsoft Outlook, со списком **папок** , панелью **сообщений** и областью **просмотра** . Это достигается главным путем закрепления элементов управления в форме.

 При закреплении элемента управления определяется граница родительского контейнера, к которому прикрепляется элемент управления. Таким образом, если задать <xref:System.Windows.Forms.SplitContainer.Dock%2A> для <xref:System.Windows.Forms.DockStyle.Right>свойства значение, то правый элемент управления будет закреплен за правым краю родительского элемента управления. Кроме того, размер закрепленного края элемента управления изменяется в соответствии с его контейнерным элементом управления. Дополнительные сведения о принципах работы <xref:System.Windows.Forms.SplitContainer.Dock%2A> этого свойства см. [в разделе как Закреплять элементы управления](how-to-dock-controls-on-windows-forms.md)на Windows Forms.

 Эта процедура посвящена <xref:System.Windows.Forms.SplitContainer> размещению и другим элементам управления в форме, а не добавлению функциональных возможностей, позволяющих приложению имитировать Microsoft Outlook.

 Чтобы создать этот пользовательский интерфейс, поместите все элементы <xref:System.Windows.Forms.SplitContainer> управления в элемент управления, который <xref:System.Windows.Forms.TreeView> содержит элемент управления на панели слева. Правая панель <xref:System.Windows.Forms.SplitContainer> элемента управления содержит второй <xref:System.Windows.Forms.SplitContainer> элемент управления <xref:System.Windows.Forms.RichTextBox> с <xref:System.Windows.Forms.ListView> элементом управления над элементом управления. Эти <xref:System.Windows.Forms.SplitContainer> элементы управления позволяют независимо изменять размер других элементов управления в форме. Вы можете адаптировать методики этой процедуры для создания собственных пользовательских интерфейсов.

## <a name="to-create-an-outlook-style-user-interface-at-design-time"></a>Создание пользовательского интерфейса в стиле Outlook во время разработки

1. Создание нового проекта приложения Windows (**файл** > **создать** > **проект** > **визуальный C#**  элемент или **Visual Basic** > **классический рабочий стол**  > ) **Windows Forms приложение**).

2. Перетащите элемент управления из **области элементов** в форму. <xref:System.Windows.Forms.SplitContainer> В окне **Свойства** присвойте свойству <xref:System.Windows.Forms.SplitContainer.Dock%2A> значение <xref:System.Windows.Forms.DockStyle.Fill>.

3. Перетащите элемент управления с **панели элементов** на левую панель <xref:System.Windows.Forms.SplitContainer> элемента управления. <xref:System.Windows.Forms.TreeView> В окне **Свойства** задайте <xref:System.Windows.Forms.SplitContainer.Dock%2A> для <xref:System.Windows.Forms.DockStyle.Left> свойства значение, щелкнув левую панель в редакторе значений, отображаемую при нажатии кнопки со стрелкой вниз.

4. Перетащите другой <xref:System.Windows.Forms.SplitContainer> элемент управления из **панели элементов**, поместите его на правую панель <xref:System.Windows.Forms.SplitContainer> элемента управления, добавленного в форму. В окне **Свойства** задайте <xref:System.Windows.Forms.SplitContainer.Dock%2A> <xref:System.Windows.Forms.DockStyle.Fill> свойству<xref:System.Windows.Forms.Orientation.Horizontal>значение, а свойству—значение.<xref:System.Windows.Forms.SplitContainer.Orientation%2A>

5. Перетащите элемент управления из **области элементов** в верхнюю панель второго <xref:System.Windows.Forms.SplitContainer> элемента управления, добавленного в форму. <xref:System.Windows.Forms.ListView> Задайте для свойства <xref:System.Windows.Forms.SplitContainer.Dock%2A> элемента управления <xref:System.Windows.Forms.ListView> значение <xref:System.Windows.Forms.DockStyle.Fill>.

6. Перетащите элемент управления с **панели элементов** на нижнюю панель второго <xref:System.Windows.Forms.SplitContainer> элемента управления. <xref:System.Windows.Forms.RichTextBox> Задайте для свойства <xref:System.Windows.Forms.SplitContainer.Dock%2A> элемента управления <xref:System.Windows.Forms.RichTextBox> значение <xref:System.Windows.Forms.DockStyle.Fill>.

     На этом этапе, если нажать клавишу F5 для запуска приложения, в форме отобразится пользовательский интерфейс с тремя частями, аналогичный Microsoft Outlook.

    > [!NOTE]
    > При помещении указателя мыши на любую из разделителей внутри <xref:System.Windows.Forms.SplitContainer> элементов управления можно изменить размер внутренних измерений.

На этом этапе разработки приложения был создан сложный пользовательский интерфейс. Следующий шаг продолжается в программировании самого приложения, возможно, путем подключения <xref:System.Windows.Forms.TreeView> элемента управления и <xref:System.Windows.Forms.ListView> элементов управления к определенному источнику данных. Дополнительные сведения о подключении элементов управления к данным см. в разделе [Привязка данных и Windows Forms](../data-binding-and-windows-forms.md).

## <a name="see-also"></a>См. также

- <xref:System.Windows.Forms.SplitContainer>
- [Элемент управления SplitContainer](splitcontainer-control-windows-forms.md)
