---
title: Исходный код L2DBForm.xaml
ms.date: 10/22/2019
ms.topic: sample
ms.openlocfilehash: 290b00e136f0c49e1b27d4fa1bca7321eebe936e
ms.sourcegitcommit: 82f94a44ad5c64a399df2a03fa842db308185a76
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2019
ms.locfileid: "72921230"
---
# <a name="l2dbformxaml-source-code"></a><span data-ttu-id="b5d3e-102">Исходный код L2DBForm.xaml</span><span class="sxs-lookup"><span data-stu-id="b5d3e-102">L2DBForm.xaml source code</span></span>

<span data-ttu-id="b5d3e-103">На этой странице содержится и описывается исходный файл XAML для [привязки данных WPF с помощью LINQ to XML примере](linq-to-xml-data-binding-sample.md).</span><span class="sxs-lookup"><span data-stu-id="b5d3e-103">This page contains and describes the XAML source file for the [WPF data binding using LINQ to XML example](linq-to-xml-data-binding-sample.md).</span></span>

## <a name="overall-ui-structure"></a><span data-ttu-id="b5d3e-104">Общая структура пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="b5d3e-104">Overall UI structure</span></span>

<span data-ttu-id="b5d3e-105">Как типично для проекта WPF, этот файл содержит один родительский элемент — <xref:System.Windows.Window> элемент XML, связанный с производным классом `L2XDBFrom` в пространстве имен `LinqToXmlDataBinding`.</span><span class="sxs-lookup"><span data-stu-id="b5d3e-105">As is typical for a WPF project, this file contains one parent element, a <xref:System.Windows.Window> XML element that's associated with the derived class `L2XDBFrom` in the `LinqToXmlDataBinding` namespace.</span></span>

<span data-ttu-id="b5d3e-106">Клиентская область содержится в <xref:System.Windows.Controls.StackPanel>, для которой задан светло-синий фон.</span><span class="sxs-lookup"><span data-stu-id="b5d3e-106">The client area is contained within a <xref:System.Windows.Controls.StackPanel> that's given a light blue background.</span></span> <span data-ttu-id="b5d3e-107">Эта панель содержит четыре раздела пользовательского интерфейса <xref:System.Windows.Controls.DockPanel> , разделенные панелями <xref:System.Windows.Controls.Separator> .</span><span class="sxs-lookup"><span data-stu-id="b5d3e-107">This panel contains four <xref:System.Windows.Controls.DockPanel> UI sections separated by <xref:System.Windows.Controls.Separator> bars.</span></span> <span data-ttu-id="b5d3e-108">Цель этих разделов описана [здесь](linq-to-xml-data-binding-sample.md#overview).</span><span class="sxs-lookup"><span data-stu-id="b5d3e-108">The purpose of these sections is described [here](linq-to-xml-data-binding-sample.md#overview).</span></span>

<span data-ttu-id="b5d3e-109">Каждый раздел содержит идентифицирующую его метку.</span><span class="sxs-lookup"><span data-stu-id="b5d3e-109">Each section contains a label that identifies it.</span></span> <span data-ttu-id="b5d3e-110">В двух первых разделах данная метка повернута на 90 градусов с помощью <xref:System.Windows.FrameworkElement.LayoutTransform%2A>.</span><span class="sxs-lookup"><span data-stu-id="b5d3e-110">In the first two sections, this label is rotated 90 degrees through the use of a <xref:System.Windows.FrameworkElement.LayoutTransform%2A>.</span></span> <span data-ttu-id="b5d3e-111">Оставшаяся часть раздела содержит элементы пользовательского интерфейса, соответствующие назначению этого раздела, например текстовые блоки, текстовые поля и кнопки.</span><span class="sxs-lookup"><span data-stu-id="b5d3e-111">The rest of the section contains UI elements appropriate to the purpose of that section, for example, text blocks, text boxes, and buttons.</span></span> <span data-ttu-id="b5d3e-112">Иногда для выравнивания этих дочерних элементов управления используется дочерний элемент <xref:System.Windows.Controls.StackPanel> .</span><span class="sxs-lookup"><span data-stu-id="b5d3e-112">Sometimes a child <xref:System.Windows.Controls.StackPanel> is used to align these child controls.</span></span>

## <a name="window-resource-section"></a><span data-ttu-id="b5d3e-113">Раздел оконных ресурсов</span><span class="sxs-lookup"><span data-stu-id="b5d3e-113">Window resource section</span></span>

<span data-ttu-id="b5d3e-114">Открывающий тег `<Window.Resources>` в строке 9 определяет начало раздела оконных ресурсов.</span><span class="sxs-lookup"><span data-stu-id="b5d3e-114">The opening `<Window.Resources>` tag on line 9 indicates the start of the window resource section.</span></span> <span data-ttu-id="b5d3e-115">Он оканчивается закрывающим тегом в строке 35.</span><span class="sxs-lookup"><span data-stu-id="b5d3e-115">It ends with the closing tag on line 35.</span></span>

<span data-ttu-id="b5d3e-116">В теге `<ObjectDataProvider>` , который охватывает строки с 11 по 25, объявляется поставщик <xref:System.Windows.Data.ObjectDataProvider>с именем `LoadedBooks`, использующий в качестве источника <xref:System.Xml.Linq.XElement> .</span><span class="sxs-lookup"><span data-stu-id="b5d3e-116">The `<ObjectDataProvider>` tag, which spans lines 11 through 25, declares a <xref:System.Windows.Data.ObjectDataProvider>, named `LoadedBooks`, that uses an <xref:System.Xml.Linq.XElement> as the source.</span></span> <span data-ttu-id="b5d3e-117">Объект <xref:System.Xml.Linq.XElement> инициализируется путем синтаксического анализа XML-документа (элемент `CDATA`).</span><span class="sxs-lookup"><span data-stu-id="b5d3e-117">The <xref:System.Xml.Linq.XElement> is initialized by parsing an embedded XML document (a `CDATA` element).</span></span> <span data-ttu-id="b5d3e-118">Обратите внимание, что пробелы сохраняются при объявлении внедренного XML-документа, а также при его анализе.</span><span class="sxs-lookup"><span data-stu-id="b5d3e-118">Notice that white space is preserved when declaring the embedded XML document and also when it's parsed.</span></span> <span data-ttu-id="b5d3e-119">Это связано с тем, что в элементе управления <xref:System.Windows.Controls.TextBlock>, используемом для отображения необработанного кода XML, не предусмотрены специальные возможности форматирования XML.</span><span class="sxs-lookup"><span data-stu-id="b5d3e-119">White space is preserved because the <xref:System.Windows.Controls.TextBlock> control, which is used to display the raw XML, has no special XML formatting capabilities.</span></span>

<span data-ttu-id="b5d3e-120">Наконец, в строках с 28 по 34 определен шаблон <xref:System.Windows.DataTemplate> под именем `BookTemplate` .</span><span class="sxs-lookup"><span data-stu-id="b5d3e-120">Lastly, a <xref:System.Windows.DataTemplate> named `BookTemplate` is defined on lines 28 through 34.</span></span> <span data-ttu-id="b5d3e-121">Он предназначен для отображения записей в разделе пользовательского интерфейса **Список книг**.</span><span class="sxs-lookup"><span data-stu-id="b5d3e-121">This template is used to display the entries in the **Book List** UI section.</span></span> <span data-ttu-id="b5d3e-122">В нем используются привязка данных и динамические свойства LINQ to XML для получения идентификатора книги с помощью следующих присваиваний.</span><span class="sxs-lookup"><span data-stu-id="b5d3e-122">It uses data binding and LINQ to XML dynamic properties to retrieve the book ID and book name through the following assignments:</span></span>

```xaml
Text="{Binding Path=Attribute[id].Value}"Text="{Binding Path=Value}"
```

## <a name="data-binding-code"></a><span data-ttu-id="b5d3e-123">Код привязки данных</span><span class="sxs-lookup"><span data-stu-id="b5d3e-123">Data binding code</span></span>

<span data-ttu-id="b5d3e-124">Кроме элемента <xref:System.Windows.DataTemplate> , привязка данных используется во многих других местах данного файла.</span><span class="sxs-lookup"><span data-stu-id="b5d3e-124">In addition to the <xref:System.Windows.DataTemplate> element, data binding is used in a number of other places in this file.</span></span>

<span data-ttu-id="b5d3e-125">В открывающем теге `<StackPanel>` в строке 38 свойство данной панели <xref:System.Windows.FrameworkElement.DataContext%2A> устанавливается на поставщика данных `LoadedBooks` .</span><span class="sxs-lookup"><span data-stu-id="b5d3e-125">In the opening `<StackPanel>` tag on line 38, the <xref:System.Windows.FrameworkElement.DataContext%2A> property of this panel is set to the `LoadedBooks` data provider.</span></span>

```xaml
DataContext="{Binding Source={StaticResource LoadedBooks}}
```

<span data-ttu-id="b5d3e-126">Задание контекста данных позволяет элементу <xref:System.Windows.Controls.TextBlock> с именем `tbRawXml` (в строке 46) отображать необработанный код XML путем привязки к свойству `Xml` этого поставщика данных.</span><span class="sxs-lookup"><span data-stu-id="b5d3e-126">Setting the data context makes it possible (on line 46) for the <xref:System.Windows.Controls.TextBlock> named `tbRawXml` to display the raw XML by binding to this data provider's `Xml` property:</span></span>

```xaml
Text="{Binding Path=Xml}"
```

<span data-ttu-id="b5d3e-127">Объект <xref:System.Windows.Controls.ListBox> в разделе интерфейса **Список книг** задает в строках с 58 по 62 для своих отображаемых элементов шаблон `BookTemplate` , определенный в разделе ресурсов окна.</span><span class="sxs-lookup"><span data-stu-id="b5d3e-127">The <xref:System.Windows.Controls.ListBox> in the **Book List** UI section, on lines 58 through 62, sets the template for its display items to the `BookTemplate` defined in the window resource section:</span></span>

```xaml
ItemTemplate ="{StaticResource BookTemplate}"
```

<span data-ttu-id="b5d3e-128">Затем в строках с 59 по 62 действительные значения книг привязываются к данному списку.</span><span class="sxs-lookup"><span data-stu-id="b5d3e-128">Then, on lines 59 through 62, the actual values of the books are bound to this list box:</span></span>

```xaml
<ListBox.ItemsSource>
    <Binding Path="Elements[{http://www.mybooks.com}book]"/>
</ListBox.ItemsSource>
```

<span data-ttu-id="b5d3e-129">В третьем разделе интерфейса, **Редактировать выбранную книгу**, сначала происходит привязка свойства <xref:System.Windows.FrameworkElement.DataContext%2A> дочернего элемента <xref:System.Windows.Controls.StackPanel> к текущему элементу, выбранному из раздела пользовательского интерфейса **Список книг** (строка 82).</span><span class="sxs-lookup"><span data-stu-id="b5d3e-129">The third UI section, **Edit Selected Book**, first binds the <xref:System.Windows.FrameworkElement.DataContext%2A> of the parent <xref:System.Windows.Controls.StackPanel> to the currently selected item in from the **Book List** UI section (line 82):</span></span>

```xaml
DataContext="{Binding ElementName=lbBooks, Path=SelectedItem}"
```

<span data-ttu-id="b5d3e-130">Затем в нем используется двусторонняя привязка данных, что позволяет отображать и обновлять текущие значения элементов книги с помощью двух текстовых полей данной панели.</span><span class="sxs-lookup"><span data-stu-id="b5d3e-130">It then uses two-way data binding, so that the current values of the book elements are displayed to, and updated from, the two text boxes in this panel.</span></span> <span data-ttu-id="b5d3e-131">Привязка данных к динамическим свойствам аналогична используемой в шаблоне данных `BookTemplate`:</span><span class="sxs-lookup"><span data-stu-id="b5d3e-131">Data binding to dynamic properties is similar to the data binding used in the `BookTemplate` data template:</span></span>

```xaml
Text="{Binding Path=Attribute[id].Value}"...Text="{Binding Path=Value}"
```

<span data-ttu-id="b5d3e-132">В коде XAML последнего раздела пользовательского интерфейса (**Добавление новой книги**) привязка к данным не используется.</span><span class="sxs-lookup"><span data-stu-id="b5d3e-132">The last UI section, **Add New Book**, doesn't use data binding in its XAML code.</span></span> <span data-ttu-id="b5d3e-133">Вместо этого привязка данных применяется в коде обработки событий в файле *L2DBForm.xaml.cs*.</span><span class="sxs-lookup"><span data-stu-id="b5d3e-133">Instead, data binding is in its event handling code in the file *L2DBForm.xaml.cs*.</span></span>

## <a name="example"></a><span data-ttu-id="b5d3e-134">Пример</span><span class="sxs-lookup"><span data-stu-id="b5d3e-134">Example</span></span>

### <a name="description"></a><span data-ttu-id="b5d3e-135">Описание</span><span class="sxs-lookup"><span data-stu-id="b5d3e-135">Description</span></span>

> [!NOTE]
> <span data-ttu-id="b5d3e-136">Рекомендуется скопировать расположенный ниже код в редактор кода, например редактор исходного кода C# в Visual Studio, чтобы было легче отслеживать номера строк.</span><span class="sxs-lookup"><span data-stu-id="b5d3e-136">We recommend that you copy the following code below into a code editor, such as the C# source code editor in Visual Studio, so that line numbers will be easier to track.</span></span>

### <a name="code"></a><span data-ttu-id="b5d3e-137">Код</span><span class="sxs-lookup"><span data-stu-id="b5d3e-137">Code</span></span>

```xml
<Window x:Class="LinqToXmlDataBinding.L2XDBForm"
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
    xmlns:system="clr-namespace:System;assembly=mscorlib"
    xmlns:xlinq="clr-namespace:System.Xml.Linq;assembly=System.Xml.Linq"
    xmlns:local="clr-namespace:LinqToXmlDataBinding"
    Title="WPF Data Binding using LINQ-to-XML" Height="665" Width="500" ResizeMode="NoResize">

    <Window.Resources>
        <!-- Books provider and inline data -->
        <ObjectDataProvider x:Key="LoadedBooks" ObjectType="{x:Type xlinq:XElement}" MethodName="Parse">
            <ObjectDataProvider.MethodParameters>
                <system:String xml:space="preserve">
<![CDATA[
<books xmlns="http://www.mybooks.com">
  <book id="0">book zero</book>
  <book id="1">book one</book>
  <book id="2">book two</book>
  <book id="3">book three</book>
</books>
]]>
                </system:String>
                <xlinq:LoadOptions>PreserveWhitespace</xlinq:LoadOptions>
            </ObjectDataProvider.MethodParameters>
        </ObjectDataProvider>

        <!-- Template for use in Books List listbox. -->
        <DataTemplate x:Key="BookTemplate">
            <StackPanel Orientation="Horizontal">
                <TextBlock Margin="3" Text="{Binding Path=Attribute[id].Value}"/>
                <TextBlock Margin="3" Text="-"/>
                <TextBlock Margin="3" Text="{Binding Path=Value}"/>
            </StackPanel>
        </DataTemplate>
    </Window.Resources>

    <!-- Main visual content container -->
    <StackPanel Background="lightblue" DataContext="{Binding Source={StaticResource LoadedBooks}}">
        <!-- Raw XML display section -->
        <DockPanel Margin="5">
            <Label  Background="Gray" FontSize="12" BorderBrush="Black" BorderThickness="1" FontWeight="Bold">XML
            <Label.LayoutTransform>
                <RotateTransform Angle="90"/>
            </Label.LayoutTransform>
            </Label>
            <TextBlock Name="tbRawXml" Height="200" Background="LightGray" Text="{Binding Path=Xml}" TextTrimming="CharacterEllipsis" />
        </DockPanel>

        <Separator Height="4" Margin="5" />

        <!-- List box to display all books section -->
        <DockPanel Margin="5">
            <Label  Background="Gray" FontSize="12" BorderBrush="Black" BorderThickness="1" FontWeight="Bold">Book List
                <Label.LayoutTransform>
                    <RotateTransform Angle="90"/>
                </Label.LayoutTransform>
            </Label>
            <ListBox Name="lbBooks" Height="200" Width="415" ItemTemplate ="{StaticResource BookTemplate}">
                <ListBox.ItemsSource>
                    <Binding Path="Elements[{http://www.mybooks.com}book]"/>
                </ListBox.ItemsSource>
            </ListBox>
            <Button Margin="5" DockPanel.Dock="Right" Height="30" Width ="130" Content="Remove Selected Book" Click="OnRemoveBook">
            <Button.LayoutTransform>
                <RotateTransform Angle="90"/>
            </Button.LayoutTransform>
            </Button>
        </DockPanel>

        <Separator Height="4" Margin="5" />

        <!-- Edit current selection section -->
        <DockPanel Margin="5">
            <TextBlock Margin="5" Height="30" Width="65" DockPanel.Dock="Right" Background="LightGray" TextWrapping="Wrap" TextAlignment="Center">
                    Changes are live!
                <TextBlock.LayoutTransform>
                    <RotateTransform Angle="90"/>
                </TextBlock.LayoutTransform>
            </TextBlock>
            <StackPanel>
                <Label Width="450" Background="Gray" FontSize="12" BorderBrush="Black" BorderThickness="1" HorizontalAlignment="Left" FontWeight="Bold">Edit Selected Book</Label>
                <StackPanel Margin="1" DataContext="{Binding ElementName=lbBooks, Path=SelectedItem}">
                    <StackPanel Orientation="Horizontal">
                        <Label Width="40">ID:</Label>
                        <TextBox Name="editAttributeTextBox" Width="410" Text="{Binding Path=Attribute[id].Value}">
                            <TextBox.ToolTip>
                                <TextBlock FontWeight="Bold" TextAlignment="Center">
                                    <Label>Edit the selected book ID and see it changed.</Label>
                                </TextBlock>
                            </TextBox.ToolTip>
                        </TextBox>
                    </StackPanel>
                    <StackPanel Orientation="Horizontal">
                        <Label Width="40">Value:</Label>
                        <TextBox Name="editValueTextBox" Width="410" Text="{Binding Path=Value}" Height="25">
                            <TextBox.ToolTip>
                                <TextBlock FontWeight="Bold" TextAlignment="Center">
                                    <Label>Edit the selected book Value and see it changed.</Label>
                                </TextBlock>
                            </TextBox.ToolTip>
                        </TextBox>
                    </StackPanel>
                </StackPanel>
            </StackPanel>
        </DockPanel>

        <Separator Height="4" Margin="5" />

        <!-- Add new book section -->
        <DockPanel Margin="5">
            <Button Margin="5" Height="30" DockPanel.Dock="Right" Click ="OnAddBook">Add Book
                <Button.LayoutTransform>
                    <RotateTransform Angle="90"/>
                </Button.LayoutTransform>
            </Button>
            <StackPanel>
                <Label Width="450" Background="Gray" FontSize="12" BorderBrush="Black" BorderThickness="1" HorizontalAlignment="Left" FontWeight="Bold">Add New Book</Label>
                <StackPanel Margin="1">
                    <StackPanel Orientation="Horizontal">
                        <Label Width="40">ID:</Label>
                        <TextBox Name="tbAddID" Width="410">
                            <TextBox.ToolTip>
                                <TextBlock FontWeight="Bold" TextAlignment="Center">
                                    <Label>Enter a book ID and Value pair, then click Add Book.</Label>
                                </TextBlock>
                            </TextBox.ToolTip>
                        </TextBox>
                    </StackPanel>
                    <StackPanel Orientation="Horizontal">
                        <Label Width="40">Value:</Label>
                        <TextBox Name="tbAddValue" Width="410" Height="25">
                            <TextBox.ToolTip>
                                <TextBlock FontWeight="UltraBold" TextAlignment="Center">
                                    <Label>Enter a book ID and Value pair, then click Add Book.</Label>
                                </TextBlock>
                            </TextBox.ToolTip>
                        </TextBox>
                    </StackPanel>
                </StackPanel>
            </StackPanel>
        </DockPanel>
    </StackPanel>
</Window>
```

### <a name="comments"></a><span data-ttu-id="b5d3e-138">Комментарии</span><span class="sxs-lookup"><span data-stu-id="b5d3e-138">Comments</span></span>

<span data-ttu-id="b5d3e-139">Сведения об исходном коде C# для обработчиков событий, связанных с элементами интерфейса WPF, см. в разделе [Исходный код L2DBForm.xaml.cs](l2dbform-xaml-cs-source-code.md).</span><span class="sxs-lookup"><span data-stu-id="b5d3e-139">For the C# source code for the event handlers associated with the WPF UI elements, see [L2DBForm.xaml.cs source code](l2dbform-xaml-cs-source-code.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="b5d3e-140">См. также</span><span class="sxs-lookup"><span data-stu-id="b5d3e-140">See also</span></span>

- [<span data-ttu-id="b5d3e-141">Пошаговое руководство. Пример LinqToXmlDataBinding</span><span class="sxs-lookup"><span data-stu-id="b5d3e-141">Walkthrough: LinqToXmlDataBinding example</span></span>](linq-to-xml-data-binding-sample.md)
- [<span data-ttu-id="b5d3e-142">Исходный код L2DBForm.xaml.cs</span><span class="sxs-lookup"><span data-stu-id="b5d3e-142">L2DBForm.xaml.cs source code</span></span>](l2dbform-xaml-cs-source-code.md)
