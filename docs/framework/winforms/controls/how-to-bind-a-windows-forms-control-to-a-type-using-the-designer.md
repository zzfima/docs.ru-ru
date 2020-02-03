---
title: Привязка элемента управления к типу с помощью конструктора
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], binding to a type
- BindingSource component [Windows Forms], binding to a type
- types [Windows Forms], binding controls to
ms.assetid: 5ab984b5-c2d0-4638-a572-1c84013e8746
ms.openlocfilehash: 2257489e123ceeea819ad3538952db51b726c7e5
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742028"
---
# <a name="how-to-bind-a-windows-forms-control-to-a-type-using-the-designer"></a>Практическое руководство. Привязка элемента управления Windows Forms к типу с помощью конструктора

При создании элементов управления, взаимодействующих с данными, иногда бывает нужно привязать элемент управления к типу, а не к объекту. Обычно подобная ситуация возникает на этапе разработки, когда данные недоступны, однако нужно, чтобы элементы управления с привязкой к данным отображали данные из открытого интерфейса типа. В следующих процедурах показано, как создать новый <xref:System.Windows.Forms.BindingSource>, привязанный к типу, а затем как привязать одно из свойств типа к свойству <xref:System.Windows.Forms.TextBox.Text%2A> <xref:System.Windows.Forms.TextBox>.

### <a name="to-bind-the-bindingsource-to-a-type"></a>Привязка BindingSource к типу

1. Создайте проект Windows Forms (**файл** > **Новый** > **проект** > **Visual C#**  или **Visual Basic** **классический рабочий стол** > **приложение > ** ).

2. В режиме **конструктора** перетащите <xref:System.Windows.Forms.BindingSource> компонент на форму.

3. В окне **Свойства** щелкните стрелку свойства <xref:System.Windows.Forms.BindingSource.DataSource%2A>.

4. В **редакторе типов пользовательского интерфейса DataSource** нажмите кнопку **Добавить источник данных проекта**.

5. На странице **Выбор типа источника данных** выберите тип **Объект** и нажмите кнопку **Далее**.

6. Выберите тип для привязки.

    - Если тип для привязки находится в текущем проекте либо сборка, содержащая этот тип, уже добавлена как ссылка, разверните узлы, а затем найдите и выберите желаемый тип.

      \-или-

    - Если тип, к которому требуется выполнить привязку, находится в другой сборке, а не в списке ссылок, нажмите кнопку **Добавить ссылку**, а затем перейдите на вкладку **проекты** . Выберите проект, содержащий нужный бизнес-объект, и нажмите кнопку **ОК**. Этот проект будет отображаться в списке сборок, так что вы сможете развернуть узлы, а затем найти и выбрать желаемый тип.

      > [!NOTE]
      > Если тип, который нужно привязать, находится в инфраструктуре или сборке Майкрософт, снимите флажок **Скрыть сборки, начинающиеся с Microsoft или System**.

7. Щелкните **Далее**и затем нажмите кнопку **Готово**.

### <a name="to-bind-the-control-to-the-bindingsource"></a>Привязка элемента управления к BindingSource

1. Добавьте на форму элемент <xref:System.Windows.Forms.TextBox>.

2. В окне **Свойства** разверните узел **(DataBindings)** .

3. Щелкните стрелку рядом со свойством <xref:System.Windows.Forms.TextBox.Text%2A>.

4. В окне **Редактор типов пользовательского интерфейса источника данных**разверните узел <xref:System.Windows.Forms.BindingSource>, добавленный ранее, и выберите свойство связанного типа, которое необходимо привязать к свойству <xref:System.Windows.Forms.TextBox.Text%2A> <xref:System.Windows.Forms.TextBox>.

## <a name="see-also"></a>См. также раздел

- [Компонент BindingSource](bindingsource-component.md)
- [Практическое руководство. Связывание элемента управления с типом в Windows Forms](how-to-bind-a-windows-forms-control-to-a-type.md)
- [Привязка элементов управления к данным в Visual Studio](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio)
