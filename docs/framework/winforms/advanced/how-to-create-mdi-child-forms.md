---
title: Практическое руководство. Создание дочерних MDI-форм
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- MDI [Windows Forms], creating forms
- child forms
ms.assetid: 164b69bb-2eca-4339-ada3-0679eb2c6dda
ms.openlocfilehash: b49d43e0e1123921cb3800f0d60193d0ea7b3924
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/25/2019
ms.locfileid: "75338597"
---
# <a name="how-to-create-mdi-child-forms"></a>Как создавать дочерние формы MDI

Дочерние MDI-формы являются ключевым элементом [приложений с интерфейсом MDI](multiple-document-interface-mdi-applications.md), так как эти формы являются центром взаимодействия с пользователем.

В следующей процедуре Visual Studio используется для создания дочерней MDI-формы, отображающей элемент управления <xref:System.Windows.Forms.RichTextBox>, аналогично большинству приложений для обработки текстов. Подставив элемент управления <xref:System.Windows.Forms> с другими элементами управления, такими как элемент управления <xref:System.Windows.Forms.DataGridView>, или сочетанием элементов управления, можно создавать дочерние MDI-окна (и по расширениям, приложения MDI) с различными возможностями.

## <a name="create-mdi-child-forms"></a>Создание дочерних форм MDI

1. Создание нового проекта Windows Forms приложения в Visual Studio. В окне **Свойства** формы задайте для свойства <xref:System.Windows.Forms.Form.IsMdiContainer%2A> значение `true`, а для свойства `WindowsState` значение `Maximized`.

   При этом форма назначается в качестве MDI-контейнера для дочерних окон.

2. Из `Toolbox` перетащите элемент управления <xref:System.Windows.Forms.MenuStrip> в форму. Присвойте свойству `Text` значение **File**.

3. Нажмите кнопку с многоточием (...) рядом со свойством **Items** и нажмите кнопку **Добавить** , чтобы добавить два дочерних пункта меню. Присвойте свойству `Text` этих элементов значение **New** и **Window**.

4. В **обозревателе решений** щелкните проект правой кнопкой мыши и выберите пункты **Добавить** > **Новый элемент**.

5. В диалоговом окне **Добавление нового элемента** выберите **Windows Form** (в Visual Basic или в Visual C#) или **Windows Forms приложение (.NET)** (в Visual C++) в области **шаблоны** . В поле **имя** введите имя формы **Form2**. Нажмите кнопку **Открыть** , чтобы добавить форму в проект.

    > [!NOTE]
    > Дочерняя форма MDI, созданная на этом этапе, является стандартной формой Windows Forms. Таким образом, у нее есть свойство <xref:System.Windows.Forms.Form.Opacity%2A>, которое позволяет управлять прозрачностью формы. Однако свойство <xref:System.Windows.Forms.Form.Opacity%2A> предназначено для окон верхнего уровня. Его не следует использовать в дочерних формах MDI, иначе могут возникнуть проблемы с рисованием.

     Эта форма будет шаблоном для дочерних форм MDI.

     Откроется **конструктор Windows Forms** , отображающий **Form2**.

6. Перетащите элемент управления **RichTextBox** из **панели элементов**в форму.

7. В окне **Свойства** задайте для свойства `Anchor` значение **сверху, слева** , а для свойства `Dock` — значение **Fill**.

   В результате элемент управления <xref:System.Windows.Forms.RichTextBox> будет целиком заполнять область дочерней формы MDI, даже если ее размеры изменятся.

8. Дважды щелкните **Новый** элемент меню, чтобы создать для него обработчик событий <xref:System.Windows.Forms.Control.Click>.

9. Вставьте код, аналогичный приведенному ниже, чтобы создать новую дочернюю форму MDI, когда пользователь щелкнет **Новый** элемент меню.

   > [!NOTE]
   > В примере ниже обработчик событий обрабатывает событие <xref:System.Windows.Forms.Control.Click> для `MenuItem2`. Имейте в виду, что в зависимости от особенностей архитектуры приложения **Новый** элемент меню может не `MenuItem2`.

    ```vb
    Protected Sub MDIChildNew_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles MenuItem2.Click
       Dim NewMDIChild As New Form2()
       'Set the Parent Form of the Child window.
       NewMDIChild.MdiParent = Me
       'Display the new form.
       NewMDIChild.Show()
    End Sub
    ```

    ```csharp
    protected void MDIChildNew_Click(object sender, System.EventArgs e){
       Form2 newMDIChild = new Form2();
       // Set the Parent Form of the Child window.
       newMDIChild.MdiParent = this;
       // Display the new form.
       newMDIChild.Show();
    }
    ```

    ```cpp
    private:
       void menuItem2_Click(System::Object ^ sender,
          System::EventArgs ^ e)
       {
          Form2^ newMDIChild = gcnew Form2();
          // Set the Parent Form of the Child window.
          newMDIChild->MdiParent = this;
          // Display the new form.
          newMDIChild->Show();
       }
    ```

   В C++добавьте следующую директиву `#include` в верхней части Form1. h:

   ```cpp
   #include "Form2.h"
   ```

10. В раскрывающемся списке в верхней части окна " **Свойства** " выберите полосу меню, соответствующую полосе меню " **файл** ", и задайте для свойства <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> значение в окне <xref:System.Windows.Forms.ToolStripMenuItem>.

    Это позволяет меню " **окно** " поддерживать список открытых дочерних окон MDI с галочкой рядом с активным дочерним окном.

11. Нажмите клавишу **F5** для запуска приложения. Выбрав пункт **создать** в меню **файл** , можно создать дочерние MDI-формы, которые будут храниться в пункте меню **окно** .

    > [!NOTE]
    > Когда в дочерней форме MDI есть компонент <xref:System.Windows.Forms.MainMenu> (обычно обладающий структурой пунктов меню) и он открыт внутри родительской формы MDI, также имеющей компонент <xref:System.Windows.Forms.MainMenu> (обычно обладающий структурой пунктов меню), пункты меню будут объединены автоматически, если задано свойство <xref:System.Windows.Forms.MenuItem.MergeType%2A> (и, возможно, свойство <xref:System.Windows.Forms.MenuItem.MergeOrder%2A>). Установите для свойства <xref:System.Windows.Forms.MenuItem.MergeType%2A> обоих компонентов <xref:System.Windows.Forms.MainMenu> и всех пунктов меню дочерней формы значение <xref:System.Windows.Forms.MenuMerge.MergeItems>. Кроме того, установите свойство <xref:System.Windows.Forms.MenuItem.MergeOrder%2A> таким образом, чтобы пункты обоих меню приводились в нужном порядке. Необходимо помнить, что при закрытии родительской формы MDI каждая из дочерних форм MDI создает событие <xref:System.Windows.Forms.Form.Closing> до создания события <xref:System.Windows.Forms.Form.Closing> для родительской формы MDI. Отмена события <xref:System.Windows.Forms.Form.Closing> дочерней формы MDI не отменяет событие <xref:System.Windows.Forms.Form.Closing> родительской формы MDI. Однако для аргумента <xref:System.ComponentModel.CancelEventArgs> для события <xref:System.Windows.Forms.Form.Closing> родительской формы MDI будет установлено значение `true`. Чтобы принудительно закрыть родительскую и все дочерние формы MDI, задайте для аргумента <xref:System.ComponentModel.CancelEventArgs> значение `false`.

## <a name="see-also"></a>См. также:

- [Приложения с интерфейсом MDI](multiple-document-interface-mdi-applications.md)
- [Практическое руководство. Создание родительских MDI-форм](how-to-create-mdi-parent-forms.md)
- [Практическое руководство. Определение активной дочерней MDI-формы](how-to-determine-the-active-mdi-child.md)
- [Практическое руководство. Отправка данных в активную дочернюю MDI-форму](how-to-send-data-to-the-active-mdi-child.md)
- [Практическое руководство. Упорядочение дочерних форм интерфейса MDI](how-to-arrange-mdi-child-forms.md)
