---
title: "Практическое руководство. Добавление кнопок загрузки, сохранения и отмены в элемент управления BindingNavigator в формах Windows Forms | Microsoft Docs"
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
  - "элементы управления [Windows Forms], управление"
  - "Элемент управления BindingNavigator [Windows Forms], добавление кнопок"
ms.assetid: faa33042-186e-4bb2-8798-17ceb987ec62
caps.latest.revision: 17
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 17
---
# Практическое руководство. Добавление кнопок загрузки, сохранения и отмены в элемент управления BindingNavigator в формах Windows Forms
Элемент управления <xref:System.Windows.Forms.BindingNavigator> является специализированным элементом управления <xref:System.Windows.Forms.ToolStrip>, который предназначен для навигации и управления привязанными к данным элементами управления формы.  
  
 Так как это элемент управления <xref:System.Windows.Forms.ToolStrip>, компонент <xref:System.Windows.Forms.BindingNavigator> может быть легко изменен для включения дополнительных или альтернативных команд для пользователя.  
  
 В следующей процедуре элемент управления <xref:System.Windows.Forms.TextBox> привязан к данным, а добавленный в форму элемент управления <xref:System.Windows.Forms.ToolStrip> дополнен кнопками загрузки, сохранения и отмены.  
  
### Чтобы добавить кнопки загрузки, сохранения и отмены в элемент BindingNavigator  
  
1.  Добавьте элемент управления <xref:System.Windows.Forms.TextBox> на форму.  
  
2.  Привяжите его к классу <xref:System.Windows.Forms.BindingSource>, который привязан к источнику данных.  Для этого примера класс <xref:System.Windows.Forms.BindingSource> привязан к базе данных.  
  
3.  Когда таблица данных и адаптер таблиц будут сгенерированы, перетащите элемент управления <xref:System.Windows.Forms.BindingNavigator> на форму.  
  
4.  На форме, привязанной к элементам управления, присвойте свойству <xref:System.Windows.Forms.BindingNavigator.BindingSource%2A> элемента управления <xref:System.Windows.Forms.BindingNavigator> значение <xref:System.Windows.Forms.BindingSource>.  
  
5.  Выберите элемент управления <xref:System.Windows.Forms.BindingNavigator>.  
  
6.  Щелкните глиф смарт\-тега \(![Глиф смарт&#45;тега](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.png "VS\_WinFormSmtTagGlyph")\), чтобы появилось диалоговое окно **Задачи BindingNavigator**, и выберите пункт **Изменение элементов**.  
  
     Появится окно **Редактор коллекции элементов**.  
  
7.  В окне **Редактор коллекции элементов** выполните следующие действия:  
  
    1.  Добавьте <xref:System.Windows.Forms.ToolStripSeparator> и три элемента <xref:System.Windows.Forms.ToolStripButton>, выбрав соответствующий тип элемента <xref:System.Windows.Forms.ToolStripItem> и нажав кнопку **Добавить**.  
  
    2.  Присвойте свойству кнопок <xref:System.Windows.Forms.ToolStripItem.Name%2A> соответственно значения `` LoadButton, `` SaveButton `` и CancelButton.  
  
    3.  Присвойте свойству кнопок <xref:System.Windows.Forms.ToolStripItem.Text%2A> значения `` Загрузить`,` Сохранить `` и Отмена.  
  
    4.  Присвойте свойству <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> каждой кнопки значение `` Text.  Также можно присвоить этому свойству значение `` Image `` или `` ImageAndText `` и задать отображаемое изображение в свойстве <xref:System.Windows.Forms.ToolStripItem.Image%2A>.  
  
    5.  Нажмите кнопку **ОК**, чтобы закрыть диалоговое окно. Кнопки будут добавлены в класс <xref:System.Windows.Forms.ToolStrip>.  
  
8.  Щелкните форму правой кнопкой мыши и выберите команду **Просмотреть код**.  
  
9. В редакторе кода найдите строку, которая загружает данные в адаптер таблиц.  Этот код был сгенерирован при установки привязки данных в этапе 2.  Код должен иметь следующий вид: `TableAdapterName.Fill(DataSetName.TableName)`.  Наиболее вероятно, что он будет в событии формы <xref:System.Windows.Forms.Form.Load>.  
  
10. Создайте обработчик события <xref:System.Windows.Forms.ToolStripItem.Click> для кнопки `T:System.Windows.Forms.ToolStripButton` `` **Загрузить**, созданной ранее, и переместите этот код загрузки данных в обработчик.  
  
     Теперь код должен выглядеть примерно следующим образом.  
  
     \[Visual Basic\]  
  
    ```  
    Private Sub LoadButton_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles LoadButton.Click  
        TableAdapterName.Fill(DataSetName.TableName)  
    End Sub  
    ```  
  
     \[C\#\]  
  
    ```  
    private void LoadButton_Click(System.Object sender,   
        System.EventArgs e)  
    {  
        TableAdapterName.Fill(DataSetName.TableName);  
    }  
    ```  
  
11. Создайте обработчик события <xref:System.Windows.Forms.ToolStripItem.Click> для кнопки <xref:System.Windows.Forms.ToolStripButton> `` **Сохранить**, созданной ранее, и напишите код для обновления данных в таблице, к которой привязан элемент управления.  
  
     \[Visual Basic\]  
  
    ```  
    Private Sub SaveButton_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles SaveButton.Click  
        TableAdapterName.Update(DataSetName.TableName)  
    End Sub  
    ```  
  
     \[C\#\]  
  
    ```  
    private void SaveButton_Click(System.Object sender,   
        System.EventArgs e)  
    {  
        TableAdapterName.Update(DataSetName.TableName);  
    }  
    ```  
  
    > [!NOTE]
    >  В некоторых случаях компонент <xref:System.Windows.Forms.BindingNavigator> уже содержит кнопку `` **Сохранить**, но код, сгенерированный конструктором Windows Forms, при этом отсутствует.  В этом случае приведенный выше код можно поместить в <xref:System.Windows.Forms.ToolStripItem.Click> обработчик событий кнопки, вместо создания полностью новой кнопки <xref:System.Windows.Forms.ToolStrip>.  Однако кнопка по умолчанию отключена, так что свойству <xref:System.Windows.Forms.ToolBarButton.Enabled%2A> кнопки необходимо присвоить значение `true`, чтобы кнопка работала правильно.  
  
12. Создайте обработчик события <xref:System.Windows.Forms.ToolStripItem.Click> для кнопки `` <xref:System.Windows.Forms.ToolStripButton> `` **Отмена**, созданной ранее, и напишите код для отмены любых изменений отображаемой записи данных.  
  
     \[Visual Basic\]  
  
    ```  
    Private Sub CancelButton_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles CancelButton.Click  
        BindingSourceName.CancelEdit()  
    End Sub  
    ```  
  
     \[C\#\]  
  
    ```  
    private void CancelButton_Click(System.Object sender, System.EventArgs e)  
    {  
        BindingSourceName.CancelEdit();  
    }  
    ```  
  
    > [!NOTE]
    >  Метод <xref:System.Windows.Forms.BindingSource.CancelEdit%2A> распространяется на строку данных.  Сохраните все изменения, сделанные при просмотре этой отдельной записи, до перехода к следующей записи.  
  
## См. также  
 <xref:System.Windows.Forms.BindingNavigator>   
 <xref:System.Windows.Forms.BindingSource>   
 <xref:System.Windows.Forms.ToolStrip>   
 [Элемент управления BindingNavigator](../../../../docs/framework/winforms/controls/bindingnavigator-control-windows-forms.md)   
 [Общие сведения о компоненте BindingSource](../../../../docs/framework/winforms/controls/bindingsource-component-overview.md)