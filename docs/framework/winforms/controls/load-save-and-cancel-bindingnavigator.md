---
title: Добавление кнопок загрузки, сохранения и отмены в элемент управления BindingNavigator
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [Windows Forms], manipulating
- BindingNavigator control [Windows Forms], adding buttons
ms.assetid: faa33042-186e-4bb2-8798-17ceb987ec62
ms.openlocfilehash: ac862d163f1bd8b66f29160d836bc459e4bf4081
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745130"
---
# <a name="how-to-add-load-save-and-cancel-buttons-to-the-windows-forms-bindingnavigator-control"></a>Практическое руководство. Добавление кнопок загрузки, сохранения и отмены в элемент управления BindingNavigator в формах Windows Forms

Элемент управления <xref:System.Windows.Forms.BindingNavigator> — это специальный <xref:System.Windows.Forms.ToolStrip>ный элемент управления, предназначенный для навигации по элементам управления формы, которые привязаны к данным, и манипуляций с ними.

Поскольку это элемент управления <xref:System.Windows.Forms.ToolStrip>, компонент <xref:System.Windows.Forms.BindingNavigator> можно легко изменить, чтобы включить дополнительные или альтернативные команды для пользователя.

В следующей процедуре элемент управления <xref:System.Windows.Forms.TextBox> привязан к данным, а элемент управления <xref:System.Windows.Forms.ToolStrip>, добавляемый в форму, изменяется для включения кнопок загрузки, сохранения и отмены.

## <a name="add-load-save-and-cancel-buttons-to-the-bindingnavigator-component"></a>Добавление кнопок загрузки, сохранения и отмены в компонент BindingNavigator

1. В Visual Studio добавьте в форму элемент управления <xref:System.Windows.Forms.TextBox>.

2. Привяжите его к <xref:System.Windows.Forms.BindingSource>, привязанному к источнику данных. В этом примере <xref:System.Windows.Forms.BindingSource> привязан к базе данных.

3. После создания набора данных и адаптера таблицы перетащите элемент управления <xref:System.Windows.Forms.BindingNavigator> в форму.

4. Задайте для свойства <xref:System.Windows.Forms.BindingNavigator.BindingSource%2A> элемента управления <xref:System.Windows.Forms.BindingNavigator> <xref:System.Windows.Forms.BindingSource> в форме, привязанной к элементам управления.

5. Выберите элемент управления <xref:System.Windows.Forms.BindingNavigator>.

6. Щелкните глиф смарт-тега (![глиф смарт-тега](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")), чтобы увидеть диалоговое окно **Задачи BindingNavigator** , и выберите **изменить элементы**.

     Откроется **Редактор коллекции элементов** .

7. В **редакторе коллекции элементов**выполните следующие действия.

    1. Добавьте <xref:System.Windows.Forms.ToolStripSeparator> и три <xref:System.Windows.Forms.ToolStripButton> элементы, выбрав соответствующий тип <xref:System.Windows.Forms.ToolStripItem> и нажав кнопку **Добавить** .

    2. Задайте для свойства <xref:System.Windows.Forms.ToolStripItem.Name%2A> кнопок значение **лоадбуттон**, **савебуттон**и **CancelButton**соответственно.

    3. Задайте для свойства <xref:System.Windows.Forms.ToolStripItem.Text%2A> кнопок значение **загружать**, **сохранять**и **отменять**.

    4. Присвойте свойству <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> для каждой кнопки значение **Text**. Кроме того, можно задать для этого свойства значение **Image** или **имажеандтекст**и задать отображение изображения в свойстве <xref:System.Windows.Forms.ToolStripItem.Image%2A>.

    5. Чтобы закрыть диалоговое окно, нажмите кнопку **ОК** . Кнопки добавляются в <xref:System.Windows.Forms.ToolStrip>.

8. Щелкните форму правой кнопкой мыши и выберите команду **Просмотреть код**.

9. В редакторе кода найдите строку кода, которая загружает данные в адаптер таблицы. Этот код был создан при настройке привязки данных на шаге 2. Код должен иметь следующий вид: `TableAdapterName.Fill(DataSetName.TableName)`. Скорее всего, это будет событие <xref:System.Windows.Forms.Form.Load> формы.

10. Создайте обработчик событий для <xref:System.Windows.Forms.ToolStripItem.Click>ного события **нагрузки** <xref:System.Windows.Forms.ToolStripButton>, созданного ранее, и переместите этот код загрузки данных в него.

     Теперь ваш код должен выглядеть следующим образом:

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

11. Создайте обработчик события <xref:System.Windows.Forms.ToolStripItem.Click> для события<xref:System.Windows.Forms.ToolStripButton>, созданного **ранее, и** напишите код для обновления данных в таблице, к которой привязан элемент управления.

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
    > В некоторых случаях в <xref:System.Windows.Forms.BindingNavigator> компонент уже есть кнопка **сохранить** , но в конструктор Windows Forms не был создан код. В этом случае можно поместить приведенный выше код в обработчик событий <xref:System.Windows.Forms.ToolStripItem.Click> для этой кнопки, а не создавать совершенно новую кнопку на <xref:System.Windows.Forms.ToolStrip>. Однако кнопка по умолчанию отключена, поэтому необходимо задать для свойства <xref:System.Windows.Forms.ToolBarButton.Enabled%2A> кнопки значение `true`, чтобы функция кнопки была правильной.

12. Создайте обработчик событий <xref:System.Windows.Forms.ToolStripItem.Click> события **Cancel** <xref:System.Windows.Forms.ToolStripButton>, созданного ранее, и напишите код, чтобы отменить все изменения в отображаемой записи данных.

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
    > Метод <xref:System.Windows.Forms.BindingSource.CancelEdit%2A> ограничивается строкой данных. Сохраните все изменения, внесенные при просмотре отдельной записи, прежде чем переходить к следующей записи.

## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Forms.BindingNavigator>
- <xref:System.Windows.Forms.BindingSource>
- <xref:System.Windows.Forms.ToolStrip>
- [Элемент управления BindingNavigator](bindingnavigator-control-windows-forms.md)
- [Общие сведения о компоненте BindingSource](bindingsource-component-overview.md)
