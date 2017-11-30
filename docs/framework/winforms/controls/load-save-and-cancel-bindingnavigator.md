---
title: "Практическое руководство. Добавление кнопок загрузки, сохранения и отмены в элемент управления BindingNavigator в формах Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [Windows Forms], manipulating
- BindingNavigator control [Windows Forms], adding buttons
ms.assetid: faa33042-186e-4bb2-8798-17ceb987ec62
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4bc4f53c404e3767b9f98ca5ab46b19db31f9c6e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-add-load-save-and-cancel-buttons-to-the-windows-forms-bindingnavigator-control"></a>Практическое руководство. Добавление кнопок загрузки, сохранения и отмены в элемент управления BindingNavigator в формах Windows Forms
<xref:System.Windows.Forms.BindingNavigator> Управления является специализированным <xref:System.Windows.Forms.ToolStrip> элемент управления, который предназначен для навигации и управления элементами управления в форме, привязанных к данным.  
  
 Так как это <xref:System.Windows.Forms.ToolStrip> управления <xref:System.Windows.Forms.BindingNavigator> компонента можно легко изменить для включения дополнительных или альтернативных команд для пользователя.  
  
 В следующей процедуре <xref:System.Windows.Forms.TextBox> элемент управления привязан к данным и <xref:System.Windows.Forms.ToolStrip> элемента управления, который добавляется в форму изменяются так, чтобы включить загрузки, сохранения и кнопки отмены.  
  
### <a name="to-add-load-save-and-cancel-buttons-to-the-bindingnavigator-component"></a>Чтобы добавить нагрузки, сохранить и Отмена кнопки для компонента BindingNavigator  
  
1.  Добавьте элемент управления <xref:System.Windows.Forms.TextBox> в форму.  
  
2.  Привяжите его к <xref:System.Windows.Forms.BindingSource>, который привязан к источнику данных. В этом примере <xref:System.Windows.Forms.BindingSource> привязан к базе данных.  
  
3.  После создания набора данных и адаптер таблицы перетащите <xref:System.Windows.Forms.BindingNavigator> на форму элемент управления.  
  
4.  Задать <xref:System.Windows.Forms.BindingNavigator> элемента управления <xref:System.Windows.Forms.BindingNavigator.BindingSource%2A> свойства <xref:System.Windows.Forms.BindingSource> формы, который привязан к элементам управления.  
  
5.  Выберите элемент управления <xref:System.Windows.Forms.BindingNavigator>.  
  
6.  Щелкните глиф смарт-тега (![глиф смарт-тега](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) таким образом **задачи BindingNavigator** диалоговое окно и выберите пункт **изменение элементов**.  
  
     **Редактор коллекции элементов** отображается.  
  
7.  В **редактор коллекции элементов**, выполните следующие действия:  
  
    1.  Добавить <xref:System.Windows.Forms.ToolStripSeparator> и три <xref:System.Windows.Forms.ToolStripButton> элементы, выбрав соответствующий тип <xref:System.Windows.Forms.ToolStripItem> и щелкнув **добавить** кнопки.  
  
    2.  Задать <xref:System.Windows.Forms.ToolStripItem.Name%2A> свойства кнопки, чтобы**LoadButton**,**SaveButton**, и**CancelButton**соответственно.  
  
    3.  Задать <xref:System.Windows.Forms.ToolStripItem.Text%2A> свойства кнопки, чтобы**нагрузки** `,` **Сохранить**, и**отменить**.  
  
    4.  Задать <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> для каждой из кнопок, чтобы**текст**. Кроме того, можно задать это свойство**изображения**или**ImageAndText**и задать изображение, отображаемое в <xref:System.Windows.Forms.ToolStripItem.Image%2A> свойство.  
  
    5.  Нажмите кнопку **ОК** чтобы закрыть диалоговое окно. Добавляются кнопки <xref:System.Windows.Forms.ToolStrip>.  
  
8.  Щелкните форму правой кнопкой мыши и выберите **Просмотр кода**.  
  
9. В редакторе кода найдите строку кода, которая загружает данные в адаптер таблицы. Этот код был создан при настройке привязки данных в шаге 2. Код должен быть примерно следующего содержания: `TableAdapterName.Fill(DataSetName.TableName)`. Он будет большинство скорее всего, в форме <xref:System.Windows.Forms.Form.Load> событий.  
  
10. Создайте обработчик событий для <xref:System.Windows.Forms.ToolStripItem.Click> событие**нагрузки** <xref:System.Windows.Forms.ToolStripButton> созданной ранее и переместите этот код загрузки данных в нее.  
  
     Код должен выглядеть следующим образом:  
  
    ```vb  
    Private Sub LoadButton_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles LoadButton.Click  
        TableAdapterName.Fill(DataSetName.TableName)  
    End Sub  
    ```  
  
    ```csharp  
    private void LoadButton_Click(System.Object sender,   
        System.EventArgs e)  
    {  
        TableAdapterName.Fill(DataSetName.TableName);  
    }  
    ```  
  
11. Создайте обработчик событий для <xref:System.Windows.Forms.ToolStripItem.Click> событие **Сохранить** <xref:System.Windows.Forms.ToolStripButton> созданную ранее, и напишите код для обновления данных в таблице элемент управления привязан к.  
  
    ```vb  
    Private Sub SaveButton_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles SaveButton.Click  
        TableAdapterName.Update(DataSetName.TableName)  
    End Sub  
    ```  
  
    ```csharp  
    private void SaveButton_Click(System.Object sender,   
        System.EventArgs e)  
    {  
        TableAdapterName.Update(DataSetName.TableName);  
    }  
    ```  
  
    > [!NOTE]
    >  В некоторых случаях <xref:System.Windows.Forms.BindingNavigator> компонент уже будет иметь**Сохранить** кнопки, но код не будет были созданы с помощью конструктора Windows Forms. В этом случае можно поместить приведенного выше кода в <xref:System.Windows.Forms.ToolStripItem.Click> обработчик событий для кнопки, а не создавать полностью новой кнопки на <xref:System.Windows.Forms.ToolStrip>. Однако кнопка становится недоступной, по умолчанию, поэтому необходимо задать <xref:System.Windows.Forms.ToolBarButton.Enabled%2A> свойства кнопки, чтобы `true` иметь кнопка работала правильно.  
  
12. Создайте обработчик событий для <xref:System.Windows.Forms.ToolStripItem.Click> событие**отменить** <xref:System.Windows.Forms.ToolStripButton> созданной ранее и написать код для отмены любых изменений отображаемой записи данных.  
  
    ```vb  
    Private Sub CancelButton_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles CancelButton.Click  
        BindingSourceName.CancelEdit()  
    End Sub  
    ```  
  
    ```csharp  
    private void CancelButton_Click(System.Object sender, System.EventArgs e)  
    {  
        BindingSourceName.CancelEdit();  
    }  
    ```  
  
    > [!NOTE]
    >  <xref:System.Windows.Forms.BindingSource.CancelEdit%2A> Метод распространяется на строку данных. Сохраните все изменения, внесенные во время просмотра этой отдельной записи до перехода к следующей записи.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.BindingNavigator>  
 <xref:System.Windows.Forms.BindingSource>  
 <xref:System.Windows.Forms.ToolStrip>  
 [Элемент управления BindingNavigator](../../../../docs/framework/winforms/controls/bindingnavigator-control-windows-forms.md)  
 [Общие сведения о компоненте BindingSource](../../../../docs/framework/winforms/controls/bindingsource-component-overview.md)
