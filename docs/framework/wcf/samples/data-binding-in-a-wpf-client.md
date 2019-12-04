---
title: Привязка данных в клиенте Windows Presentation Foundation
ms.date: 03/30/2017
ms.assetid: bb8c8293-5973-4aef-9b07-afeff5d3293c
ms.openlocfilehash: 44a208cf081ef00396dfc874349dff57363c0df3
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74715396"
---
# <a name="data-binding-in-a-windows-presentation-foundation-client"></a><span data-ttu-id="40e0b-102">Привязка данных в клиенте Windows Presentation Foundation</span><span class="sxs-lookup"><span data-stu-id="40e0b-102">Data Binding in a Windows Presentation Foundation Client</span></span>
<span data-ttu-id="40e0b-103">Этот образец демонстрирует использование привязки данных в клиенте Windows Presentation Foundation (WPF).</span><span class="sxs-lookup"><span data-stu-id="40e0b-103">This sample demonstrates the use of data binding in a Windows Presentation Foundation (WPF) client.</span></span> <span data-ttu-id="40e0b-104">В примере используется служба Windows Communication Foundation (WCF), которая случайным образом создает массив альбомов для возврата клиенту.</span><span class="sxs-lookup"><span data-stu-id="40e0b-104">The sample uses a Windows Communication Foundation (WCF) service that randomly generates an array of albums to return to the client.</span></span> <span data-ttu-id="40e0b-105">Каждый альбом имеет имя, цену и список дорожек в альбоме.</span><span class="sxs-lookup"><span data-stu-id="40e0b-105">Each album has a name, a price, and a list of album tracks.</span></span> <span data-ttu-id="40e0b-106">Каждая дорожка в альбоме имеет имя и длительность.</span><span class="sxs-lookup"><span data-stu-id="40e0b-106">The album tracks have a name and duration.</span></span> <span data-ttu-id="40e0b-107">Сведения, возвращаемые службой, автоматически привязываются к пользовательскому интерфейсу, предоставленному клиентом Windows Presentation Foundation (WPF).</span><span class="sxs-lookup"><span data-stu-id="40e0b-107">The information that is returned by the service is automatically bound to the user interface (UI) provided by the Windows Presentation Foundation (WPF) client.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="40e0b-108">Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.</span><span class="sxs-lookup"><span data-stu-id="40e0b-108">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="40e0b-109">Привязка данных позволяет автоматически привязывать источник данных к пользовательскому интерфейсу.</span><span class="sxs-lookup"><span data-stu-id="40e0b-109">Data binding allows a data source to be automatically bound to a UI.</span></span> <span data-ttu-id="40e0b-110">Это упрощает модель программирования, устраняя необходимость программным способом обновлять каждый элемент пользовательского интерфейса данными из объекта данных или массива объектов данных.</span><span class="sxs-lookup"><span data-stu-id="40e0b-110">This simplifies the programming model because it does not require that you programmatically update each UI element with the data from a data object or an array of data objects.</span></span> <span data-ttu-id="40e0b-111">Можно как привязать объект к одному элементу пользовательского интерфейса, так и привязать массив к элементу управления, принимающему несколько входных объектов, такому как `ListBox`.</span><span class="sxs-lookup"><span data-stu-id="40e0b-111">You can bind an object to a single UI element or an array to a control that takes multiple inputs, such as a `ListBox`.</span></span> <span data-ttu-id="40e0b-112">В следующем примере кода показана привязка данных к контексту данных (`DataContext`) элемента пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="40e0b-112">The following code shows how to bind data to the `DataContext` of a UI element.</span></span>  
  
```csharp  
// Event handler executed when call is complete  
void client_GetAlbumListCompleted(object sender, GetAlbumListCompletedEventArgs e)  
{  
    // This is on the UI thread, myPanel can be accessed directly  
    myPanel.DataContext = e.Result;   
}  
```  
  
 <span data-ttu-id="40e0b-113">В предыдущем образце `DataContext` для элемента макета `grid` с именем `myPanel` получает в качестве значения данные, возвращаемые методом `GetAlbumList`.</span><span class="sxs-lookup"><span data-stu-id="40e0b-113">In the previous sample, the `DataContext` for the `grid` layout element named `myPanel` is set to the data returned by the `GetAlbumList` method.</span></span> <span data-ttu-id="40e0b-114">`DataContext` позволяет элементам наследовать от своих родительских элементов информацию об источнике данных, используемом для привязки, а также другие характеристики привязки, например путь.</span><span class="sxs-lookup"><span data-stu-id="40e0b-114">The `DataContext` allows elements to inherit information from their parent elements about the data source that is used for binding, as well as other characteristics of the binding such as the path.</span></span> <span data-ttu-id="40e0b-115">Эта строка кода должна выполняться при каждом обновлении данных на сервере.</span><span class="sxs-lookup"><span data-stu-id="40e0b-115">The line of code must be executed every time the data on the server is updated.</span></span> <span data-ttu-id="40e0b-116">Например, она выполняется при инициализации окна и при добавлении нового альбома.</span><span class="sxs-lookup"><span data-stu-id="40e0b-116">For example, it is executed when the window is initialized and when a new album is added.</span></span>  
  
 <span data-ttu-id="40e0b-117">В следующем примере XAML-кода для элемента `ListBox` задано, что `ItemsSource="{Binding }"`.</span><span class="sxs-lookup"><span data-stu-id="40e0b-117">In the following sample XAML code, the `ListBox` specifies `ItemsSource="{Binding }"`.</span></span>  
  
```xml  
<ListBox   
          ItemTemplate="{StaticResource AlbumStyle}"  
          ItemsSource="{Binding }"   
          IsSynchronizedWithCurrentItem="true" />  
```  
  
 <span data-ttu-id="40e0b-118">Это указывает, что данные, привязываемые к элементу пользовательского интерфейса верхнего уровня, привязываются также к этому элементу управления (т. е. массиву альбомов).</span><span class="sxs-lookup"><span data-stu-id="40e0b-118">This specifies that the data bound to the top-level UI element is also bound to this control (that is, the array of Albums).</span></span> <span data-ttu-id="40e0b-119">Кроме того, инструкция `ItemTemplate="{StaticResource AlbumStyle}"` задает шаблон данных, который должен использоваться для каждого элемента в `ListBox`.</span><span class="sxs-lookup"><span data-stu-id="40e0b-119">In addition, `ItemTemplate="{StaticResource AlbumStyle}"` specifies the data template to be used for each item in the `ListBox`.</span></span> <span data-ttu-id="40e0b-120">Можно также определять шаблоны данных для задания способа форматирования данных.</span><span class="sxs-lookup"><span data-stu-id="40e0b-120">You can also define data templates to specify how the data should be formatted.</span></span> <span data-ttu-id="40e0b-121">Эти шаблоны данных можно использовать повторно - для других элементов пользовательского интерфейса в приложении, с тем преимуществом, что шаблон определяется и хранится в одном месте.</span><span class="sxs-lookup"><span data-stu-id="40e0b-121">These data templates can be reused for other UI elements in the application, the advantage is that the data template is defined and maintained in one place.</span></span>  
  
 <span data-ttu-id="40e0b-122">Шаблон данных `AlbumStyle` создает сетку, состоящую из двух расположенных бок о бок элементов `TextBlock`.</span><span class="sxs-lookup"><span data-stu-id="40e0b-122">The `AlbumStyle` data template lays out a grid with two `TextBlock`s side by side.</span></span> <span data-ttu-id="40e0b-123">В одном блоке текста указывается название альбома, а в другом количество дорожек в альбоме.</span><span class="sxs-lookup"><span data-stu-id="40e0b-123">One specifies the name of the Album and the other the number of Tracks in the album.</span></span>  
  
```xaml  
<DataTemplate x:Key="AlbumStyle">  
    <Grid>  
        <Grid.ColumnDefinitions>  
            <ColumnDefinition Width="260" />  
            <ColumnDefinition Width="60" />  
        </Grid.ColumnDefinitions>  
        <TextBlock Grid.Column="0" TextContent="{Binding Path=Title}" />  
        <TextBlock Grid.Column="1" TextContent="{Binding Path=Tracks#.Count}" HorizontalAlignment="Right" />  
    </Grid>  
</DataTemplate>  
```  
  
 <span data-ttu-id="40e0b-124">Следующий XAML-код создает второй `ListBox`.</span><span class="sxs-lookup"><span data-stu-id="40e0b-124">The following XAML code creates a second `ListBox`.</span></span>  
  
```xaml  
<ListBox Grid.Row="2"   
            Grid.ColumnSpan="2"   
            ItemTemplate="{StaticResource TrackStyle}"  
            ItemsSource="{Binding Path=Tracks}" />  
```  
  
 <span data-ttu-id="40e0b-125">В коде задан путь к объекту `ItemsSource`.</span><span class="sxs-lookup"><span data-stu-id="40e0b-125">The code specifies a path for the `ItemsSource`.</span></span> <span data-ttu-id="40e0b-126">Это означает, что данные, привязываемые к этому элементу управления, являются не данными верхнего уровня, а свойством данных верхнего уровня с именем `Tracks`.</span><span class="sxs-lookup"><span data-stu-id="40e0b-126">This indicates that the data bound to this control is not the top-level data but a property of the top-level data named `Tracks`.</span></span> <span data-ttu-id="40e0b-127">Это свойство представляет собой массив дорожек, содержащихся в альбоме.</span><span class="sxs-lookup"><span data-stu-id="40e0b-127">This property represents the array of tracks contained within the album.</span></span> <span data-ttu-id="40e0b-128">Кроме того, задан другой шаблон данных `DataTemplate` с именем `TrackStyle`.</span><span class="sxs-lookup"><span data-stu-id="40e0b-128">In addition, a different `DataTemplate` named `TrackStyle` is specified.</span></span> <span data-ttu-id="40e0b-129">Макет, создаваемый шаблоном `TrackStyle`, аналогичен макету шаблона `AlbumStyle`, однако элементы `TextBlock` привязаны к другим свойствам.</span><span class="sxs-lookup"><span data-stu-id="40e0b-129">The layout of the `TrackStyle` template is similar to that of the `AlbumStyle` template, but the `TextBlock`s are bound to different properties.</span></span> <span data-ttu-id="40e0b-130">Это связано с тем, что шаблоны используются для разных объектов данных.</span><span class="sxs-lookup"><span data-stu-id="40e0b-130">This is because the two templates are used with different data objects.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="40e0b-131">Настройка, сборка и выполнение образца</span><span class="sxs-lookup"><span data-stu-id="40e0b-131">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="40e0b-132">Убедитесь, что вы выполнили [однократную процедуру настройки для Windows Communication Foundation примеров](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="40e0b-132">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="40e0b-133">Чтобы создать выпуск решения на языке C# или Visual Basic .NET, следуйте инструкциям в разделе [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="40e0b-133">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="40e0b-134">Чтобы запустить пример в конфигурации с одним или несколькими компьютерами, следуйте инструкциям в разделе [выполнение примеров Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="40e0b-134">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="40e0b-135">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="40e0b-135">The samples may already be installed on your machine.</span></span> <span data-ttu-id="40e0b-136">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="40e0b-136">Check for the following (default) directory before continuing.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> <span data-ttu-id="40e0b-137">Если этот каталог не существует, перейдите к [примерам Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , чтобы скачать все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Samples.</span><span class="sxs-lookup"><span data-stu-id="40e0b-137">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="40e0b-138">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="40e0b-138">This sample is located in the following directory.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Scenario\DataBinding\WPFDataBinding`  
