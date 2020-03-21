---
title: Практическое руководство. Включение автозаполнения для элементов управления ToolStrip
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
ms.openlocfilehash: 18b17aaea9d2354c03bb43f3fdd8d3779697cf58
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79142022"
---
# <a name="how-to-enable-autocomplete-in-toolstrip-controls-in-windows-forms"></a>Практическое руководство. Включение автозаполнения для элементов управления ToolStrip в Windows Forms
Следующая процедура сочетает <xref:System.Windows.Forms.ToolStripLabel> в <xref:System.Windows.Forms.ToolStripComboBox> себе, что может быть удален, чтобы показать список элементов, таких как недавно посетивший веб-сайты. Если пользователь вводит символ, который соответствует первому символу одного из элементов в списке, элемент немедленно отображается.  
  
> [!NOTE]
> Автоматическое завершение работает с `ToolStrip` элементами управления так <xref:System.Windows.Forms.ComboBox> <xref:System.Windows.Forms.TextBox>же, как он работает с традиционными элементами управления, такими как и .  
  
### <a name="to-enable-autocomplete-in-a-toolstrip-control"></a>Включить AutoComplete в управление ToolStrip  
  
1. Создайте <xref:System.Windows.Forms.ToolStrip> элементы управления и добавьте элементы к нему.  
  
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
  
2. Установите <xref:System.Windows.Forms.ToolStripItem.Overflow%2A> свойство этикетки и комбо-бокс, чтобы <xref:System.Windows.Forms.ToolStripItemOverflow.Never> список всегда был доступен независимо от размера формы.  
  
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
  
3. Добавьте слова в коллекцию элементов элемента <xref:System.Windows.Forms.ToolStripComboBox> управления.  
  
    ```vb  
    ToolStripComboBox1.Items.AddRange(New Object() {"First Item", _  
        "Second Item", "Third Item"})  
    ```  
  
    ```csharp  
    toolStripComboBox1.Items.AddRange(new object[] {"First item", "Second item", "Third item"});  
    ```  
  
4. Установите <xref:System.Windows.Forms.ComboBox.AutoCompleteMode%2A> свойство комбо-бокса. <xref:System.Windows.Forms.AutoCompleteMode.Append>  
  
    ```vb  
    ToolStripComboBox1.AutoCompleteMode = _  
        System.Windows.Forms.AutoCompleteMode.Append  
    ```  
  
    ```csharp  
    toolStripComboBox1.AutoCompleteMode = System.Windows.Forms.AutoCompleteMode.Append;  
    ```  
  
5. Установите <xref:System.Windows.Forms.ComboBox.AutoCompleteSource%2A> свойство комбо-бокса. <xref:System.Windows.Forms.AutoCompleteSource.ListItems>  
  
    ```vb  
    ToolStripComboBox1.AutoCompleteSource = _  
        System.Windows.Forms.AutoCompleteSource.ListItems  
    ```  
  
    ```csharp  
    toolStripComboBox1.AutoCompleteSource = System.Windows.Forms.AutoCompleteSource.ListItems;  
    ```  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStripLabel>
- <xref:System.Windows.Forms.ToolStripComboBox>
- <xref:System.Windows.Forms.ToolStripComboBox.AutoCompleteMode%2A>
- <xref:System.Windows.Forms.ToolStripComboBox.AutoCompleteSource%2A>
- [Общие сведения об элементе управления ToolStrip](toolstrip-control-overview-windows-forms.md)
- [Архитектура элемента управления ToolStrip](toolstrip-control-architecture.md)
- [Технологии, положенные в основу работы элемента управления ToolStrip](toolstrip-technology-summary.md)
