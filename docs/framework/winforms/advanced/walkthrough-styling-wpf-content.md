---
title: Пошаговое руководство. стиль содержимого WPF
ms.date: 03/30/2017
helpviewer_keywords:
- WPF Designer [Windows Forms], styling WPF content
- interoperability [WDF]
- styles [Windows Forms], WPF content
ms.assetid: e574aac7-7ea4-4cdb-8034-bab541f000df
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: e52297f51c74fc3dba93c987fd5b9bd5b6801777
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76732542"
---
# <a name="walkthrough-style-wpf-content"></a>Пошаговое руководство. стиль содержимого WPF

В этой статье показано, как применять стили к элементу управления Windows Presentation Foundation (WPF), размещенному в форме Windows Forms.

## <a name="prerequisites"></a>предварительные требования

Для выполнения шагов, описанных в этом руководстве, вам понадобится Visual Studio.

## <a name="create-the-project"></a>Создание проекта

Откройте Visual Studio и создайте новый проект Windows Forms приложения в Visual Basic или Visual C# с именем `StylingWpfContent`.

> [!NOTE]
> При размещении содержимого WPF поддерживаются только проекты C# и Visual Basic.

## <a name="create-the-wpf-control-types"></a>Создание типов элементов управления WPF

После добавления в проект типа элемента управления WPF можно разместить его в элементе управления <xref:System.Windows.Forms.Integration.ElementHost>.

1. Добавьте в решение новый проект WPF <xref:System.Windows.Controls.UserControl>. Используйте имя по умолчанию для этого типа элемента управления (`UserControl1.xaml`). Дополнительные сведения см. в разделе [Пошаговое руководство. Создание нового содержимого WPF на Windows Forms во время разработки](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).

2. Убедитесь в том, что элемент `UserControl1` выбран в представлении конструирования.

3. В окне **Свойства** задайте для свойств <xref:System.Windows.FrameworkElement.Width%2A> и <xref:System.Windows.FrameworkElement.Height%2A> значение **200**.

4. Добавьте элемент управления <xref:System.Windows.Controls.Button?displayProperty=nameWithType> в <xref:System.Windows.Controls.UserControl> и присвойте свойству <xref:System.Windows.Controls.ContentControl.Content%2A> значение **Cancel**.

5. Добавьте второй элемент управления <xref:System.Windows.Controls.Button?displayProperty=nameWithType> в <xref:System.Windows.Controls.UserControl> и присвойте свойству <xref:System.Windows.Controls.ContentControl.Content%2A> значение **ОК**.

6. Создайте проект.

## <a name="apply-a-style-to-a-wpf-control"></a>Применение стиля к элементу управления WPF

Для изменения внешнего вида и поведения элемента управления WPF к нему можно применить различные стили.

1. Откройте `Form1` в конструкторе Windows Forms.

1. На **панели элементов**дважды щелкните `UserControl1`, чтобы создать экземпляр `UserControl1` в форме.

   Экземпляр `UserControl1` размещается в новом элементе управления <xref:System.Windows.Forms.Integration.ElementHost> с именем `elementHost1`.

1. На панели смарт-тегов для `elementHost1`щелкните **Изменить размещенное содержимое** из раскрывающегося списка.

   `UserControl1` откроется в конструкторе WPF.

1. В представлении XAML вставьте следующий код XAML после открывающего тега `<UserControl>` . Этот код XAML создает градиент с контрастной градиентной границей. При нажатии на элемент управления градиенты изменяются, формируя образ нажатой кнопки. Более подробную информацию см. в разделе [Стилизация и использование шаблонов](../../../desktop-wpf/fundamentals/styles-templates-overview.md).

   ```xaml
   <UserControl.Resources>
    <LinearGradientBrush x:Key="NormalBrush" EndPoint="0,1" StartPoint="0,0">
        <GradientStop Color="#FFF" Offset="0.0"/>
        <GradientStop Color="#CCC" Offset="1.0"/>
    </LinearGradientBrush>
    <LinearGradientBrush x:Key="PressedBrush" EndPoint="0,1" StartPoint="0,0">
        <GradientStop Color="#BBB" Offset="0.0"/>
        <GradientStop Color="#EEE" Offset="0.1"/>
        <GradientStop Color="#EEE" Offset="0.9"/>
        <GradientStop Color="#FFF" Offset="1.0"/>
    </LinearGradientBrush>
    <LinearGradientBrush x:Key="NormalBorderBrush" EndPoint="0,1" StartPoint="0,0">
        <GradientStop Color="#CCC" Offset="0.0"/>
        <GradientStop Color="#444" Offset="1.0"/>
    </LinearGradientBrush>
    <LinearGradientBrush x:Key="BorderBrush" EndPoint="0,1" StartPoint="0,0">
        <GradientStop Color="#CCC" Offset="0.0"/>
        <GradientStop Color="#444" Offset="1.0"/>
    </LinearGradientBrush>
    <LinearGradientBrush x:Key="PressedBorderBrush" EndPoint="0,1" StartPoint="0,0">
        <GradientStop Color="#444" Offset="0.0"/>
        <GradientStop Color="#888" Offset="1.0"/>
    </LinearGradientBrush>

    <Style x:Key="SimpleButton" TargetType="{x:Type Button}" BasedOn="{x:Null}">
        <Setter Property="Background" Value="{StaticResource NormalBrush}"/>
        <Setter Property="BorderBrush" Value="{StaticResource NormalBorderBrush}"/>
        <Setter Property="Template">
            <Setter.Value>
                <ControlTemplate TargetType="{x:Type Button}">
                    <Grid x:Name="Grid">
                        <Border x:Name="Border" Background="{TemplateBinding Background}" BorderBrush="{TemplateBinding BorderBrush}" BorderThickness="{TemplateBinding BorderThickness}" Padding="{TemplateBinding Padding}"/>
                        <ContentPresenter HorizontalAlignment="{TemplateBinding HorizontalContentAlignment}" Margin="{TemplateBinding Padding}" VerticalAlignment="{TemplateBinding VerticalContentAlignment}" RecognizesAccessKey="True"/>
                    </Grid>
                    <ControlTemplate.Triggers>
                        <Trigger Property="IsPressed" Value="true">
                            <Setter Property="Background" Value="{StaticResource PressedBrush}" TargetName="Border"/>
                            <Setter Property="BorderBrush" Value="{StaticResource PressedBorderBrush}" TargetName="Border"/>
                        </Trigger>
                    </ControlTemplate.Triggers>
                </ControlTemplate>
            </Setter.Value>
        </Setter>
    </Style>
   </UserControl.Resources>
   ```

1. Примените стиль `SimpleButton`, определенный на предыдущем шаге, к кнопке Отмена, вставив следующий код XAML в тег `<Button>` кнопки **Отмена** .

   ```xaml
   Style="{StaticResource SimpleButton}
   ```

   Объявление кнопки будет похоже на следующий XAML:

   ```xaml
   <Button Height="23" Margin="41,52,98,0" Name="button1" VerticalAlignment="Top"
                Style="{StaticResource SimpleButton}">Cancel</Button>
   ```

1. Создайте проект.

1. Откройте `Form1` в конструкторе Windows Forms.

1. Новый стиль применяется для элемента управления button.

1. В меню **Отладка** выберите команду **начать отладку** , чтобы запустить приложение.

1. Нажмите кнопки **ОК** и **Отмена** и просмотрите различия.

## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Миграция и взаимодействие систем](../../wpf/advanced/migration-and-interoperability.md)
- [Использование элементов управления WPF](using-wpf-controls.md)
- [Проектирование XAML в Visual Studio](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
- [Обзор XAML (WPF)](../../wpf/advanced/xaml-overview-wpf.md)
- [Использование стилей и шаблонов](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
