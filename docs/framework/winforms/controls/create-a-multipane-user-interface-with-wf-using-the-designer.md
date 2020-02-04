---
title: Создание пользовательского интерфейса с несколькими панелями с помощью конструктора
ms.date: 03/30/2017
helpviewer_keywords:
- user interface [Windows Forms], multipane
- SplitContainer control [Windows Forms], using the designer
- multipane user interface
ms.assetid: c3f9294d-a26c-4198-9242-f237f55f7573
ms.openlocfilehash: 6b41d538f1cd1633cec51c89e27adf3c5b47f9a6
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76737273"
---
# <a name="how-to-create-a-multipane-user-interface-with-windows-forms-using-the-designer"></a>Практическое руководство. Создание пользовательского интерфейса с несколькими областями с использованием форм Windows Forms с помощью конструктора
В следующей процедуре будет создан пользовательский интерфейс с несколькими панелями, аналогичный тому, который используется в Microsoft Outlook, со списком **папок** , панелью **сообщений** и областью **просмотра** . Это достигается главным путем закрепления элементов управления в форме.

 При закреплении элемента управления определяется граница родительского контейнера, к которому прикрепляется элемент управления. Таким образом, если для свойства <xref:System.Windows.Forms.SplitContainer.Dock%2A> задано значение <xref:System.Windows.Forms.DockStyle.Right>, правый элемент управления будет закреплен за правым краю родительского элемента управления. Кроме того, размер закрепленного края элемента управления изменяется в соответствии с его контейнерным элементом управления. Дополнительные сведения о том, как работает свойство <xref:System.Windows.Forms.SplitContainer.Dock%2A>, см. в разделе [как закреплять элементы управления в Windows Forms](how-to-dock-controls-on-windows-forms.md).

 Эта процедура посвящена размещению <xref:System.Windows.Forms.SplitContainer> и других элементов управления в форме, а не добавлению функций, позволяющих приложению имитировать Microsoft Outlook.

 Чтобы создать этот пользовательский интерфейс, поместите все элементы управления в элемент управления <xref:System.Windows.Forms.SplitContainer>, который содержит элемент управления <xref:System.Windows.Forms.TreeView> на панели слева. Правая панель элемента управления <xref:System.Windows.Forms.SplitContainer> содержит второй элемент управления <xref:System.Windows.Forms.SplitContainer> с элементом управления <xref:System.Windows.Forms.ListView> над элементом управления <xref:System.Windows.Forms.RichTextBox>. Эти <xref:System.Windows.Forms.SplitContainer> элементы управления позволяют независимо изменять размер других элементов управления в форме. Вы можете адаптировать методики этой процедуры для создания собственных пользовательских интерфейсов.

## <a name="to-create-an-outlook-style-user-interface-at-design-time"></a>Создание пользовательского интерфейса в стиле Outlook во время разработки

1. Создайте новый проект приложения Windows (**файл** > **Новый** > **проект** > **Visual C#**  или **Visual Basic** > **классический Настольный компьютер** > **приложение**).

2. Перетащите элемент управления <xref:System.Windows.Forms.SplitContainer> из **области элементов** в форму. В окне **Свойства** присвойте свойству <xref:System.Windows.Forms.SplitContainer.Dock%2A> значение <xref:System.Windows.Forms.DockStyle.Fill>.

3. Перетащите элемент управления <xref:System.Windows.Forms.TreeView> из **области элементов** в левую панель элемента управления <xref:System.Windows.Forms.SplitContainer>. В окне **Свойства** присвойте свойству <xref:System.Windows.Forms.SplitContainer.Dock%2A> значение <xref:System.Windows.Forms.DockStyle.Left>, щелкнув левую панель в редакторе значений, отображаемую при нажатии кнопки со стрелкой вниз.

4. Перетащите другой элемент управления <xref:System.Windows.Forms.SplitContainer> из **панели элементов**. Поместите его на правой панели элемента управления <xref:System.Windows.Forms.SplitContainer>, добавленного в форму. В окне **Свойства** задайте для свойства <xref:System.Windows.Forms.SplitContainer.Dock%2A> значение <xref:System.Windows.Forms.DockStyle.Fill>, а для свойства <xref:System.Windows.Forms.SplitContainer.Orientation%2A> значение <xref:System.Windows.Forms.Orientation.Horizontal>.

5. Перетащите элемент управления <xref:System.Windows.Forms.ListView> из **области элементов** в верхнюю панель второго элемента управления <xref:System.Windows.Forms.SplitContainer>, добавленного в форму. Задайте для свойства <xref:System.Windows.Forms.SplitContainer.Dock%2A> элемента управления <xref:System.Windows.Forms.ListView> значение <xref:System.Windows.Forms.DockStyle.Fill>.

6. Перетащите элемент управления <xref:System.Windows.Forms.RichTextBox> из **области элементов** на нижнюю панель второго элемента управления <xref:System.Windows.Forms.SplitContainer>. Задайте для свойства <xref:System.Windows.Forms.SplitContainer.Dock%2A> элемента управления <xref:System.Windows.Forms.RichTextBox> значение <xref:System.Windows.Forms.DockStyle.Fill>.

     На этом этапе, если нажать клавишу F5 для запуска приложения, в форме отобразится пользовательский интерфейс с тремя частями, аналогичный Microsoft Outlook.

    > [!NOTE]
    > При помещении указателя мыши на любую из разделителей элементов управления <xref:System.Windows.Forms.SplitContainer> можно изменить размер внутренних измерений.

На этом этапе разработки приложения был создан сложный пользовательский интерфейс. Следующий шаг продолжается в программировании самого приложения, возможно, путем подключения элемента управления <xref:System.Windows.Forms.TreeView> и <xref:System.Windows.Forms.ListView> элементов управления к определенному источнику данных. Дополнительные сведения о подключении элементов управления к данным см. в разделе [Привязка данных и Windows Forms](../data-binding-and-windows-forms.md).

## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Forms.SplitContainer>
- [Элемент управления SplitContainer](splitcontainer-control-windows-forms.md)
