---
title: Практическое руководство. Включение автозаполнения в элементах управления ToolStrip в Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- AutoComplete [Windows Forms], examples
- toolbars [Windows Forms], AutoComplete
- examples [Windows Forms], toolbars
- AutoComplete [Windows Forms], enabling in toolbars
- ToolStripComboBox class [Windows Forms], examples
- ToolStrip control [Windows Forms], AutoComplete
ms.assetid: fd66d085-1af1-45d4-930a-cde944da2e16
ms.openlocfilehash: 301f1b156bbaee5c5f7be95e972ee1ebaa83777f
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69963613"
---
# <a name="how-to-enable-autocomplete-in-toolstrip-controls-in-windows-forms"></a>Практическое руководство. Включение автозаполнения в элементах управления ToolStrip в Windows Forms
Следующая процедура сочетает <xref:System.Windows.Forms.ToolStripLabel> <xref:System.Windows.Forms.ToolStripComboBox> с, которая может быть отброшена для отображения списка элементов, например недавно посещенных веб-узлов. Если пользователь вводит символ, совпадающий с первым символом одного из элементов списка, элемент сразу же отображается.  
  
> [!NOTE]
> Автоматическое заполнение работает `ToolStrip` с элементами управления так же, как и с традиционными элементами управления <xref:System.Windows.Forms.ComboBox> , <xref:System.Windows.Forms.TextBox>такими как и.  
  
### <a name="to-enable-autocomplete-in-a-toolstrip-control"></a>Включение автозаполнения в элементе управления ToolStrip  
  
1. <xref:System.Windows.Forms.ToolStrip> Создайте элемент управления и добавьте в него элементы.  
  
    ```vb  
    ToolStrip1 = New System.Windows.Forms.ToolStrip  
    ToolStrip1.Items.AddRange(New System.Windows.Forms.ToolStripItem()_  
        {ToolStripLabel1, ToolStripComboBox1})  
    ```  
  
    ```csharp  
    toolStrip1 = new System.Windows.Forms.ToolStrip();  
    toolStrip1.Items.AddRange(new System.Windows.Forms.ToolStripItem[]   
        {toolStripLabel1, toolStripComboBox1});  
    ```  
  
2. Установите свойство метки и поля со списком таким образом, чтобы <xref:System.Windows.Forms.ToolStripItemOverflow.Never> список всегда был доступен независимо от размера формы. <xref:System.Windows.Forms.ToolStripItem.Overflow%2A>  
  
    ```vb  
    ToolStripLabel1.Overflow = _  
        System.Windows.Forms.ToolStripItemOverflow.Never  
    ToolStripComboBox1.Overflow = _  
        System.Windows.Forms.ToolStripItemOverflow.Never  
    ```  
  
    ```csharp  
    toolStripLabel1.Overflow = _  
        System.Windows.Forms.ToolStripItemOverflow.Never  
    toolStripComboBox1.Overflow = System.Windows.Forms.ToolStripItemOverflow.Never  
    ```  
  
3. Добавление слов в коллекцию <xref:System.Windows.Forms.ToolStripComboBox> Items элемента управления.  
  
    ```vb  
    ToolStripComboBox1.Items.AddRange(New Object() {"First Item", _  
        "Second Item", "Third Item"})  
    ```  
  
    ```csharp  
    toolStripComboBox1.Items.AddRange(new object[] {"First item", "Second item", "Third item"});  
    ```  
  
4. Задайте для <xref:System.Windows.Forms.ComboBox.AutoCompleteMode%2A> <xref:System.Windows.Forms.AutoCompleteMode.Append>свойства поля со списком значение.  
  
    ```vb  
    ToolStripComboBox1.AutoCompleteMode = _  
        System.Windows.Forms.AutoCompleteMode.Append  
    ```  
  
    ```csharp  
    toolStripComboBox1.AutoCompleteMode = System.Windows.Forms.AutoCompleteMode.Append;  
    ```  
  
5. Задайте для <xref:System.Windows.Forms.ComboBox.AutoCompleteSource%2A> <xref:System.Windows.Forms.AutoCompleteSource.ListItems>свойства поля со списком значение.  
  
    ```vb  
    ToolStripComboBox1.AutoCompleteSource = _  
        System.Windows.Forms.AutoCompleteSource.ListItems  
    ```  
  
    ```csharp  
    toolStripComboBox1.AutoCompleteSource = System.Windows.Forms.AutoCompleteSource.ListItems;  
    ```  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStripLabel>
- <xref:System.Windows.Forms.ToolStripComboBox>
- <xref:System.Windows.Forms.ToolStripComboBox.AutoCompleteMode%2A>
- <xref:System.Windows.Forms.ToolStripComboBox.AutoCompleteSource%2A>
- [Общие сведения об элементе управления ToolStrip](toolstrip-control-overview-windows-forms.md)
- [Архитектура элемента управления ToolStrip](toolstrip-control-architecture.md)
- [Технологии, положенные в основу работы элемента управления ToolStrip](toolstrip-technology-summary.md)
