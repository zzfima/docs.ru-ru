---
title: "Пошаговое руководство. Создание кнопки с помощью XAML"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: buttons [WPF]
ms.assetid: 138c41c4-1759-4bbf-8d77-77031a06a8a0
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 543e6496c826c864dc77e50fd096fc4cb43f600e
ms.sourcegitcommit: 01ea3686e74ff05e4f6de3d8d46dc603d051ec00
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/13/2017
---
# <a name="walkthrough-create-a-button-by-using-xaml"></a>Пошаговое руководство. Создание кнопки с помощью XAML
Цель данного руководства — сведения о создании анимированной кнопки для использования в [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] приложения. В этом пошаговом руководстве используется стиль и шаблон для создания ресурса пользовательской кнопки, которая позволяет повторно использовать код и разделять логику от объявления кнопки. В этом пошаговом руководстве приведено полностью в [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].  
  
> [!IMPORTANT]
>  В этом пошаговом руководстве поможет выполнить шаги для создания приложения путем ввода или копирования и вставки [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] в Microsoft [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)]. Если вы предпочитаете узнать, как использовать средство разработки (Microsoft Expression Blend) для создания того же приложения см. в разделе [Создание кнопки с помощью Microsoft Expression Blend](../../../../docs/framework/wpf/controls/walkthrough-create-a-button-by-using-microsoft-expression-blend.md).  
  
 На следующем рисунке показана созданные кнопки.  
  
 ![Настраиваемые кнопки, созданные с помощью XAML](../../../../docs/framework/wpf/controls/media/custom-button-animatedbutton-5.gif "custom_button_AnimatedButton_5")  
  
## <a name="create-basic-buttons"></a>Создание простых кнопок  
 Начнем с создания проекта и добавления нескольких кнопок в окно.  
  
#### <a name="to-create-a-new-wpf-project-and-add-buttons-to-the-window"></a>Чтобы создать новый проект WPF и добавить кнопки в окно  
  
1.  Запустить[!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)].  
  
2.  **Создайте новый проект WPF:** на **файл** последовательно выберите пункты **New**, а затем нажмите кнопку **проекта**. Найти **приложения Windows (WPF)** шаблон и имя проекта «AnimatedButton». Это создает основу для приложения.  
  
3.  **Добавление кнопок basic по умолчанию:** все файлы, необходимые для этого пошагового руководства включенных в шаблон. Откройте файл Window1.xaml, дважды щелкнув его в обозревателе решений. По умолчанию — <xref:System.Windows.Controls.Grid> элемент в Window1.xaml. Удалить <xref:System.Windows.Controls.Grid> элемент и добавьте несколько кнопок для [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] страницы путем ввода или копирования и вставки в Window1.xaml следующий выделенный код:  
  
    ```xaml  
    <Window x:Class="AnimatedButton.Window1"  
      xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"  
      xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"  
      Title="AnimatedButton" Height="300" Width="300"   
      Background="Black">   <!-- Buttons arranged vertically inside a StackPanel. -->   <StackPanel HorizontalAlignment="Left">     <Button>Button 1</Button>     <Button>Button 2</Button>     <Button>Button 3</Button>   </StackPanel>  
  
    </Window>  
    ```  
  
     Нажмите клавишу F5 для запуска приложения; Вы увидите набор кнопок, который выглядит как на следующем рисунке.  
  
     ![Три основные кнопки](../../../../docs/framework/wpf/controls/media/custom-button-animatedbutton-1.gif "custom_button_AnimatedButton_1")  
  
     После создания простых кнопок вы закончили работу в файле Window1.xaml. Остальная часть пошагового руководства основное внимание уделяется файл app.xaml, определять стили и шаблон для кнопок.  
  
## <a name="set-basic-properties"></a>Набор основных свойств  
 Далее зададим некоторые свойства этих кнопок, определяющие внешний вид кнопки и макет. Вместо того чтобы задавать свойства для кнопок по отдельности, будет использовать ресурсы для определения свойств кнопки для всего приложения. Ресурсы приложений похожи на внешние [!INCLUDE[TLA#tla_css](../../../../includes/tlasharptla-css-md.md)] для веб-страниц; Однако ресурсы являются гораздо эффективнее, чем [!INCLUDE[TLA#tla_css](../../../../includes/tlasharptla-css-md.md)], как можно будет увидеть в конце данного пошагового руководства. Дополнительные сведения о ресурсах см. в разделе [ресурсов XAML](../../../../docs/framework/wpf/advanced/xaml-resources.md).  
  
#### <a name="to-use-styles-to-set-basic-properties-on-the-buttons"></a>Чтобы использовать стили для установки основных свойств кнопок  
  
1.  **Определение блока ресурсы приложения:** откройте файл app.xaml и добавьте следующую выделенную разметку, если он еще не существует:  
  
    ```xaml  
    <Application x:Class="AnimatedButton.App"  
      xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"  
      xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"  
      StartupUri="Window1.xaml"  
      >  
      <Application.Resources>
        <!-- Resources for the entire application can be defined here. -->
      </Application.Resources>  
    </Application>  
    ```  
  
     Область ресурса определяется где определить ресурс. Определение ресурсов в `Application.Resources` в файле app.xaml файл позволяет ресурса для использования в любом месте в приложении. Дополнительные сведения об определении области ресурсов см. в разделе [ресурсов XAML](../../../../docs/framework/wpf/advanced/xaml-resources.md).  
  
2.  **Создание стиля и определять значения свойств основных с ним:** добавьте следующую разметку, чтобы `Application.Resources` блока. Эта разметка создает <xref:System.Windows.Style> , применяется для всех кнопок в приложении, устанавливая <xref:System.Windows.FrameworkElement.Width%2A> кнопок на 90 и <xref:System.Windows.FrameworkElement.Margin%2A> до 10:  
  
    ```xaml  
    <Application.Resources>  
      <Style TargetType="Button">
        <Setter Property="Width" Value="90" />
        <Setter Property="Margin" Value="10" />
      </Style>  
    </Application.Resources>  
    ```  
  
     <xref:System.Windows.Style.TargetType%2A> Свойство указывает, что стиль применяется ко всем объектам типа <xref:System.Windows.Controls.Button>. Каждый <xref:System.Windows.Setter> задает другое значение свойства для <xref:System.Windows.Style>. Поэтому в этот момент все кнопки в приложении имеет шириной равной 90 и границей 10.  Если нажать клавишу F5 для запуска приложения, вы увидите следующее окно.  
  
     ![Кнопки с шириной равной 90 и границей 10](../../../../docs/framework/wpf/controls/media/custom-button-animatedbutton-2.gif "custom_button_AnimatedButton_2")  
  
     Есть намного больше, можно сделать с помощью стилей, включая различные способы настройки целевых объектах, указание сложных значений свойств и даже использование стилей в качестве входных данных для других стилей. Более подробную информацию см. в разделе [Стилизация и использование шаблонов](../../../../docs/framework/wpf/controls/styling-and-templating.md).  
  
3.  **Задайте значение свойства стиля для ресурса:** ресурсы позволяют простой способ повторного использования часто определяемых объектов и значений. Это особенно полезно для определения сложных значений с помощью ресурсов, чтобы сделать код более удобным. Добавьте следующую выделенную разметку в файл app.xaml.  
  
    ```xaml  
    <Application.Resources>  
      <LinearGradientBrush x:Key="GrayBlueGradientBrush" StartPoint="0,0" EndPoint="1,1">
        <GradientStop Color="DarkGray" Offset="0" />
        <GradientStop Color="#CCCCFF" Offset="0.5" />
        <GradientStop Color="DarkGray" Offset="1" />
      </LinearGradientBrush>  
      <Style TargetType="{x:Type Button}">  
        <Setter Property="Background" Value="{StaticResource GrayBlueGradientBrush}" />  
        <Setter Property="Width" Value="80" />  
        <Setter Property="Margin" Value="10" />  
      </Style>  
    </Application.Resources>  
    ```  
  
     Непосредственно под `Application.Resources` блок, вы создали ресурсу с именем «GrayBlueGradientBrush». Этот ресурс определяет горизонтальный градиент. Этот ресурс можно использовать в качестве значения свойства из любого места в приложении, в том числе внутри метода задания стиля кнопки для <xref:System.Windows.Controls.Control.Background%2A> свойства. Теперь все кнопки имеют <xref:System.Windows.Controls.Control.Background%2A> значение свойства для этого градиента.  
  
     Нажмите клавишу F5 для запуска приложения. Он должен выглядеть следующим образом.  
  
     ![Кнопки с фоновым градиентом](../../../../docs/framework/wpf/controls/media/custom-button-animatedbutton-3.gif "custom_button_AnimatedButton_3")  
  
## <a name="create-a-template-that-defines-the-look-of-the-button"></a>Создание шаблона, который определяет внешний вид кнопки  
 В этом разделе создайте шаблон, который настраивает внешний вид (представление) кнопки. Представление кнопки состоит из нескольких объектов, включая прямоугольники и другие компоненты для предоставления уникальный вид кнопки.  
  
 На данный момент управления видом кнопок в приложении выполнялось с помощью изменения свойств кнопки. Что делать, если вы хотите внести кардинально изменить внешний вид кнопки? Шаблоны включают мощным средством управления представлением объекта. Поскольку шаблоны могут использоваться в стилях, можно применить шаблон ко всем объектам, применяется стиль (в этом пошаговом руководстве, кнопки).  
  
#### <a name="to-use-the-template-to-define-the-look-of-the-button"></a>Чтобы использовать шаблон для определения внешнего вида кнопки  
  
1.  **Настройка шаблона:** так, как элементы управления, например <xref:System.Windows.Controls.Button> имеют <xref:System.Windows.Controls.Control.Template%2A> можно определить значение свойства шаблона так же, как и другие значения свойств, заданных в <xref:System.Windows.Style> с помощью <xref:System.Windows.Setter>. Добавьте следующую выделенную разметку в стиль кнопки.  
  
    ```xaml
    <Application.Resources>  
      <LinearGradientBrush x:Key="GrayBlueGradientBrush"   
        StartPoint="0,0" EndPoint="1,1">  
        <GradientStop Color="DarkGray" Offset="0" />  
        <GradientStop Color="#CCCCFF" Offset="0.5" />  
        <GradientStop Color="DarkGray" Offset="1" />  
      </LinearGradientBrush>  
      <Style TargetType="{x:Type Button}">  
        <Setter Property="Background" Value="{StaticResource GrayBlueGradientBrush}" />  
        <Setter Property="Width" Value="80" />  
        <Setter Property="Margin" Value="10" />  
        <Setter Property="Template">
          <Setter.Value>
            <!-- The button template is defined here. -->
          </Setter.Value>
        </Setter>  
      </Style>  
    </Application.Resources>  
    ```  
  
2.  **ALTER презентации кнопки:** на этом этапе необходимо определить шаблон. Добавьте следующую выделенную разметку. Эта разметка задает два <xref:System.Windows.Shapes.Rectangle> элементы со скругленными краями, за которым следует <xref:System.Windows.Controls.DockPanel>. <xref:System.Windows.Controls.DockPanel> Используется для размещения <xref:System.Windows.Controls.ContentPresenter> кнопки. Объект <xref:System.Windows.Controls.ContentPresenter> отображает содержимое кнопки. В этом пошаговом руководстве содержимым является текст («Button 1», «Button 2», «Button 3»). Все компоненты шаблона (прямоугольники и <xref:System.Windows.Controls.DockPanel>) располагаются внутри <xref:System.Windows.Controls.Grid>.  
  
    ```xaml  
    <Setter.Value>  
      <ControlTemplate TargetType="Button">
        <Grid Width="{TemplateBinding Width}" Height="{TemplateBinding Height}" ClipToBounds="True">
          <!-- Outer Rectangle with rounded corners. -->
          <Rectangle x:Name="outerRectangle" HorizontalAlignment="Stretch" VerticalAlignment="Stretch" Stroke="{TemplateBinding Background}" RadiusX="20" RadiusY="20" StrokeThickness="5" Fill="Transparent" />
          <!-- Inner Rectangle with rounded corners. -->
          <Rectangle x:Name="innerRectangle" HorizontalAlignment="Stretch" VerticalAlignment="Stretch" Stroke="Transparent" StrokeThickness="20" Fill="{TemplateBinding Background}" RadiusX="20" RadiusY="20" />
          <!-- Present Content (text) of the button. -->
          <DockPanel Name="myContentPresenterDockPanel">
            <ContentPresenter x:Name="myContentPresenter" Margin="20" Content="{TemplateBinding  Content}" TextBlock.Foreground="Black" />
          </DockPanel>
        </Grid>
      </ControlTemplate>  
    </Setter.Value>  
    ```  
  
     Нажмите клавишу F5 для запуска приложения. Он должен выглядеть следующим образом.  
  
     ![](../../../../docs/framework/wpf/controls/media/custom-button-animatedbutton-4.gif "custom_button_AnimatedButton_4")  
  
3.  **Добавление прозрачности в шаблон:** мы добавим стекла. Сначала создать ресурсы, которые создают эффект градиента прозрачности. Добавьте эти градиентные ресурсы в любом месте в пределах `Application.Resources` блока:  
  
    ```xaml  
    <Application.Resources>  
      <GradientStopCollection x:Key="MyGlassGradientStopsResource">     <GradientStop Color="WhiteSmoke" Offset="0.2" />     <GradientStop Color="Transparent" Offset="0.4" />     <GradientStop Color="WhiteSmoke" Offset="0.5" />     <GradientStop Color="Transparent" Offset="0.75" />     <GradientStop Color="WhiteSmoke" Offset="0.9" />     <GradientStop Color="Transparent" Offset="1" />   </GradientStopCollection>   <LinearGradientBrush x:Key="MyGlassBrushResource"     StartPoint="0,0" EndPoint="1,1" Opacity="0.75"     GradientStops="{StaticResource MyGlassGradientStopsResource}" />  
    <!-- Styles and other resources below here. -->  
    ```  
  
     Эти ресурсы используются как <xref:System.Windows.Shapes.Shape.Fill%2A> для прямоугольника, который вставляется в <xref:System.Windows.Controls.Grid> шаблона кнопки. Добавьте следующую выделенную разметку в шаблон.  
  
    ```  
    <Setter.Value>  
      <ControlTemplate TargetType="{x:Type Button}">  
        <Grid Width="{TemplateBinding Width}" Height="{TemplateBinding Height}"  
    ClipToBounds="True">  
  
        <!-- Outer Rectangle with rounded corners. -->  
        <Rectangle x:Name="outerRectangle" HorizontalAlignment="Stretch"   
          VerticalAlignment="Stretch" Stroke="{TemplateBinding Background}"   
          RadiusX="20" RadiusY="20" StrokeThickness="5" Fill="Transparent" />  
  
        <!-- Inner Rectangle with rounded corners. -->  
        <Rectangle x:Name="innerRectangle" HorizontalAlignment="Stretch"   
          VerticalAlignment="Stretch" Stroke="Transparent" StrokeThickness="20"   
          Fill="{TemplateBinding Background}" RadiusX="20" RadiusY="20" />  
  
        <!-- Glass Rectangle -->     <Rectangle x:Name="glassCube" HorizontalAlignment="Stretch"       VerticalAlignment="Stretch"       StrokeThickness="2" RadiusX="10" RadiusY="10" Opacity="0"       Fill="{StaticResource MyGlassBrushResource}"       RenderTransformOrigin="0.5,0.5">       <Rectangle.Stroke>         <LinearGradientBrush StartPoint="0.5,0" EndPoint="0.5,1">           <LinearGradientBrush.GradientStops>             <GradientStop Offset="0.0" Color="LightBlue" />             <GradientStop Offset="1.0" Color="Gray" />           </LinearGradientBrush.GradientStops>         </LinearGradientBrush>       </Rectangle.Stroke>       <!-- These transforms have no effect as they are declared here.             The reason the transforms are included is to be targets             for animation (see later). -->       <Rectangle.RenderTransform>         <TransformGroup>           <ScaleTransform />           <RotateTransform />         </TransformGroup>       </Rectangle.RenderTransform>       <!-- A BevelBitmapEffect is applied to give the button a             "Beveled" look. -->       <Rectangle.BitmapEffect>         <BevelBitmapEffect />       </Rectangle.BitmapEffect>     </Rectangle>  
  
        <!-- Present Text of the button. -->  
        <DockPanel Name="myContentPresenterDockPanel">  
          <ContentPresenter x:Name="myContentPresenter" Margin="20"   
            Content="{TemplateBinding  Content}" TextBlock.Foreground="Black" />  
        </DockPanel>  
      </Grid>  
    </ControlTemplate>  
    </Setter.Value>  
    ```  
  
     Обратите внимание, что <xref:System.Windows.UIElement.Opacity%2A> прямоугольника с `x:Name` свойство «glassCube» задано значение 0, поэтому при выполнении примера, вы не видите прозрачного прямоугольника в верхней части. Это потому, что впоследствии будет происходить добавление триггеров в шаблон для взаимодействия пользователя с помощью кнопки. Тем не менее, вы увидите, что эта кнопка выглядит теперь изменив <xref:System.Windows.UIElement.Opacity%2A> значение 1, а также выполнение приложения. См. следующий рисунок. Прежде чем переходить к следующему шагу изменить <xref:System.Windows.UIElement.Opacity%2A> значение 0.  
  
     ![Настраиваемые кнопки, созданные с помощью XAML](../../../../docs/framework/wpf/controls/media/custom-button-animatedbutton-5.gif "custom_button_AnimatedButton_5")  
  
## <a name="create-button-interactivity"></a>Создать интерактивную кнопку  
 В этом разделе вы создадите свойство триггеров и триггеров событий для изменения значений свойств и выполнения анимации в ответ на действия пользователя, например Наведение указателя мыши на кнопку и нажав кнопку.  
  
 Простой способ добавления интерактивности (указатель, оставьте мыши, нажмите кнопку и т. д.) является определение триггеров в шаблоне или стиле. Для создания <xref:System.Windows.Trigger>, определять свойство «условие», такие как: кнопки <xref:System.Windows.UIElement.IsMouseOver%2A> значение свойства равно `true`. Затем предстоит определить элементы Setter (действия), выполняемые при условия триггера.  
  
#### <a name="to-create-button-interactivity"></a>Чтобы создать интерактивную кнопку  
  
1.  **Добавить триггеры шаблона:** добавьте выделенную разметку в шаблон.  
  
    ```  
    <Setter.Value>  
      <ControlTemplate TargetType="{x:Type Button}">  
        <Grid Width="{TemplateBinding Width}"   
          Height="{TemplateBinding Height}" ClipToBounds="True">  
  
          <!-- Outer Rectangle with rounded corners. -->  
          <Rectangle x:Name="outerRectangle" HorizontalAlignment="Stretch"   
          VerticalAlignment="Stretch" Stroke="{TemplateBinding Background}"   
          RadiusX="20" RadiusY="20" StrokeThickness="5" Fill="Transparent" />  
  
          <!-- Inner Rectangle with rounded corners. -->  
          <Rectangle x:Name="innerRectangle" HorizontalAlignment="Stretch"   
            VerticalAlignment="Stretch" Stroke="Transparent"   
            StrokeThickness="20"   
            Fill="{TemplateBinding Background}" RadiusX="20" RadiusY="20"   
          />  
  
          <!-- Glass Rectangle -->  
          <Rectangle x:Name="glassCube" HorizontalAlignment="Stretch"  
            VerticalAlignment="Stretch"  
            StrokeThickness="2" RadiusX="10" RadiusY="10" Opacity="0"  
            Fill="{StaticResource MyGlassBrushResource}"  
            RenderTransformOrigin="0.5,0.5">  
            <Rectangle.Stroke>  
              <LinearGradientBrush StartPoint="0.5,0" EndPoint="0.5,1">  
                <LinearGradientBrush.GradientStops>  
                  <GradientStop Offset="0.0" Color="LightBlue" />  
                  <GradientStop Offset="1.0" Color="Gray" />  
                </LinearGradientBrush.GradientStops>  
              </LinearGradientBrush>  
            </Rectangle.Stroke>  
  
            <!-- These transforms have no effect as they   
                 are declared here.   
                 The reason the transforms are included is to be targets   
                 for animation (see later). -->  
            <Rectangle.RenderTransform>  
              <TransformGroup>  
                <ScaleTransform />  
                <RotateTransform />  
              </TransformGroup>  
            </Rectangle.RenderTransform>  
  
              <!-- A BevelBitmapEffect is applied to give the button a   
                   "Beveled" look. -->  
            <Rectangle.BitmapEffect>  
              <BevelBitmapEffect />  
            </Rectangle.BitmapEffect>  
          </Rectangle>  
  
          <!-- Present Text of the button. -->  
          <DockPanel Name="myContentPresenterDockPanel">  
            <ContentPresenter x:Name="myContentPresenter" Margin="20"   
              Content="{TemplateBinding  Content}" TextBlock.Foreground="Black" />  
          </DockPanel>  
        </Grid>  
  
        <ControlTemplate.Triggers>       <!-- Set action triggers for the buttons and define            what the button does in response to those triggers. -->     </ControlTemplate.Triggers>  
      </ControlTemplate>  
    </Setter.Value>  
    ```  
  
2.  **Добавить триггеры свойств:** добавьте выделенную разметку для `ControlTemplate.Triggers` блока:  
  
    ```  
    <ControlTemplate.Triggers>  
  
      <!-- Set properties when mouse pointer is over the button. -->   <Trigger Property="IsMouseOver" Value="True">     <!-- Below are three property settings that occur when the           condition is met (user mouses over button).  -->     <!-- Change the color of the outer rectangle when user           mouses over it. -->     <Setter Property ="Rectangle.Stroke" TargetName="outerRectangle"       Value="{DynamicResource {x:Static SystemColors.HighlightBrushKey}}" />     <!-- Sets the glass opacity to 1, therefore, the           glass "appears" when user mouses over it. -->     <Setter Property="Rectangle.Opacity" Value="1" TargetName="glassCube" />     <!-- Makes the text slightly blurry as though you           were looking at it through blurry glass. -->     <Setter Property="ContentPresenter.BitmapEffect"        TargetName="myContentPresenter">       <Setter.Value>         <BlurBitmapEffect Radius="1" />       </Setter.Value>     </Setter>   </Trigger>  
  
    <ControlTemplate.Triggers/>  
    ```  
  
     Нажмите клавишу F5, чтобы запустить приложение и увидеть эффект при запуске указатель мыши над кнопками.  
  
3.  **Добавление триггера фокус:** Далее мы добавим некоторые аналогичные методы задания для обработки случая, когда кнопка имеет фокус (например, при нажатии ее).  
  
    ```  
    <ControlTemplate.Triggers>  
  
      <!-- Set properties when mouse pointer is over the button. -->  
      <Trigger Property="IsMouseOver" Value="True">  
  
        <!-- Below are three property settings that occur when the   
             condition is met (user mouses over button).  -->  
        <!-- Change the color of the outer rectangle when user          mouses over it. -->  
        <Setter Property ="Rectangle.Stroke" TargetName="outerRectangle"  
          Value="{DynamicResource {x:Static SystemColors.HighlightBrushKey}}" />  
  
        <!-- Sets the glass opacity to 1, therefore, the          glass "appears" when user mouses over it. -->  
        <Setter Property="Rectangle.Opacity" Value="1"       TargetName="glassCube" />  
  
        <!-- Makes the text slightly blurry as though you were          looking at it through blurry glass. -->  
        <Setter Property="ContentPresenter.BitmapEffect"       TargetName="myContentPresenter">  
          <Setter.Value>  
            <BlurBitmapEffect Radius="1" />  
          </Setter.Value>  
        </Setter>  
      </Trigger>  
      <!-- Set properties when button has focus. -->   <Trigger Property="IsFocused" Value="true">     <Setter Property="Rectangle.Opacity" Value="1"       TargetName="glassCube" />     <Setter Property="Rectangle.Stroke" TargetName="outerRectangle"       Value="{DynamicResource {x:Static SystemColors.HighlightBrushKey}}" />     <Setter Property="Rectangle.Opacity" Value="1" TargetName="glassCube" />   </Trigger>  
  
    </ControlTemplate.Triggers>  
    ```  
  
     Нажмите клавишу F5 для запуска приложения и выберите одну из кнопок. Обратите внимание, что кнопка остается выделенной после нажатия, поскольку она по-прежнему имеет фокус. Если щелкнуть еще одну кнопку «Создать» получает фокус, во время его утрачивает последним.  
  
4.  **Добавление анимации для** <xref:System.Windows.UIElement.MouseEnter> **и** <xref:System.Windows.UIElement.MouseLeave> **:** Далее будет добавлена анимация к триггерам. Добавьте следующую разметку в любое место `ControlTemplate.Triggers` блока.  
  
    ```  
    <!-- Animations that start when mouse enters and leaves button. -->  
    <EventTrigger RoutedEvent="Mouse.MouseEnter">  
      <EventTrigger.Actions>  
        <BeginStoryboard Name="mouseEnterBeginStoryboard">  
          <Storyboard>  
          <!-- This animation makes the glass rectangle shrink in the X direction. -->  
            <DoubleAnimation Storyboard.TargetName="glassCube"   
              Storyboard.TargetProperty=  
              "(Rectangle.RenderTransform).(TransformGroup.Children)[0].(ScaleTransform.ScaleX)"  
              By="-0.1" Duration="0:0:0.5" />  
            <!-- This animation makes the glass rectangle shrink in the Y direction. -->  
            <DoubleAnimation  
            Storyboard.TargetName="glassCube"   
              Storyboard.TargetProperty=  
              "(Rectangle.RenderTransform).(TransformGroup.Children)[0].(ScaleTransform.ScaleY)"   
              By="-0.1" Duration="0:0:0.5" />  
          </Storyboard>  
        </BeginStoryboard>  
      </EventTrigger.Actions>  
    </EventTrigger>  
    <EventTrigger RoutedEvent="Mouse.MouseLeave">  
      <EventTrigger.Actions>  
        <!-- Stopping the storyboard sets all animated properties back to default. -->  
        <StopStoryboard BeginStoryboardName="mouseEnterBeginStoryboard" />  
      </EventTrigger.Actions>  
    </EventTrigger>  
    ```  
  
     Прозрачный прямоугольник уменьшается, когда указатель мыши перемещается над кнопкой и возвращает в исходное состояние, когда указатель мыши покидает.  
  
     Существуют две анимации, которые запускаются при наведении указателя мыши на кнопку (<xref:System.Windows.UIElement.MouseEnter> события). Эти анимации сжимают прозрачный прямоугольник вдоль оси X и Y. Обратите внимание на <xref:System.Windows.Media.Animation.DoubleAnimation> элементов — <xref:System.Windows.Media.Animation.Timeline.Duration%2A> и <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>. <xref:System.Windows.Media.Animation.Timeline.Duration%2A> Указывает, что анимация выполняется через полсекунды, а <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> указывает, что прозрачный элемент сжимается на 10%.  
  
     Второй триггер события (<xref:System.Windows.UIElement.MouseLeave>) просто останавливает первое из них. При остановке <xref:System.Windows.Media.Animation.Storyboard>, все анимированные свойства возвращаются к значениям по умолчанию. Таким образом когда пользователь перемещает указатель мыши за границы кнопки, кнопки возвращается так, как оно было до перемещения указателя мыши на кнопку. Дополнительные сведения об анимации см. в разделе [Обзор анимации](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).  
  
5.  **Добавление анимации, при щелчке кнопки:** последний шаг — добавить триггер для при нажатии кнопки. Добавьте следующую разметку в любое место `ControlTemplate.Triggers` блока:  
  
    ```  
    <!-- Animation fires when button is clicked, causing glass to spin.  -->  
    <EventTrigger RoutedEvent="Button.Click">  
      <EventTrigger.Actions>  
        <BeginStoryboard>  
          <Storyboard>  
            <DoubleAnimation Storyboard.TargetName="glassCube"   
              Storyboard.TargetProperty=  
              "(Rectangle.RenderTransform).(TransformGroup.Children)[1].(RotateTransform.Angle)"   
              By="360" Duration="0:0:0.5" />  
          </Storyboard>  
        </BeginStoryboard>  
      </EventTrigger.Actions>  
    </EventTrigger>  
    ```  
  
     Нажмите клавишу F5, чтобы запустить приложение и щелкните одну из кнопок. При нажатии кнопки вращаться прозрачного прямоугольника.  
  
## <a name="summary"></a>Сводка  
 В этом пошаговом руководстве вы выполнили следующие упражнения:  
  
-   Целевые <xref:System.Windows.Style> к типу объекта (<xref:System.Windows.Controls.Button>).  
  
-   Управление основными свойствами кнопок в всего приложения с помощью <xref:System.Windows.Style>.  
  
-   Создать ресурсы, такие как градиенты, для использования в качестве значений свойств для <xref:System.Windows.Style> задания.  
  
-   Настройка внешнего вида кнопок во всем приложении путем применения шаблона к кнопкам.  
  
-   Настройка поведения для кнопок в ответ на действия пользователя (например, <xref:System.Windows.UIElement.MouseEnter>, <xref:System.Windows.UIElement.MouseLeave>, и <xref:System.Windows.Controls.Primitives.ButtonBase.Click>), которые включены эффекты анимации.  
  
## <a name="see-also"></a>См. также  
 [Создание кнопки с помощью Microsoft Expression Blend](../../../../docs/framework/wpf/controls/walkthrough-create-a-button-by-using-microsoft-expression-blend.md)  
 [Стилизация и использование шаблонов](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [Общие сведения об эффектах анимации](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [Общие сведения о закраске сплошным цветом и градиентом](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)  
 [Общие сведения об эффектах для точечных рисунков](../../../../docs/framework/wpf/graphics-multimedia/bitmap-effects-overview.md)
