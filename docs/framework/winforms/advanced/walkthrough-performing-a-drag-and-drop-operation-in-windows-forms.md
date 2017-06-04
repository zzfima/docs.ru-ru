---
title: "Walkthrough: Performing a Drag-and-Drop Operation in Windows Forms | Microsoft Docs"
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
  - "Windows Forms, drag and drop operations"
  - "drag and drop, Windows Forms"
ms.assetid: eb66f6bf-4a7d-4c2d-b276-40fefb2d3b6c
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Walkthrough: Performing a Drag-and-Drop Operation in Windows Forms
Для выполнения операций перетаскивания в приложениях Windows необходимо обрабатывать последовательность событий, главным образом события <xref:System.Windows.Forms.Control.DragEnter>, <xref:System.Windows.Forms.Control.DragLeave> и <xref:System.Windows.Forms.Control.DragDrop>.  Перетаскивание можно с легкостью организовать при работе со сведениями, доступными через аргументы этих событий.  
  
## Перенос данных  
 Все операции перетаскивания начинаются с переноса данных.  Функциональные возможности, позволяющие собрать данные при начале перетаскивания, реализуются в методе <xref:System.Windows.Forms.Control.DoDragDrop%2A>.  
  
 В следующем примере событие <xref:System.Windows.Forms.Control.MouseDown> используется для начала операции перетаскивания, так как это первое, что делает интуитивно пользователь \(большинство операций перетаскивания начинаются с отпущенной кнопкой мыши\).  Однако следует учесть, что для инициализации процедуры перетаскивания может использоваться любое событие.  
  
> [!NOTE]
>  Некоторые элементы управления имеют специальные события, относящиеся к перетаскиванию.  Например, элементы управления <xref:System.Windows.Forms.ListView> и <xref:System.Windows.Forms.TreeView> имеют событие <xref:System.Windows.Forms.TreeView.ItemDrag>.  
  
#### Чтобы начать операцию переноса, выполните следующие действия.  
  
1.  в <xref:System.Windows.Forms.Control.MouseDown>событие элемента управления, где начинается, используется перетаскивание  `DoDragDrop` метод для задания сведений для перетаскивания и разрешенный перетаскивания будет иметь эффекта.  Дополнительные сведения см. в разделах <xref:System.Windows.Forms.DragEventArgs.Data%2A> и <xref:System.Windows.Forms.DragEventArgs.AllowedEffect%2A>.  
  
     В следующем примере показан способ инициализации операции переноса.  Элементом управления, в котором начинается перетаскивание, является <xref:System.Windows.Forms.Button>, перетаскиваемыми данными является строка, представляющая свойство <xref:System.Windows.Forms.Control.Text%2A> элемента управления <xref:System.Windows.Forms.Button>, а в качестве разрешенных действий устанавливаются копирование и перемещение.  
  
    ```vb  
    Private Sub Button1_MouseDown(ByVal sender As Object, ByVal e As System.Windows.Forms.MouseEventArgs) Handles Button1.MouseDown  
       Button1.DoDragDrop(Button1.Text, DragDropEffects.Copy Or DragDropEffects.Move)  
    End Sub  
  
    ```  
  
    ```csharp  
    private void button1_MouseDown(object sender,   
    System.Windows.Forms.MouseEventArgs e)  
    {  
       button1.DoDragDrop(button1.Text, DragDropEffects.Copy |   
          DragDropEffects.Move);  
    }  
  
    ```  
  
    > [!NOTE]
    >  В качестве параметра метода `DoDragDrop` можно использовать любые данные. В предыдущем примере использовалось свойство <xref:System.Windows.Forms.Control.Text%2A> элемента управления <xref:System.Windows.Forms.Button> \(вместо того чтобы жестко запрограммировать значение или получить значение из набора данных\), поскольку это свойство было связано с местом расположения данных, которые требовалось перенести \(элемент управления <xref:System.Windows.Forms.Button>\).  Помните об этом при реализации операций перетаскивания в приложениях Windows.  
  
 Во время выполнения операции перетаскивания можно обрабатывать событие <xref:System.Windows.Forms.Control.QueryContinueDrag>, которое "запрашивает разрешение" системы на продолжение операции перетаскивания.  При обработке этого метода удобно также вызывать методы, влияющие на операцию перетаскивания, таких как развертывание объекта <xref:System.Windows.Forms.TreeNode> в элементе управления <xref:System.Windows.Forms.TreeView>, когда курсор находится над ним.  
  
## Освобождение данных  
 После начала операции переноса данных из определенной области в форме Windows Form или из элемента управления, необходимо эти данные куда\-либо поместить.  При прохождении курсора через область формы или элемент управления, которые правильно настроены для освобождения данных, вид курсора изменится.  Любая область внутри формы Windows Form или элемента управления может быть настроена для приема перетащенных данных путем установки свойства <xref:System.Windows.Forms.Control.AllowDrop%2A> и обработки событий <xref:System.Windows.Forms.Control.DragEnter> и <xref:System.Windows.Forms.Control.DragDrop>.  
  
#### Чтобы осуществить освобождение данных, выполните следующие действия.  
  
1.  Задайте значение "true" свойству <xref:System.Windows.Forms.Control.AllowDrop%2A>.  
  
2.  Убедитесь, что перетаскиваемые данные являются допустимым типом для события `DragEnter` элемента управления, в который осуществляется перетаскивание \(в данном случае этим типом является <xref:System.Windows.Forms.Control.Text%2A>\).  Затем в коде для эффекта, возникающего после освобождения данных, задайте значение перечисления <xref:System.Windows.Forms.DragDropEffects>.  Дополнительные сведения см. в разделе <xref:System.Windows.Forms.DragEventArgs.Effect%2A>.  
  
    ```vb  
    Private Sub TextBox1_DragEnter(ByVal sender As Object, ByVal e As System.Windows.Forms.DragEventArgs) Handles TextBox1.DragEnter  
       If (e.Data.GetDataPresent(DataFormats.Text)) Then  
         e.Effect = DragDropEffects.Copy  
       Else  
         e.Effect = DragDropEffects.None  
       End If  
    End Sub  
  
    ```  
  
    ```csharp  
    private void textBox1_DragEnter(object sender,   
    System.Windows.Forms.DragEventArgs e)  
    {  
       if (e.Data.GetDataPresent(DataFormats.Text))   
          e.Effect = DragDropEffects.Copy;  
       else  
          e.Effect = DragDropEffects.None;  
    }  
  
    ```  
  
    > [!NOTE]
    >  Можно определить собственные форматы <xref:System.Windows.Forms.DataFormats>, указав собственный объект в качестве параметра <xref:System.Object> метода <xref:System.Windows.Forms.DataObject.SetData%2A>.  Убедитесь, что при выполнении этого действия указанный объект можно сериализовать.  Дополнительные сведения см. в разделе [Интерфейс ISerializable](frlrfSystemRuntimeSerializationISerializableClassTopic).  
  
3.  В событии <xref:System.Windows.Forms.Control.DragDrop> для элемента управления, в котором будут размещены данные, используйте метод <xref:System.Windows.Forms.DataObject.GetData%2A> для получения перетаскиваемых данных.  Дополнительные сведения см. в разделе [Свойство DtaObject.Data](frlrfSystemSecurityCryptographyXmlDataObjectClassDataTopic).  
  
     В показанном ниже примере элемент управления <xref:System.Windows.Forms.TextBox> является элементом управления, в который переносятся данные \(в котором будет выполнено освобождение данных\).  В этом коде свойство <xref:System.Windows.Forms.Control.Text%2A> элемента управления <xref:System.Windows.Forms.TextBox> устанавливается равным перетаскиваемым данным.  
  
    ```vb  
    Private Sub TextBox1_DragDrop(ByVal sender As Object, ByVal e As System.Windows.Forms.DragEventArgs) Handles TextBox1.DragDrop  
       TextBox1.Text = e.Data.GetData(DataFormats.Text).ToString  
    End Sub  
  
    ```  
  
    ```csharp  
    private void textBox1_DragDrop(object sender,   
    System.Windows.Forms.DragEventArgs e)  
    {  
       textBox1.Text = e.Data.GetData(DataFormats.Text).ToString();  
    }  
  
    ```  
  
    > [!NOTE]
    >  Кроме того, можно работать со свойством <xref:System.Windows.Forms.DragEventArgs.KeyState%2A>: в зависимости от клавиш, нажатых во время операции перетаскивания, происходят определенные действия \(например, при нажатии клавиши CTRL обычно происходит копирование переносимых данных\).  
  
## См. также  
 [How to: Add Data to the Clipboard](../../../../docs/framework/winforms/advanced/how-to-add-data-to-the-clipboard.md)   
 [How to: Retrieve Data from the Clipboard](../../../../docs/framework/winforms/advanced/how-to-retrieve-data-from-the-clipboard.md)   
 [Drag\-and\-Drop Operations and Clipboard Support](../../../../docs/framework/winforms/advanced/drag-and-drop-operations-and-clipboard-support.md)