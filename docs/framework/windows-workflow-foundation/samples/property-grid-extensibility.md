---
title: Расширяемость сетки свойств - пример WF
ms.date: 03/30/2017
ms.assetid: 3530c3a3-756d-4712-9f10-fb2897414d3a
ms.openlocfilehash: f1cb64cb10e8d88359e8f94b57602ab127314cff
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57509553"
---
# <a name="property-grid-extensibility"></a>Расширяемость сетки свойств

Разработчик может настроить сетку свойств, которая будет отображаться при выборе в редакторе определенного действия. Таким образом можно реализовать расширенные возможности редактирования. Они показываются в данном образце.

## <a name="demonstrates"></a>Демонстрации

Расширяемость сетки свойств конструктора рабочих процессов.

> [!IMPORTANT]
> Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] примеры. Этот образец расположен в следующем каталоге.
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Designer\PropertyGridExtensibility`

## <a name="discussion"></a>Обсуждение

Чтобы расширить сетку свойств, разработчик может настроить встроенное представление редактора сетки свойств или реализовать диалоговое окно, которое будет отображать усовершенствованную область расширенного редактирования. В этом образце демонстрируется работа двух разных редакторов: встроенного редактора и диалогового редактора.

## <a name="inline-editor"></a>Встроенный редактор

В образце встроенного редактора показаны следующие действия.

- Создает тип, производный от <xref:System.Activities.Presentation.PropertyEditing.PropertyValueEditor>.

- В конструкторе <xref:System.Activities.Presentation.PropertyEditing.PropertyValueEditor.InlineEditorTemplate%2A> значение задается с помощью шаблона данных Windows Presentation Foundation (WPF). Значение может быть привязано к XAML-шаблону, однако в этом образце для инициализации привязки данных используется код.

- Шаблон данных имеет контекст данных значения <xref:System.Activities.Presentation.PropertyEditing.PropertyValue> для элемента, отображаемого в сетке свойств. Обратите внимание, что в приведенном ниже коде (файл CustomInlineEditor.cs) этот контекст привязывается к свойству `Value`.

    ```csharp
    FrameworkElementFactory stack = new FrameworkElementFactory(typeof(StackPanel));
    FrameworkElementFactory slider = new FrameworkElementFactory(typeof(Slider));
    Binding sliderBinding = new Binding("Value");
    sliderBinding.Mode = BindingMode.TwoWay;
    slider.SetValue(Slider.MinimumProperty, 0.0);
    slider.SetValue(Slider.MaximumProperty, 100.0);
    slider.SetValue(Slider.ValueProperty, sliderBinding);
    stack.AppendChild(slider);
    ```

- Поскольку действие и конструктор находятся в одной сборке, регистрация атрибутов конструктора действий выполняется в статическом конструкторе самого действия, как показано в следующем примере из файла SimpleCodeActivity.cs.

    ```csharp
    static SimpleCodeActivity()
    {
        AttributeTableBuilder builder = new AttributeTableBuilder();
        builder.AddCustomAttributes(typeof(SimpleCodeActivity), "RepeatCount", new EditorAttribute(typeof(CustomInlineEditor), typeof(PropertyValueEditor)));
        builder.AddCustomAttributes(typeof(SimpleCodeActivity), "FileName", new EditorAttribute(typeof(FilePickerEditor), typeof(DialogPropertyValueEditor)));
        MetadataStore.AddAttributeTable(builder.CreateTable());
    }
    ```

## <a name="dialog-editor"></a>редактор диалоговых окон

В образце диалогового редактора показаны следующие действия.

1. Создает тип, производный от <xref:System.Activities.Presentation.PropertyEditing.DialogPropertyValueEditor>.

2. В конструкторе значение <xref:System.Activities.Presentation.PropertyEditing.PropertyValueEditor.InlineEditorTemplate%2A> задается при помощи шаблона данных [!INCLUDE[avalon2](../../../../includes/avalon2-md.md)]. Значение может быть создано в XAML, однако в этом образце оно создается с помощью кода.

3. Шаблон данных имеет контекст данных значения <xref:System.Activities.Presentation.PropertyEditing.PropertyValue> для элемента, отображаемого в сетке свойств. В следующем коде значение привязывается к свойству `Value`. Важно также добавить кнопку <xref:System.Activities.Presentation.PropertyEditing.EditModeSwitchButton> для обеспечения возможности вызова диалогового окна в файле FilePickerEditor.cs.

    ```csharp
    this.InlineEditorTemplate = new DataTemplate();

    FrameworkElementFactory stack = new FrameworkElementFactory(typeof(StackPanel));
    stack.SetValue(StackPanel.OrientationProperty, Orientation.Horizontal);
    FrameworkElementFactory label = new FrameworkElementFactory(typeof(Label));
    Binding labelBinding = new Binding("Value");
    label.SetValue(Label.ContentProperty, labelBinding);
    label.SetValue(Label.MaxWidthProperty, 90.0);

    stack.AppendChild(label);

    FrameworkElementFactory editModeSwitch = new FrameworkElementFactory(typeof(EditModeSwitchButton));

    editModeSwitch.SetValue(EditModeSwitchButton.TargetEditModeProperty, PropertyContainerEditMode.Dialog);

    stack.AppendChild(editModeSwitch);

    this.InlineEditorTemplate.VisualTree = stack;
    ```

4. Переопределяет метод <xref:System.Activities.Presentation.PropertyEditing.DialogPropertyValueEditor.ShowDialog%2A> в типе конструктора для управления отображением диалогового окна. В этом образце показано базовое диалоговое окно <xref:System.Windows.Forms.FileDialog>.

    ```csharp
    public override void ShowDialog(PropertyValue propertyValue, IInputElement commandSource)
    {
        Microsoft.Win32.OpenFileDialog ofd = new Microsoft.Win32.OpenFileDialog();
        if (ofd.ShowDialog() == true)
        {
            propertyValue.Value = ofd.FileName;
        }
    }
    ```

5. Поскольку действие и конструктор находятся в одной сборке, регистрация атрибутов конструктора действий выполняется в статическом конструкторе самого действия, как показано в следующем примере из файла SimpleCodeActivity.cs.

    ```csharp
    static SimpleCodeActivity()
    {
        AttributeTableBuilder builder = new AttributeTableBuilder();
        builder.AddCustomAttributes(typeof(SimpleCodeActivity), "RepeatCount", new EditorAttribute(typeof(CustomInlineEditor), typeof(PropertyValueEditor)));
        builder.AddCustomAttributes(typeof(SimpleCodeActivity), "FileName", new EditorAttribute(typeof(FilePickerEditor), typeof(DialogPropertyValueEditor)));
        MetadataStore.AddAttributeTable(builder.CreateTable());
    }
    ```

## <a name="to-set-up-build-and-run-the-sample"></a>Настройка, сборка и выполнение образца

1. Постройте решение и откройте файл Workflow1.xaml.

2. Перетащите **SimpleCodeActivity** из области элементов на холст конструктора.

3. Нажмите кнопку **SimpleCodeActivity** и откройте сетку свойств, где имеется элемент управления "ползунок" и элемент выбора файла.

> [!IMPORTANT]
> Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] примеры. Этот образец расположен в следующем каталоге.
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Designer\PropertyGridExtensibility`