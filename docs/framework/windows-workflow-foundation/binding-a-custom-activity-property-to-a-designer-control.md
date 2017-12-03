---
title: "Привязка пользовательского свойства действия к элементу управления конструктора"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2e8061ea-10f5-407c-a31f-d0d74ce12f27
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 07a39983d0e561fdad4c09e641912b0d15aa4033
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="binding-a-custom-activity-property-to-a-designer-control"></a>Привязка пользовательского свойства действия к элементу управления конструктора
Привязка элемента управления конструктора текстового поля к аргументу действия выполняется очень просто, однако при привязке сложного элемента управления конструктора (например, поля со списком) к аргументу действия могут возникнуть некоторые сложности. В этом разделе описан способ привязки аргумента действия к полю со списком в конструкторе пользовательских действий.  
  
#### <a name="creating-the-combo-box-item-converter"></a>Создание преобразователя элементов поля со списком  
  
1.  Создайте новое пустое решение в среде Visual Studio 2010 под названием CustomProperty.  
  
2.  Создайте новый класс с именем ComboBoxItemConverter. Добавьте ссылку на сборку System.Windows.Data и сделайте класс производным от <xref:System.Windows.Data.IValueConverter>. В Visual Studio внедрите интерфейс, создав заглушки для `Convert` и `ConvertBack`.  
  
3.  Добавьте следующий код в метод `Convert`. Этот код преобразует <xref:System.Activities.InArgument%601> действия типа <xref:System.String> в значение, которое нужно вставить в конструктор.  
  
    ```  
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
  
     Выражение в предыдущем фрагменте кода можно также создать с помощью <xref:Microsoft.CSharp.Activities.CSharpValue%601> вместо <xref:Microsoft.VisualBasic.Activities.VisualBasicValue%601>.  
  
    ```  
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
  
4.  Добавьте следующий код в метод `ConvertBack`. Этот код преобразует входящий элемент поля со списком обратно в <xref:System.Activities.InArgument%601>.  
  
    ```  
    // Convert combo box value to InArgument<string>  
                string itemContent = (string)((ComboBoxItem)value).Content;  
                VisualBasicValue<string> vbArgument = new VisualBasicValue<string>(itemContent);  
                InArgument<string> inArgument = new InArgument<string>(vbArgument);  
                return inArgument;  
    ```  
  
     Выражение в предыдущем фрагменте кода можно также создать с помощью <xref:Microsoft.CSharp.Activities.CSharpValue%601> вместо <xref:Microsoft.VisualBasic.Activities.VisualBasicValue%601>.  
  
    ```  
    // Convert combo box value to InArgument<string>  
                string itemContent = (string)((ComboBoxItem)value).Content;  
                CSharpValue<string> csArgument = new CSharpValue<string>(itemContent);  
                InArgument<string> inArgument = new InArgument<string>(csArgument);  
                return inArgument;  
    ```  
  
#### <a name="adding-the-comboboxitemconverter-to-the-custom-designer-of-an-activity"></a>Добавление класса ComboBoxItemConverter в конструктор пользовательского действия  
  
1.  Добавьте новый элемент в проект. В диалоговом окне «Новый элемент» выберите узел «Рабочий процесс» и тип нового элемента «Конструктор действия». Присвойте элементу имя CustomPropertyDesigner.  
  
2.  Добавьте в новый конструктор поле со списком. В свойстве Items добавьте в поле со списком два элемента со значениями «Item1» и «Item2».  
  
3.  Измените XAML поля со списком, добавив новый преобразователь элементов, который будет использоваться в поле со списком. Преобразователь добавляется в качестве ресурса в сегмент ActivityDesigner.Resources и указывает преобразователь в атрибуте Converter для <xref:System.Windows.Controls.ComboBox>. Обратите внимание, что пространство имен проекта указывается в атрибутах пространства имен для конструктора действий. Если конструктор предполагается использовать в другом проекте, то придется изменить это пространство имен.  
  
    ```  
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
  
4.  Создайте новый элемент типа <xref:System.Activities.CodeActivity>. Код по умолчанию, созданный для действия интерактивной средой, подойдет для этого примера.  
  
5.  Добавьте в определение класса следующий атрибут.  
  
    ```  
    [Designer(typeof(CustomPropertyDesigner))]  
    ```  
  
     Эта строка связывает новый конструктор с новым классом.  
  
 Новое действие должно быть связано с конструктором. Чтобы проверить новое действие, добавьте его в рабочий процесс и задайте для поля со списком два значения. Окно свойств должно обновиться: в нем появится значение поля со списком.
