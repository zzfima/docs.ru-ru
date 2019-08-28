---
title: Практическое руководство. Привязка элемента управления Windows Forms к типу с помощью конструктора
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], binding to a type
- BindingSource component [Windows Forms], binding to a type
- types [Windows Forms], binding controls to
ms.assetid: 5ab984b5-c2d0-4638-a572-1c84013e8746
ms.openlocfilehash: 5069d7d3b5ef4c5b05159dac521d32f5be8abdd1
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/27/2019
ms.locfileid: "70046045"
---
# <a name="how-to-bind-a-windows-forms-control-to-a-type-using-the-designer"></a>Практическое руководство. Привязка элемента управления Windows Forms к типу с помощью конструктора

При создании элементов управления, взаимодействующих с данными, иногда бывает нужно привязать элемент управления к типу, а не к объекту. Обычно подобная ситуация возникает на этапе разработки, когда данные недоступны, однако нужно, чтобы элементы управления с привязкой к данным отображали данные из открытого интерфейса типа. В следующих процедурах показано, как создать новый <xref:System.Windows.Forms.BindingSource> объект, привязанный к типу, а затем как привязать одно из свойств типа <xref:System.Windows.Forms.TextBox.Text%2A> к свойству объекта <xref:System.Windows.Forms.TextBox>.

### <a name="to-bind-the-bindingsource-to-a-type"></a>Привязка BindingSource к типу

1. Создание проекта Windows Forms (**файл** > **создать** > **проект** > **визуальный C#**  элемент или **Visual Basic** > **классический рабочий** стол >   **Windows Forms приложение**).

2. В режиме **конструктора** перетащите <xref:System.Windows.Forms.BindingSource> компонент на форму.

3. В окне **Свойства** щелкните стрелку <xref:System.Windows.Forms.BindingSource.DataSource%2A> свойства.

4. В **редакторе типов пользовательского интерфейса DataSource** нажмите кнопку **Добавить источник данных проекта**.

5. На странице **Выбор типа источника данных** выберите тип **Объект** и нажмите кнопку **Далее**.

6. Выберите тип для привязки.

    - Если тип для привязки находится в текущем проекте либо сборка, содержащая этот тип, уже добавлена как ссылка, разверните узлы, а затем найдите и выберите желаемый тип.

      \-или-

    - Если тип для привязки находится в другой сборке, которой еще нет в списке ссылок, нажмите **Добавить ссылку** и выберите вкладку **Проекты**. Выберите проект, содержащий нужный вам бизнес-объект, и нажмите кнопку **ОК**. Этот проект будет отображаться в списке сборок, так что вы сможете развернуть узлы, а затем найти и выбрать желаемый тип.

      > [!NOTE]
      > Если тип, который нужно привязать, находится в инфраструктуре или сборке Майкрософт, снимите флажок **Скрыть сборки, начинающиеся с Microsoft или System**.

7. Щелкните **Далее**и затем нажмите кнопку **Готово**.

### <a name="to-bind-the-control-to-the-bindingsource"></a>Привязка элемента управления к BindingSource

1. Добавьте на форму элемент <xref:System.Windows.Forms.TextBox>.

2. В окне **Свойства** разверните узел **(DataBindings)** .

3. Щелкните стрелку рядом <xref:System.Windows.Forms.TextBox.Text%2A> со свойством.

4. В окне **Редактор типов пользовательского интерфейса источника данных**разверните узел <xref:System.Windows.Forms.BindingSource> добавленного ранее и выберите свойство связанного типа, которое необходимо привязать к <xref:System.Windows.Forms.TextBox.Text%2A> свойству <xref:System.Windows.Forms.TextBox>.

## <a name="see-also"></a>См. также

- [Компонент BindingSource](bindingsource-component.md)
- [Практическое руководство. Привязка элемента управления Windows Forms к типу](how-to-bind-a-windows-forms-control-to-a-type.md)
- [Привязка элементов управления к данным в Visual Studio](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio)
