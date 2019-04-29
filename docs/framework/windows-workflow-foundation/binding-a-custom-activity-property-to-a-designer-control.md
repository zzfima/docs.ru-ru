---
title: Привязка пользовательского свойства действия к элементу управления конструктора
ms.date: 03/30/2017
ms.assetid: 2e8061ea-10f5-407c-a31f-d0d74ce12f27
ms.openlocfilehash: 142a9eb273a98d3a2d83a1239d6d7c891d5cc305
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61945903"
---
# <a name="binding-a-custom-activity-property-to-a-designer-control"></a><span data-ttu-id="4d424-102">Привязка пользовательского свойства действия к элементу управления конструктора</span><span class="sxs-lookup"><span data-stu-id="4d424-102">Binding a custom activity property to a designer control</span></span>

<span data-ttu-id="4d424-103">Привязка элемента управления конструктора текстового поля к аргументу действия выполняется очень просто, однако при привязке сложного элемента управления конструктора (например, поля со списком) к аргументу действия могут возникнуть некоторые сложности.</span><span class="sxs-lookup"><span data-stu-id="4d424-103">Binding a text box designer control to an activity argument is fairly straightforward; binding a complex designer control (such as a combo box) to an activity argument may present challenges, however.</span></span> <span data-ttu-id="4d424-104">В этом разделе описан способ привязки аргумента действия к полю со списком в конструкторе пользовательских действий.</span><span class="sxs-lookup"><span data-stu-id="4d424-104">This topic discusses how to bind an activity argument to a combo box control on a custom activity designer.</span></span>

## <a name="creating-the-combo-box-item-converter"></a><span data-ttu-id="4d424-105">Создание преобразователя элементов поля со списком</span><span class="sxs-lookup"><span data-stu-id="4d424-105">Creating the combo box item converter</span></span>

1. <span data-ttu-id="4d424-106">Создайте новое пустое решение в среде Visual Studio 2010 под названием CustomProperty.</span><span class="sxs-lookup"><span data-stu-id="4d424-106">Create a new empty solution in Visual Studio called CustomProperty.</span></span>

2. <span data-ttu-id="4d424-107">Создайте новый класс с именем ComboBoxItemConverter.</span><span class="sxs-lookup"><span data-stu-id="4d424-107">Create a new class called ComboBoxItemConverter.</span></span> <span data-ttu-id="4d424-108">Добавьте ссылку на сборку System.Windows.Data и сделайте класс производным от <xref:System.Windows.Data.IValueConverter>.</span><span class="sxs-lookup"><span data-stu-id="4d424-108">Add a reference to System.Windows.Data, and have the class derive from <xref:System.Windows.Data.IValueConverter>.</span></span> <span data-ttu-id="4d424-109">В Visual Studio внедрите интерфейс, создав заглушки для `Convert` и `ConvertBack`.</span><span class="sxs-lookup"><span data-stu-id="4d424-109">Have Visual Studio implement the interface to generate stubs for `Convert` and `ConvertBack`.</span></span>

3. <span data-ttu-id="4d424-110">Добавьте следующий код в метод `Convert` .</span><span class="sxs-lookup"><span data-stu-id="4d424-110">Add the following code to the `Convert` method.</span></span> <span data-ttu-id="4d424-111">Этот код преобразует <xref:System.Activities.InArgument%601> действия типа <xref:System.String> в значение, которое нужно вставить в конструктор.</span><span class="sxs-lookup"><span data-stu-id="4d424-111">This code converts the activity's <xref:System.Activities.InArgument%601> of type <xref:System.String> to the value to be placed in the designer.</span></span>

    ```csharp
    ModelItem modelItem = value as ModelItem;
    if (value != null)
    {
        InArgument<string> inArgument = modelItem.GetCurrentValue() as InArgument<string>;

        if (inArgument != null)
        {
            Activity<string> expression = inArgument.Expression;
            VisualBasicValue<string> vbexpression = expression as VisualBasicValue<string>;
            Literal<string> literal = expression as Literal<string>;

            if (literal != null)
            {
                return "\"" + literal.Value + "\"";
            }
            else if (vbexpression != null)
            {
                return vbexpression.ExpressionText;
            }
        }
    }
    return null;
    ```

     <span data-ttu-id="4d424-112">Выражение в предыдущем фрагменте кода можно также создать с помощью <xref:Microsoft.CSharp.Activities.CSharpValue%601> вместо <xref:Microsoft.VisualBasic.Activities.VisualBasicValue%601>.</span><span class="sxs-lookup"><span data-stu-id="4d424-112">The expression in the above code snippet can also be created using <xref:Microsoft.CSharp.Activities.CSharpValue%601> instead of <xref:Microsoft.VisualBasic.Activities.VisualBasicValue%601>.</span></span>

    ```csharp
    ModelItem modelItem = value as ModelItem;
    if (value != null)
    {
        InArgument<string> inArgument = modelItem.GetCurrentValue() as InArgument<string>;

        if (inArgument != null)
        {
            Activity<string> expression = inArgument.Expression;
            CSharpValue<string> csexpression = expression as CSharpValue<string>;
            Literal<string> literal = expression as Literal<string>;

            if (literal != null)
            {
                return "\"" + literal.Value + "\"";
            }
            else if (csexpression != null)
            {
                return csexpression.ExpressionText;
            }
        }
    }
    return null;
    ```

4. <span data-ttu-id="4d424-113">Добавьте следующий код в метод `ConvertBack` .</span><span class="sxs-lookup"><span data-stu-id="4d424-113">Add the following code to the `ConvertBack` method.</span></span> <span data-ttu-id="4d424-114">Этот код преобразует входящий элемент поля со списком обратно в <xref:System.Activities.InArgument%601>.</span><span class="sxs-lookup"><span data-stu-id="4d424-114">This code converts the incoming combo box item back to an <xref:System.Activities.InArgument%601>.</span></span>

    ```csharp
    // Convert combo box value to InArgument<string>
                string itemContent = (string)((ComboBoxItem)value).Content;
                VisualBasicValue<string> vbArgument = new VisualBasicValue<string>(itemContent);
                InArgument<string> inArgument = new InArgument<string>(vbArgument);
                return inArgument;
    ```

     <span data-ttu-id="4d424-115">Выражение в предыдущем фрагменте кода можно также создать с помощью <xref:Microsoft.CSharp.Activities.CSharpValue%601> вместо <xref:Microsoft.VisualBasic.Activities.VisualBasicValue%601>.</span><span class="sxs-lookup"><span data-stu-id="4d424-115">The expression in the above code snippet can also be created using <xref:Microsoft.CSharp.Activities.CSharpValue%601> instead of <xref:Microsoft.VisualBasic.Activities.VisualBasicValue%601>.</span></span>

    ```csharp
    // Convert combo box value to InArgument<string>
                string itemContent = (string)((ComboBoxItem)value).Content;
                CSharpValue<string> csArgument = new CSharpValue<string>(itemContent);
                InArgument<string> inArgument = new InArgument<string>(csArgument);
                return inArgument;
    ```

## <a name="adding-the-comboboxitemconverter-to-the-custom-designer-of-an-activity"></a><span data-ttu-id="4d424-116">Добавление класса ComboBoxItemConverter в конструктор пользовательского действия</span><span class="sxs-lookup"><span data-stu-id="4d424-116">Adding the ComboBoxItemConverter to the custom designer of an activity</span></span>

1. <span data-ttu-id="4d424-117">Добавьте новый элемент в проект.</span><span class="sxs-lookup"><span data-stu-id="4d424-117">Add a new item to the project.</span></span> <span data-ttu-id="4d424-118">В диалоговом окне «Новый элемент» выберите узел «Рабочий процесс» и тип нового элемента «Конструктор действия».</span><span class="sxs-lookup"><span data-stu-id="4d424-118">In the New Item dialog, select the Workflow node and select Activity Designer as the type of the new item.</span></span> <span data-ttu-id="4d424-119">Присвойте элементу имя CustomPropertyDesigner.</span><span class="sxs-lookup"><span data-stu-id="4d424-119">Name the item CustomPropertyDesigner.</span></span>

2. <span data-ttu-id="4d424-120">Добавьте в новый конструктор поле со списком.</span><span class="sxs-lookup"><span data-stu-id="4d424-120">Add a Combo Box to the new designer.</span></span> <span data-ttu-id="4d424-121">В свойстве Items добавьте в поле со списком два элемента со значениями «Item1» и «Item2».</span><span class="sxs-lookup"><span data-stu-id="4d424-121">In the Items property, add a couple of items to the combo box, with Content values of "Item1" and 'Item2".</span></span>

3. <span data-ttu-id="4d424-122">Измените XAML поля со списком, добавив новый преобразователь элементов, который будет использоваться в поле со списком.</span><span class="sxs-lookup"><span data-stu-id="4d424-122">Modify the XAML of the combo box to add the new item converter as the item converter to be used for the combo box.</span></span> <span data-ttu-id="4d424-123">Преобразователь добавляется в качестве ресурса в сегмент ActivityDesigner.Resources и указывает преобразователь в атрибуте Converter для <xref:System.Windows.Controls.ComboBox>.</span><span class="sxs-lookup"><span data-stu-id="4d424-123">The converter is added as a resource in the ActivityDesigner.Resources segment, and specifies the converter in the Converter attribute for the <xref:System.Windows.Controls.ComboBox>.</span></span> <span data-ttu-id="4d424-124">Обратите внимание, что пространство имен проекта указывается в атрибутах пространства имен для конструктора действий. Если конструктор предполагается использовать в другом проекте, то придется изменить это пространство имен.</span><span class="sxs-lookup"><span data-stu-id="4d424-124">Note that the namespace of the project is specified in the namespaces attributes for the activity designer; if the designer is to be used in a different project, this namespace will need to be changed.</span></span>

    ```xaml
    <sap:ActivityDesigner x:Class="CustomProperty.CustomPropertyDesigner"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:c="clr-namespace:CustomProperty"
        xmlns:sap="clr-namespace:System.Activities.Presentation;assembly=System.Activities.Presentation"
        xmlns:sapv="clr-namespace:System.Activities.Presentation.View;assembly=System.Activities.Presentation">

        <sap:ActivityDesigner.Resources>
            <ResourceDictionary>
                <c:ComboBoxItemConverter x:Key="comboBoxItemConverter"/>
            </ResourceDictionary>
        </sap:ActivityDesigner.Resources>
        <Grid>
            <ComboBox SelectedValue="{Binding Path=ModelItem.Text, Mode=TwoWay, Converter={StaticResource comboBoxItemConverter}}"  Height="23" HorizontalAlignment="Left" Margin="132,5,0,0" Name="comboBox1" VerticalAlignment="Top" Width="120" ItemsSource="{Binding}">
                <ComboBoxItem>item1</ComboBoxItem>
                <ComboBoxItem>item2</ComboBoxItem>
            </ComboBox>
        </Grid>
    </sap:ActivityDesigner>
    ```

4. <span data-ttu-id="4d424-125">Создайте новый элемент типа <xref:System.Activities.CodeActivity>.</span><span class="sxs-lookup"><span data-stu-id="4d424-125">Create a new item of type <xref:System.Activities.CodeActivity>.</span></span> <span data-ttu-id="4d424-126">Код по умолчанию, созданный для действия интерактивной средой, подойдет для этого примера.</span><span class="sxs-lookup"><span data-stu-id="4d424-126">The default code created by the IDE for the activity will be sufficient for this example.</span></span>

5. <span data-ttu-id="4d424-127">Добавьте в определение класса следующий атрибут.</span><span class="sxs-lookup"><span data-stu-id="4d424-127">Add the following attribute to the class definition:</span></span>

    ```csharp
    [Designer(typeof(CustomPropertyDesigner))]
    ```

     <span data-ttu-id="4d424-128">Эта строка связывает новый конструктор с новым классом.</span><span class="sxs-lookup"><span data-stu-id="4d424-128">This line associates the new designer with the new class.</span></span>

 <span data-ttu-id="4d424-129">Новое действие должно быть связано с конструктором.</span><span class="sxs-lookup"><span data-stu-id="4d424-129">The new activity should now be associated with the designer.</span></span> <span data-ttu-id="4d424-130">Чтобы проверить новое действие, добавьте его в рабочий процесс и задайте для поля со списком два значения.</span><span class="sxs-lookup"><span data-stu-id="4d424-130">To test the new activity, add it to a workflow, and set the combo box to the two values.</span></span> <span data-ttu-id="4d424-131">Окно свойств должно обновиться: в нем появится значение поля со списком.</span><span class="sxs-lookup"><span data-stu-id="4d424-131">The properties window should update to reflect the combo box value.</span></span>
