---
title: "Пошаговое руководство. Создание кнопки с помощью XAML | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "кнопки"
ms.assetid: 138c41c4-1759-4bbf-8d77-77031a06a8a0
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Пошаговое руководство. Создание кнопки с помощью XAML
Цель данного пошагового руководства — ознакомление со способами создания анимированной кнопки в приложении [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)].  В данном руководстве используется стиль и шаблон для создания ресурса пользовательской кнопки, которые позволяют повторно использовать код и разделять логику от объявления кнопки.  Данное пошаговое руководство приведено полностью в [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].  
  
> [!IMPORTANT]
>  В данном пошаговом руководстве приведена последовательность действий для создания приложения путем ввода или копирования и вставки [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] в Microsoft [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)].  Если необходимо узнать, как создать это же приложение с помощью средства разработки Microsoft Expression Blend, см. [Создание кнопки с помощью Microsoft Expression Blend](../../../../docs/framework/wpf/controls/walkthrough-create-a-button-by-using-microsoft-expression-blend.md).  
  
 На следующем рисунке показаны созданные кнопки.  
  
 ![Настраиваемые кнопки, созданные при помощи XAML](../../../../docs/framework/wpf/controls/media/custom-button-animatedbutton-5.png "custom\_button\_AnimatedButton\_5")  
  
## Создание простых кнопок  
 Начнем с создания нового проекта и добавления нескольких кнопок в окно.  
  
#### Чтобы создать новый проект WPF и добавить кнопки в окно  
  
1.  Запустите [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)].  
  
2.  **Создайте новый проект WPF:** в меню **Файл** выберите команду **Создать** и выберите пункт **Проект**.  Перейдите к шаблону **Windows Application \(WPF\)** и назовите проект "AnimatedButton".  Будет создан скелет для приложения.  
  
3.  **Добавьте основные кнопки по умолчанию:** все необходимы файлы для данного пошагового руководства предоставляются шаблоном.  Откройте файл Window1.xaml, дважды щелкнув его в обозревателе решений.  По умолчанию в Window1.xaml имеется элемент <xref:System.Windows.Controls.Grid>.  Удалите элемент <xref:System.Windows.Controls.Grid> и добавьте несколько кнопок на страницу [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] путем ввода или копирования и вставки следующего выделенного кода в Window1.xaml:  
  
    ```  
    <Window x:Class="AnimatedButton.Window1"  
      xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"  
      xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"  
      Title="AnimatedButton" Height="300" Width="300"   
      Background="Black">  
  
      <!-- Buttons arranged vertically inside a StackPanel. -->  
      <StackPanel HorizontalAlignment="Left">  
        <Button>Button 1</Button>  
        <Button>Button 2</Button>  
        <Button>Button 3</Button>  
      </StackPanel>  
  
    </Window>  
    ```  
  
     Нажмите клавишу F5 для запуска приложения. Должен появиться набор кнопок, как показано на следующем рисунке.  
  
     ![Три основные кнопки](../../../../docs/framework/wpf/controls/media/custom-button-animatedbutton-1.png "custom\_button\_AnimatedButton\_1")  
  
     Теперь, когда простые кнопки созданы, работа в файле Window1.xaml закончена.  Остальная часть руководства посвящена файлу App.XAML, определяющему стили и шаблон для кнопок.  
  
## Установка основных свойств  
 Теперь зададим некоторые свойства этих кнопок для управления внешним видом и структурой кнопки.  Вместо задания свойств для каждой отдельной кнопки, следует использовать ресурсы для определения свойств кнопки для всего приложения.  Ресурсы приложений похожи на внешние [!INCLUDE[TLA#tla_css](../../../../includes/tlasharptla-css-md.md)] для веб\-страниц. Однако ресурсы являются гораздо более мощным средством, чем [!INCLUDE[TLA#tla_css](../../../../includes/tlasharptla-css-md.md)], что будет продемонстрировано в этом пошаговом руководстве.  Дополнительные сведения о ресурсах см. в разделе [Ресурсы XAML](../../../../docs/framework/wpf/advanced/xaml-resources.md).  
  
#### Чтобы использовать стили для установки основных свойств кнопок  
  
1.  **Определите блок Application.Resources:** откройте файл app.xaml и добавьте следующую выделенную разметку \(если она еще не добавлена\).  
  
    ```  
    <Application x:Class="AnimatedButton.App"  
      xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"  
      xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"  
      StartupUri="Window1.xaml"  
      >  
      <Application.Resources>  
  
        <!-- Resources for the entire application can be   
             defined here. -->  
  
      </Application.Resources>  
    </Application>  
    ```  
  
     Область ресурса определяется по тому, где определяется ресурс.  Определение ресурсов в `Application.Resoureses` в файле app.xaml позволяет использовать ресурсы в любом месте приложения.  Подробные сведения об определении области ресурсов см. в разделе [Ресурсы XAML](../../../../docs/framework/wpf/advanced/xaml-resources.md).  
  
2.  **Создайте стиль и задайте значения для его основных свойств:** добавьте в блок `Application.Resources` следующую разметку.  Эта разметка создает <xref:System.Windows.Style>, который применяется для всех кнопок в приложении, устанавливая <xref:System.Windows.FrameworkElement.Width%2A> кнопок на 90 и <xref:System.Windows.FrameworkElement.Margin%2A> на 10:  
  
    ```  
    <Application.Resources>  
  
      <Style TargetType="Button">  
        <Setter Property="Width" Value="90" />  
        <Setter Property="Margin" Value="10" />  
      </Style>  
  
    </Application.Resources>  
    ```  
  
     Свойство <xref:System.Windows.Style.TargetType%2A> указывает, что стиль применяется ко всем объектам типа <xref:System.Windows.Controls.Button>.  Каждый <xref:System.Windows.Setter> устанавливает различное значение свойства для <xref:System.Windows.Style>.  Поэтому на данном этапе каждая кнопка в приложении имеет ширину 90 и поле 10.  Если нажать клавишу F5 для запуска приложения, появится следующее окно.  
  
     ![Кнопки с шириной равной 90 и границей 10](../../../../docs/framework/wpf/controls/media/custom-button-animatedbutton-2.png "custom\_button\_AnimatedButton\_2")  
  
     Есть много вариантов работы со стилем, включая различные способы настройки целевых объектов, например, указание сложных значений свойств и даже использование стилей в качестве входных данных для других стилей.  Дополнительные сведения см. в разделе [Стилизация и использование шаблонов](../../../../docs/framework/wpf/controls/styling-and-templating.md).  
  
3.  **Задайте значение свойства стиля для ресурса:** Ресурсы предоставляют простой способ повторного использования часто определяемых объектов и значений.  Определение сложных значений с помощью ресурсов позволяет сделать код более удобным.  Добавьте следующую выделенную разметку в файл app.xaml.  
  
    ```  
    <Application.Resources>  
  
      <LinearGradientBrush x:Key="GrayBlueGradientBrush"   
        StartPoint="0,0" EndPoint="1,1">  
        <GradientStop Color="DarkGray" Offset="0" />  
        <GradientStop Color="#CCCCFF" Offset="0.5" />  
        <GradientStop Color="DarkGray" Offset="1" />  
      </LinearGradientBrush>  
  
      <Style TargetType="{x:Type Button}">  
        <Setter Property="Background"   
          Value="{StaticResource GrayBlueGradientBrush}" />  
        <Setter Property="Width" Value="80" />  
        <Setter Property="Margin" Value="10" />  
      </Style>  
  
    </Application.Resources>  
    ```  
  
     Непосредственно под блоком `Application.Resources` создается ресурс "GrayBlueGradientBrush".  Этот ресурс определяет горизонтальный градиент.  Этот ресурс может использоваться в качестве значения свойства из любого места в приложении, в том числе из метода задания стиля кнопки для свойства <xref:System.Windows.Controls.Control.Background%2A>.  Теперь все кнопки имеют значение свойства <xref:System.Windows.Controls.Control.Background%2A> для этого градиента.  
  
     Нажмите клавишу F5 для запуска приложения.  Код должен выглядеть следующим образом.  
  
     ![Кнопки с фоновым градиентом](../../../../docs/framework/wpf/controls/media/custom-button-animatedbutton-3.png "custom\_button\_AnimatedButton\_3")  
  
## Создание шаблона, который определяет вид элемента Button  
 В этом разделе создается шаблон, который настраивает внешний вид \(представление\) кнопки.  Представление кнопки состоит из нескольких объектов, включая прямоугольники и другие компоненты, придающих кнопке уникальный вид.  
  
 До сих пор управление видом кнопок в приложении выполнялось с помощью изменения свойств кнопки.  Что делать, если необходимо кардинально изменить внешний вид кнопки?  Шаблоны являются мощным средством управления представлением объекта.  Поскольку шаблоны можно использовать в стилях, можно применить шаблон ко всем объектам, к которым применяется стиль \(в данном руководстве — кнопка\).  
  
#### Чтобы использовать шаблон для определения внешнего вида кнопки  
  
1.  **Настройте шаблон:** поскольку элементы управления, такие как <xref:System.Windows.Controls.Button>, имеют свойство <xref:System.Windows.Controls.Control.Template%2A>, можно определить значение свойства шаблона так же, как другие значения свойств, которые были установлены в <xref:System.Windows.Style> с помощью <xref:System.Windows.Setter>.  Добавьте следующую выделенную разметку в стиль кнопки.  
  
    ```  
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
  
2.  **Измените представление кнопки:** на данном этапе необходимо определить шаблон.  Добавьте следующую выделенную разметку.  Эта разметка задает два элемента <xref:System.Windows.Shapes.Rectangle> со скругленными краями, за которыми следует <xref:System.Windows.Controls.DockPanel>.  <xref:System.Windows.Controls.DockPanel> используется для размещения <xref:System.Windows.Controls.ContentPresenter> кнопки.  <xref:System.Windows.Controls.ContentPresenter> отображает содержимое кнопки.  В данном пошаговом руководстве содержимым является текст \("Button 1", "Button 2", "Button 3"\).  Все компоненты шаблона \(прямоугольники и <xref:System.Windows.Controls.DockPanel>\) располагаются внутри элемента <xref:System.Windows.Controls.Grid>.  
  
    ```  
    <Setter.Value>  
      <ControlTemplate TargetType="Button">  
        <Grid Width="{TemplateBinding Width}"   
         Height="{TemplateBinding Height}" ClipToBounds="True">  
  
          <!-- Outer Rectangle with rounded corners. -->  
          <Rectangle x:Name="outerRectangle"   
            HorizontalAlignment="Stretch"   
            VerticalAlignment="Stretch"   
            Stroke="{TemplateBinding Background}"   
            RadiusX="20" RadiusY="20" StrokeThickness="5"   
            Fill="Transparent" />  
  
          <!-- Inner Rectangle with rounded corners. -->  
          <Rectangle x:Name="innerRectangle"   
            HorizontalAlignment="Stretch"   
            VerticalAlignment="Stretch" Stroke="Transparent"   
            StrokeThickness="20"   
            Fill="{TemplateBinding Background}"   
            RadiusX="20" RadiusY="20"   />  
  
          <!-- Present Content (text) of the button. -->  
          <DockPanel Name="myContentPresenterDockPanel">  
            <ContentPresenter x:Name="myContentPresenter" Margin="20"   
              Content="{TemplateBinding  Content}"   
              TextBlock.Foreground="Black" />  
          </DockPanel>  
        </Grid>  
      </ControlTemplate>  
    </Setter.Value>  
    ```  
  
     Нажмите клавишу F5 для запуска приложения.  Код должен выглядеть следующим образом.  
  
     ![](../../../../docs/framework/wpf/controls/media/custom-button-animatedbutton-4.gif "custom\_button\_AnimatedButton\_4")  
  
3.  **Добавьте в шаблон эффект прозрачности:** теперь предстоит добавить эффект прозрачности.  Сначала создайте ресурсы, которые создают эффект градиента прозрачности.  Добавьте эти градиентные ресурсы в любое место внутри блока `Application.Resources`:  
  
    ```  
    <Application.Resources>  
      <GradientStopCollection x:Key="MyGlassGradientStopsResource">  
        <GradientStop Color="WhiteSmoke" Offset="0.2" />  
        <GradientStop Color="Transparent" Offset="0.4" />  
        <GradientStop Color="WhiteSmoke" Offset="0.5" />  
        <GradientStop Color="Transparent" Offset="0.75" />  
        <GradientStop Color="WhiteSmoke" Offset="0.9" />  
        <GradientStop Color="Transparent" Offset="1" />  
      </GradientStopCollection>  
  
      <LinearGradientBrush x:Key="MyGlassBrushResource"   
       StartPoint="0,0" EndPoint="1,1" Opacity="0.75"   
       GradientStops="{StaticResource MyGlassGradientStopsResource}" />  
    <!-- Styles and other resources below here. -->  
    ```  
  
     Эти ресурсы используются как <xref:System.Windows.Shapes.Shape.Fill%2A> для прямоугольника, который вставляется в <xref:System.Windows.Controls.Grid> шаблона кнопки.  Добавьте следующую выделенную разметку в шаблон.  
  
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
  
          <!-- These transforms have no effect as they are declared here.   
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
    </ControlTemplate>  
    </Setter.Value>  
    ```  
  
     Обратите внимание, что <xref:System.Windows.UIElement.Opacity%2A> прямоугольника со свойством `x:Name` для "glassCube" должна быть равной 0, чтобы при запуске примера не было видно прозрачного прямоугольника.  Это необходимо выполнить, поскольку впоследствии будет происходить добавление триггеров в шаблон для взаимодействия пользователя с кнопкой.  Однако можно просмотреть, как теперь выглядит кнопка, изменив значение <xref:System.Windows.UIElement.Opacity%2A> на 1 и запустив приложение.  См. следующий рисунок.  Перед переходом к следующему действию измените <xref:System.Windows.UIElement.Opacity%2A> назад на 0.  
  
     ![Настраиваемые кнопки, созданные при помощи XAML](../../../../docs/framework/wpf/controls/media/custom-button-animatedbutton-5.png "custom\_button\_AnimatedButton\_5")  
  
## Создание интерактивной кнопки  
 В этом разделе предстоит создать триггеры свойств и триггеры событий для изменения значений свойств и запуска эффектов анимации в ответ на действия пользователя, например наведение указателя мыши на кнопку и ее нажатие.  
  
 Легкий способ сделать кнопку интерактивной \(при наведении указателя мыши на кнопку, выходе указателя мыши за границы кнопки, щелчке кнопки мыши и т. д.\) является определение триггеров в шаблоне или стиле.  Чтобы создать <xref:System.Windows.Trigger>, определите "условие" для свойства, например: значение свойства <xref:System.Windows.UIElement.IsMouseOver%2A> кнопки равно `true`.  Затем предстоит определить элементы Setter \(действия\), которые выполняются, если условия триггера удовлетворяются.  
  
#### Чтобы создать интерактивную кнопку  
  
1.  **Добавьте триггеры шаблона:** добавьте выделенную разметку в шаблон.  
  
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
  
        <ControlTemplate.Triggers>  
          <!-- Set action triggers for the buttons and define  
               what the button does in response to those triggers. -->  
        </ControlTemplate.Triggers>  
      </ControlTemplate>  
    </Setter.Value>  
    ```  
  
2.  **Добавьте триггеры свойств:** добавьте выделенную разметку в блок `ControlTemplate.Triggers`.  
  
    ```  
    <ControlTemplate.Triggers>  
  
      <!-- Set properties when mouse pointer is over the button. -->  
      <Trigger Property="IsMouseOver" Value="True">  
  
        <!-- Below are three property settings that occur when the   
             condition is met (user mouses over button).  -->  
        <!-- Change the color of the outer rectangle when user   
             mouses over it. -->  
        <Setter Property ="Rectangle.Stroke" TargetName="outerRectangle"  
          Value="{DynamicResource {x:Static SystemColors.HighlightBrushKey}}" />  
  
        <!-- Sets the glass opacity to 1, therefore, the   
             glass "appears" when user mouses over it. -->  
        <Setter Property="Rectangle.Opacity" Value="1" TargetName="glassCube" />  
  
        <!-- Makes the text slightly blurry as though you   
             were looking at it through blurry glass. -->  
        <Setter Property="ContentPresenter.BitmapEffect"   
          TargetName="myContentPresenter">  
          <Setter.Value>  
            <BlurBitmapEffect Radius="1" />  
          </Setter.Value>  
        </Setter>  
      </Trigger>  
  
    <ControlTemplate.Triggers/>  
    ```  
  
     Нажмите клавишу F5, чтобы запустить приложение и увидеть эффект при наведении указателя мыши на кнопку.  
  
3.  **Добавьте триггер фокуса:** теперь будут добавлены некоторые аналогичные элементы Setter для обработки в случае, когда кнопка имеет фокус \(например, после того как пользователь нажмет ее\).  
  
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
      <!-- Set properties when button has focus. -->  
      <Trigger Property="IsFocused" Value="true">  
        <Setter Property="Rectangle.Opacity" Value="1"       TargetName="glassCube" />  
        <Setter Property="Rectangle.Stroke" TargetName="outerRectangle"  
          Value="{DynamicResource {x:Static SystemColors.HighlightBrushKey}}" />  
        <Setter Property="Rectangle.Opacity" Value="1" TargetName="glassCube" />  
      </Trigger>  
  
    </ControlTemplate.Triggers>  
    ```  
  
     Нажмите клавишу F5, чтобы запустить приложение, а затем нажмите одну из кнопок.  Обратите внимание, что кнопка остается выделенной после нажатия, поскольку она по\-прежнему имеет фокус.  При нажатии другой кнопки новая кнопка получает фокус, в то время как предыдущая его утрачивает.  
  
4.  **Добавьте анимацию для**  <xref:System.Windows.UIElement.MouseEnter>  **и**  <xref:System.Windows.UIElement.MouseLeave> **:**. Далее будет добавлена анимация к триггерам.  Добавьте следующую разметку в любое место в блоке `ControlTemplate.Triggers`.  
  
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
  
     Прозрачный прямоугольник уменьшается, когда указатель мыши наведен на кнопку, и возвращается в исходное состояние, при выходе указателя мыши за границы кнопки.  
  
     Существуют две анимации, которые запускаются при наведении указателя мыши на кнопку \(вызывается событие <xref:System.Windows.UIElement.MouseEnter>\).  Эти анимации сжимают прозрачный прямоугольник вдоль осей X и Y.  Обратите внимание на элементы <xref:System.Windows.Media.Animation.DoubleAnimation> — <xref:System.Windows.Media.Animation.Timeline.Duration%2A> и <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>.  <xref:System.Windows.Media.Animation.Timeline.Duration%2A> указывает, что анимация возникает через полсекунды, а <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> указывает, что прозрачный элемент сжимается на 10 %.  
  
     Триггер второго события \(<xref:System.Windows.UIElement.MouseLeave>\) просто останавливает первое из них.  При остановке <xref:System.Windows.Media.Animation.Storyboard> все анимированные свойства возвращаются в значения по умолчанию.  Поэтому когда пользователь перемещает указатель мыши за границы кнопки, кнопка возвращается в состояние, которое было до наведения указателя мыши на нее.  Дополнительные сведения об анимации см. в разделе [Общие сведения об эффектах анимации](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).  
  
5.  **Добавьте анимацию при нажатии кнопки:** последним действием является добавление триггера для события, которое происходит, когда пользователь нажимает кнопку.  Добавьте следующую разметку в любое место в блоке `ControlTemplate.Triggers`.  
  
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
  
     Нажмите клавишу F5, чтобы запустить приложение, а затем нажмите одну из кнопок.  При нажатии кнопки прозрачный прямоугольник начинает вращаться.  
  
## Сводка  
 В данном пошаговом руководстве были выполнены следующие упражнения:  
  
-   Привязка <xref:System.Windows.Style> к типу объекта \(<xref:System.Windows.Controls.Button>\).  
  
-   Управление основными свойствами кнопок во всем приложении с помощью <xref:System.Windows.Style>.  
  
-   Создание ресурсов, таких как градиенты, для использования в качестве значений свойств для методов установки <xref:System.Windows.Style>.  
  
-   Настройка внешнего вида кнопок во всем приложении с помощью применения к кнопкам шаблона.  
  
-   Настройка поведения для кнопок в ответ на действия пользователя \(такие как <xref:System.Windows.UIElement.MouseEnter>, <xref:System.Windows.UIElement.MouseLeave> и <xref:System.Windows.Controls.Primitives.ButtonBase.Click>\), которые включают эффекты анимации.  
  
## См. также  
 [Создание кнопки с помощью Microsoft Expression Blend](../../../../docs/framework/wpf/controls/walkthrough-create-a-button-by-using-microsoft-expression-blend.md)   
 [Стилизация и использование шаблонов](../../../../docs/framework/wpf/controls/styling-and-templating.md)   
 [Общие сведения об эффектах анимации](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)   
 [Общие сведения о закраске сплошным цветом и градиентом](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)   
 [Общие сведения об эффектах для точечных рисунков](../../../../docs/framework/wpf/graphics-multimedia/bitmap-effects-overview.md)