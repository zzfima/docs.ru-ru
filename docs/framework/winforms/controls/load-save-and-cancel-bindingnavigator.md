---
title: Практическое руководство. Добавление кнопок загрузки, сохранения и отмены в элемент управления BindingNavigator в формах Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [Windows Forms], manipulating
- BindingNavigator control [Windows Forms], adding buttons
ms.assetid: faa33042-186e-4bb2-8798-17ceb987ec62
ms.openlocfilehash: 2d4867c0bc4feb7b43e15614fc56a3c709cef9e7
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/14/2019
ms.locfileid: "70991741"
---
# <a name="how-to-add-load-save-and-cancel-buttons-to-the-windows-forms-bindingnavigator-control"></a>Практическое руководство. Добавление кнопок загрузки, сохранения и отмены в элемент управления BindingNavigator в формах Windows Forms

Элемент управления — это специализированный <xref:System.Windows.Forms.ToolStrip> элемент управления, предназначенный для навигации по элементам управления формы, привязанным к данным, и манипулирования ими. <xref:System.Windows.Forms.BindingNavigator>

Поскольку это <xref:System.Windows.Forms.BindingNavigator> элемент управления, компонент можно легко изменить, включив в него дополнительные или альтернативные команды для пользователя. <xref:System.Windows.Forms.ToolStrip>

В следующей процедуре <xref:System.Windows.Forms.TextBox> элемент управления привязан к данным, <xref:System.Windows.Forms.ToolStrip> а элемент управления, добавляемый в форму, изменяется для включения кнопок загрузки, сохранения и отмены.

## <a name="add-load-save-and-cancel-buttons-to-the-bindingnavigator-component"></a>Добавление кнопок загрузки, сохранения и отмены в компонент BindingNavigator

1. В Visual Studio добавьте <xref:System.Windows.Forms.TextBox> в форму элемент управления.

2. Привяжите его к <xref:System.Windows.Forms.BindingSource>, который привязан к источнику данных. В <xref:System.Windows.Forms.BindingSource> этом примере Привязка привязана к базе данных.

3. После создания набора данных и адаптера таблицы перетащите <xref:System.Windows.Forms.BindingNavigator> элемент управления в форму.

4. Присвойте <xref:System.Windows.Forms.BindingNavigator.BindingSource%2A> <xref:System.Windows.Forms.BindingSource> свойству <xref:System.Windows.Forms.BindingNavigator> элемента управления значение в форме, привязанной к элементам управления.

5. Выберите элемент управления <xref:System.Windows.Forms.BindingNavigator>.

6. Щелкните глиф смарт-тега (![глиф смарт-тега](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")), чтобы увидеть диалоговое окно **Задачи BindingNavigator** , и выберите **изменить элементы**.

     Откроется **Редактор коллекции элементов** .

7. В **редакторе коллекции элементов**выполните следующие действия.

    1. Добавьте и три <xref:System.Windows.Forms.ToolStripButton> элемента, <xref:System.Windows.Forms.ToolStripItem> выбрав соответствующий тип и нажав кнопку **Добавить.** <xref:System.Windows.Forms.ToolStripSeparator>

    2. Задайте длясвойств кнопок значение лоадбуттон, савебуттон и CancelButton соответственно. <xref:System.Windows.Forms.ToolStripItem.Name%2A>

    3. Задайте длясвойства кнопки значение Загрузка, сохранение и Отмена. <xref:System.Windows.Forms.ToolStripItem.Text%2A>

    4. Присвойте свойству каждой кнопки значение Text. <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> Кроме того, можно задать для этого свойства значение **Image** или **имажеандтекст**и задать <xref:System.Windows.Forms.ToolStripItem.Image%2A> отображение изображения в свойстве.

    5. Нажмите кнопку **ОК**, чтобы закрыть диалоговое окно. Кнопки добавляются в <xref:System.Windows.Forms.ToolStrip>.

8. Щелкните форму правой кнопкой мыши и выберите команду **Просмотреть код**.

9. В редакторе кода найдите строку кода, которая загружает данные в адаптер таблицы. Этот код был создан при настройке привязки данных на шаге 2. Код должен выглядеть следующим образом: `TableAdapterName.Fill(DataSetName.TableName)`. Скорее всего, оно будет содержаться в <xref:System.Windows.Forms.Form.Load> событии формы.

10. Создайте обработчик событий для <xref:System.Windows.Forms.ToolStripItem.Click> события ранее созданной **нагрузки** <xref:System.Windows.Forms.ToolStripButton> и переместите в нее этот код загрузки данных.

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

11. Создайте обработчик событий для <xref:System.Windows.Forms.ToolStripItem.Click> события ранее созданного **сохранения** <xref:System.Windows.Forms.ToolStripButton> и напишите код для обновления данных в таблице, к которой привязан элемент управления.

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
    > В некоторых случаях <xref:System.Windows.Forms.BindingNavigator> в компоненте уже есть кнопка **сохранить** , но конструктор Windows Forms не был создан код. В этом случае можно поместить приведенный выше код в <xref:System.Windows.Forms.ToolStripItem.Click> обработчик событий для этой кнопки, а не создавать совершенно новую кнопку <xref:System.Windows.Forms.ToolStrip>на. Однако кнопка по умолчанию отключена, поэтому необходимо задать <xref:System.Windows.Forms.ToolBarButton.Enabled%2A> для свойства `true` кнопки значение, чтобы функция кнопки была правильной.

12. Создайте обработчик событий для <xref:System.Windows.Forms.ToolStripItem.Click> события **отмены** <xref:System.Windows.Forms.ToolStripButton> , созданного ранее, и напишите код, чтобы отменить все изменения, внесенные в отображаемую запись данных.

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
    > <xref:System.Windows.Forms.BindingSource.CancelEdit%2A> Метод ограничивается строкой данных. Сохраните все изменения, внесенные при просмотре отдельной записи, прежде чем переходить к следующей записи.

## <a name="see-also"></a>См. также

- <xref:System.Windows.Forms.BindingNavigator>
- <xref:System.Windows.Forms.BindingSource>
- <xref:System.Windows.Forms.ToolStrip>
- [Элемент управления BindingNavigator](bindingnavigator-control-windows-forms.md)
- [Общие сведения о компоненте BindingSource](bindingsource-component-overview.md)
