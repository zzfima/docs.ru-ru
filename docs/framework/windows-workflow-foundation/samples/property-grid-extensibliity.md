---
title: Расширяемость сетки свойств
ms.date: 03/30/2017
ms.assetid: 3530c3a3-756d-4712-9f10-fb2897414d3a
ms.openlocfilehash: b7c3e3dbc3ccd95fc12dffd40927b3e2bbbc8226
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43660260"
---
# <a name="property-grid-extensibliity"></a><span data-ttu-id="78102-102">Расширяемость сетки свойств</span><span class="sxs-lookup"><span data-stu-id="78102-102">Property Grid Extensibliity</span></span>
<span data-ttu-id="78102-103">Разработчик может настроить сетку свойств, которая будет отображаться при выборе в редакторе определенного действия.</span><span class="sxs-lookup"><span data-stu-id="78102-103">A developer can customize the property grid that is displayed when a given activity is selected within the designer.</span></span> <span data-ttu-id="78102-104">Таким образом можно реализовать расширенные возможности редактирования.</span><span class="sxs-lookup"><span data-stu-id="78102-104">This can be done to create a rich editing experience.</span></span> <span data-ttu-id="78102-105">Они показываются в данном образце.</span><span class="sxs-lookup"><span data-stu-id="78102-105">This sample shows how this can be done.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="78102-106">Демонстрации</span><span class="sxs-lookup"><span data-stu-id="78102-106">Demonstrates</span></span>  
 <span data-ttu-id="78102-107">Расширяемость сетки свойств конструктора рабочих процессов.</span><span class="sxs-lookup"><span data-stu-id="78102-107">Workflow designer property grid extensibility.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="78102-108">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="78102-108">The samples may already be installed on your machine.</span></span> <span data-ttu-id="78102-109">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="78102-109">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="78102-110">Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] примеры.</span><span class="sxs-lookup"><span data-stu-id="78102-110">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="78102-111">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="78102-111">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Designer\PropertyGridExtensibility`  
  
## <a name="discussion"></a><span data-ttu-id="78102-112">Обсуждение</span><span class="sxs-lookup"><span data-stu-id="78102-112">Discussion</span></span>  
 <span data-ttu-id="78102-113">Чтобы расширить сетку свойств, разработчик может настроить встроенное представление редактора сетки свойств или реализовать диалоговое окно, которое будет отображать усовершенствованную область расширенного редактирования.</span><span class="sxs-lookup"><span data-stu-id="78102-113">To extend the property grid, a developer has options to customize the inline appearance of a property grid editor or provide a dialog that appears for a more advanced editing surface.</span></span> <span data-ttu-id="78102-114">В этом образце демонстрируется работа двух разных редакторов: встроенного редактора и диалогового редактора.</span><span class="sxs-lookup"><span data-stu-id="78102-114">There are two different editors demonstrated in this sample; an inline editor and a dialog editor.</span></span>  
  
## <a name="inline-editor"></a><span data-ttu-id="78102-115">Встроенный редактор</span><span class="sxs-lookup"><span data-stu-id="78102-115">Inline Editor</span></span>  
 <span data-ttu-id="78102-116">В образце встроенного редактора показаны следующие действия.</span><span class="sxs-lookup"><span data-stu-id="78102-116">The inline editor sample demonstrates the following:</span></span>  
  
-   <span data-ttu-id="78102-117">Создает тип, производный от <xref:System.Activities.Presentation.PropertyEditing.PropertyValueEditor>.</span><span class="sxs-lookup"><span data-stu-id="78102-117">Creates a type that derives from <xref:System.Activities.Presentation.PropertyEditing.PropertyValueEditor>.</span></span>  
  
-   <span data-ttu-id="78102-118">В конструкторе <xref:System.Activities.Presentation.PropertyEditing.PropertyValueEditor.InlineEditorTemplate%2A> значение задается с помощью шаблона данных Windows Presentation Foundation (WPF).</span><span class="sxs-lookup"><span data-stu-id="78102-118">In the constructor, the <xref:System.Activities.Presentation.PropertyEditing.PropertyValueEditor.InlineEditorTemplate%2A> value is set with a Windows Presentation Foundation (WPF) data template.</span></span> <span data-ttu-id="78102-119">Значение может быть привязано к XAML-шаблону, однако в этом образце для инициализации привязки данных используется код.</span><span class="sxs-lookup"><span data-stu-id="78102-119">This can be bound to a XAML template, but in this sample, code is used to initialize data binding.</span></span>  
  
-   <span data-ttu-id="78102-120">Шаблон данных имеет контекст данных значения <xref:System.Activities.Presentation.PropertyEditing.PropertyValue> для элемента, отображаемого в сетке свойств.</span><span class="sxs-lookup"><span data-stu-id="78102-120">The data template has a data context of the <xref:System.Activities.Presentation.PropertyEditing.PropertyValue> of the item rendered in the property grid.</span></span> <span data-ttu-id="78102-121">Обратите внимание, что в приведенном ниже коде (файл CustomInlineEditor.cs) этот контекст привязывается к свойству `Value`.</span><span class="sxs-lookup"><span data-stu-id="78102-121">Note in the following code (from CustomInlineEditor.cs) that this context then binds to the `Value` property.</span></span>  
  
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
  
-   <span data-ttu-id="78102-122">Поскольку действие и конструктор находятся в одной сборке, регистрация атрибутов конструктора действий выполняется в статическом конструкторе самого действия, как показано в следующем примере из файла SimpleCodeActivity.cs.</span><span class="sxs-lookup"><span data-stu-id="78102-122">Because the activity and the designer are in the same assembly, registration of the activity designer attributes are accomplished in the static constructor of the activity itself, as shown in the following example from SimpleCodeActivity.cs.</span></span>  
  
    ```  
    static SimpleCodeActivity()  
    {  
        AttributeTableBuilder builder = new AttributeTableBuilder();  
        builder.AddCustomAttributes(typeof(SimpleCodeActivity), "RepeatCount", new EditorAttribute(typeof(CustomInlineEditor), typeof(PropertyValueEditor)));  
        builder.AddCustomAttributes(typeof(SimpleCodeActivity), "FileName", new EditorAttribute(typeof(FilePickerEditor), typeof(DialogPropertyValueEditor)));  
        MetadataStore.AddAttributeTable(builder.CreateTable());  
    }  
    ```  
  
## <a name="dialog-editor"></a><span data-ttu-id="78102-123">Редактор диалоговых окон</span><span class="sxs-lookup"><span data-stu-id="78102-123">Dialog Editor</span></span>  
 <span data-ttu-id="78102-124">В образце диалогового редактора показаны следующие действия.</span><span class="sxs-lookup"><span data-stu-id="78102-124">The dialog editor sample demonstrates the following:</span></span>  
  
1.  <span data-ttu-id="78102-125">Создает тип, производный от <xref:System.Activities.Presentation.PropertyEditing.DialogPropertyValueEditor>.</span><span class="sxs-lookup"><span data-stu-id="78102-125">Creates a type that derives from <xref:System.Activities.Presentation.PropertyEditing.DialogPropertyValueEditor>.</span></span>  
  
2.  <span data-ttu-id="78102-126">В конструкторе значение <xref:System.Activities.Presentation.PropertyEditing.PropertyValueEditor.InlineEditorTemplate%2A> задается при помощи шаблона данных [!INCLUDE[avalon2](../../../../includes/avalon2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="78102-126">Sets the <xref:System.Activities.Presentation.PropertyEditing.PropertyValueEditor.InlineEditorTemplate%2A> value in the constructor with a [!INCLUDE[avalon2](../../../../includes/avalon2-md.md)] data template.</span></span> <span data-ttu-id="78102-127">Значение может быть создано в XAML, однако в этом образце оно создается с помощью кода.</span><span class="sxs-lookup"><span data-stu-id="78102-127">This can be created in XAML, but in this sample, this is created in code.</span></span>  
  
3.  <span data-ttu-id="78102-128">Шаблон данных имеет контекст данных значения <xref:System.Activities.Presentation.PropertyEditing.PropertyValue> для элемента, отображаемого в сетке свойств.</span><span class="sxs-lookup"><span data-stu-id="78102-128">The data template has a data context of the <xref:System.Activities.Presentation.PropertyEditing.PropertyValue> of the item rendered in the property grid.</span></span> <span data-ttu-id="78102-129">В следующем коде значение привязывается к свойству `Value`.</span><span class="sxs-lookup"><span data-stu-id="78102-129">In the following code, this then binds to the `Value` property.</span></span> <span data-ttu-id="78102-130">Важно также добавить кнопку <xref:System.Activities.Presentation.PropertyEditing.EditModeSwitchButton> для обеспечения возможности вызова диалогового окна в файле FilePickerEditor.cs.</span><span class="sxs-lookup"><span data-stu-id="78102-130">It is critical to also include an <xref:System.Activities.Presentation.PropertyEditing.EditModeSwitchButton> to provide the button that raises the dialog in FilePickerEditor.cs.</span></span>  
  
    ```  
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
  
4.  <span data-ttu-id="78102-131">Переопределяет <!--zz <xref:Microsoft.Windows.Design.PropertyEditing.ShowDialog%2A>--> `Microsoft.Windows.Design.PropertyEditing.ShowDialog` метода в типе конструктора для управления отображением диалогового окна.</span><span class="sxs-lookup"><span data-stu-id="78102-131">Overrides the <!--zz <xref:Microsoft.Windows.Design.PropertyEditing.ShowDialog%2A>--> `Microsoft.Windows.Design.PropertyEditing.ShowDialog` method in the designer type to handle the display of the dialog.</span></span> <span data-ttu-id="78102-132">В этом образце показано базовое диалоговое окно <xref:System.Windows.Forms.FileDialog>.</span><span class="sxs-lookup"><span data-stu-id="78102-132">In this sample, a basic <xref:System.Windows.Forms.FileDialog> is shown.</span></span>  
  
    ```  
    public override void ShowDialog(PropertyValue propertyValue, IInputElement commandSource)  
    {  
        Microsoft.Win32.OpenFileDialog ofd = new Microsoft.Win32.OpenFileDialog();  
        if (ofd.ShowDialog() == true)  
        {  
            propertyValue.Value = ofd.FileName;  
        }  
    }  
    ```  
  
5.  <span data-ttu-id="78102-133">Поскольку действие и конструктор находятся в одной сборке, регистрация атрибутов конструктора действий выполняется в статическом конструкторе самого действия, как показано в следующем примере из файла SimpleCodeActivity.cs.</span><span class="sxs-lookup"><span data-stu-id="78102-133">Because the activity and the designer are in the same assembly, registration of the activity designer attributes are accomplished in the static constructor of the activity itself, as shown in the following example from SimpleCodeActivity.cs.</span></span>  
  
    ```  
    static SimpleCodeActivity()  
    {  
        AttributeTableBuilder builder = new AttributeTableBuilder();  
        builder.AddCustomAttributes(typeof(SimpleCodeActivity), "RepeatCount", new EditorAttribute(typeof(CustomInlineEditor), typeof(PropertyValueEditor)));  
        builder.AddCustomAttributes(typeof(SimpleCodeActivity), "FileName", new EditorAttribute(typeof(FilePickerEditor), typeof(DialogPropertyValueEditor)));  
        MetadataStore.AddAttributeTable(builder.CreateTable());  
    }  
    ```  
  
## <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="78102-134">Настройка, сборка и выполнение образца</span><span class="sxs-lookup"><span data-stu-id="78102-134">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="78102-135">Постройте решение и откройте файл Workflow1.xaml.</span><span class="sxs-lookup"><span data-stu-id="78102-135">Build the solution, and then open Workflow1.xaml.</span></span>  
  
2.  <span data-ttu-id="78102-136">Перетащите **SimpleCodeActivity** из области элементов на холст конструктора.</span><span class="sxs-lookup"><span data-stu-id="78102-136">Drag a **SimpleCodeActivity** from the toolbox onto the designer canvas.</span></span>  
  
3.  <span data-ttu-id="78102-137">Нажмите кнопку **SimpleCodeActivity** и откройте сетку свойств, где имеется элемент управления "ползунок" и элемент выбора файла.</span><span class="sxs-lookup"><span data-stu-id="78102-137">Click the **SimpleCodeActivity** and then open the property grid where there is a slider control and a file picking control.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="78102-138">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="78102-138">The samples may already be installed on your machine.</span></span> <span data-ttu-id="78102-139">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="78102-139">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="78102-140">Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] примеры.</span><span class="sxs-lookup"><span data-stu-id="78102-140">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="78102-141">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="78102-141">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Designer\PropertyGridExtensibility`
