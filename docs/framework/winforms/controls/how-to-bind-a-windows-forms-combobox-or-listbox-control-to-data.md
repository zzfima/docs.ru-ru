---
title: "Практическое руководство. Связывание элемента управления ComboBox или ListBox с данными в Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "элементы управления с привязкой, поля со списком"
  - "поля со списком, привязка данных"
  - "ComboBox - элемент управления [Windows Forms], привязка данных"
  - "данные [Windows Forms], привязка к элементам управления"
  - "привязка данных, поля со списком"
  - "элементы управления с привязкой к данным, Windows Forms"
  - "списки, привязка данных"
  - "ListBox - элемент управления [Windows Forms], привязка данных"
  - "элементы управления Windows Forms, привязка данных"
ms.assetid: dfd7f081-8bea-4a41-86a3-86a1934828ef
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# Практическое руководство. Связывание элемента управления ComboBox или ListBox с данными в Windows Forms
Можно связать элемент управления <xref:System.Windows.Forms.ComboBox> и элемент управления <xref:System.Windows.Forms.ListBox> для выполнения таких задач как просмотр данных в базе данных, ввод новых данных и изменение существующих данных.  
  
### Чтобы выполнить привязку для элемента управления ComboBox или ListBox  
  
1.  Установка`DataSource`свойство объекту источника данных.  Возможные источники данных — связанная с данными <xref:System.Windows.Forms.BindingSource>, таблица данных, представление данных, набор данных, диспетчер представлений данных, массив, а также любой класс, реализующий интерфейс <xref:System.Collections.IList>.  Дополнительные сведения см. в разделе [Источники данных, поддерживаемые Windows Forms](../../../../docs/framework/winforms/data-sources-supported-by-windows-forms.md).  
  
2.  При привязке к таблице, параметр`DisplayMember`свойство имени столбца в источнике данных.  
  
     \- или \-  
  
     При привязке к элементу управления <xref:System.Collections.IList> укажите элемент отображения в качестве значения свойства типа в списке.  
  
    ```vb  
    Private Sub BindComboBox()  
      ComboBox1.DataSource = DataSet1.Tables("Suppliers")  
      ComboBox1.DisplayMember = "ProductName"  
    End Sub  
  
    ```  
  
    ```csharp  
    private void BindComboBox()  
    {  
      comboBox1.DataSource = dataSet1.Tables["Suppliers"];  
      comboBox1.DisplayMember = "ProductName";  
    }  
  
    ```  
  
    > [!NOTE]
    >  При привязке к источнику данных, который не реализует интерфейс <xref:System.ComponentModel.IBindingList>, например к <xref:System.Collections.ArrayList>, данные привязанного элемента управления не будут обновлены при обновлении источника данных.  Например, если при наличии поля со списком, привязанного к объекту <xref:System.Collections.ArrayList> в объект <xref:System.Collections.ArrayList> добавляются данные, эти новые элементы не появляются в поле со списком.  Однако можно обеспечить принудительное обновление поля со списком путем вызова методов <xref:System.Windows.Forms.BindingManagerBase.SuspendBinding%2A> и <xref:System.Windows.Forms.BindingManagerBase.ResumeBinding%2A> для экземпляра класса <xref:System.Windows.Forms.BindingContext>, к которому привязан элемент управления.  
  
## См. также  
 <xref:System.Windows.Forms.ComboBox>   
 <xref:System.Windows.Forms.ListBox>   
 [Связывание элементов управления Windows Forms с данными](../../../../docs/framework/winforms/windows-forms-data-binding.md)   
 [Связывание данных и Windows Forms](../../../../docs/framework/winforms/data-binding-and-windows-forms.md)   
 [Создание списка для выбора элементов в Windows Forms](../../../../docs/framework/winforms/controls/windows-forms-controls-used-to-list-options.md)