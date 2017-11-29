---
title: "Создание приложения Магазина Windows, работающего со службой OData"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: csharp
ms.assetid: 9917a0e9-ec93-49e5-a366-fd39b892eb8b
caps.latest.revision: "4"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 0c1e2b9092abd54fd62848f58e2385bee5058553
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="writing-a-windows-store-app-that-consumes-an-odata-service"></a><span data-ttu-id="bc724-102">Создание приложения Магазина Windows, работающего со службой OData</span><span class="sxs-lookup"><span data-stu-id="bc724-102">Writing a Windows Store App that consumes an OData Service</span></span>
<span data-ttu-id="bc724-103">Windows 8 появился новый тип приложения: приложение для магазина Windows.</span><span class="sxs-lookup"><span data-stu-id="bc724-103">Windows 8 introduces a new type of application: the Windows Store app.</span></span> <span data-ttu-id="bc724-104">Приложения Магазина Windows имеют новый внешний вид, выполняются на различных устройствах и доступны в Магазине Windows.</span><span class="sxs-lookup"><span data-stu-id="bc724-104">Windows Store apps have a brand new look and feel, run on a variety of devices, and are made available on the Windows Store.</span></span> <span data-ttu-id="bc724-105">В этом разделе описывается процесс создания приложения Магазина Windows, использующего службу OData, а именно, службу OData NetFlix Catalog.</span><span class="sxs-lookup"><span data-stu-id="bc724-105">This topic describes how to write a Windows Store app that consumes an OData service, specifically the NetFlix Catalog OData service.</span></span> <span data-ttu-id="bc724-106">Дополнительные сведения о приложениях для магазина Windows, ознакомьтесь с [Приступая к работе с приложениями магазина Windows](http://msdn.microsoft.com/library/windows/apps/br211386.aspx).</span><span class="sxs-lookup"><span data-stu-id="bc724-106">For more information about Windows Store Apps, please read [Getting Started with Windows Store apps](http://msdn.microsoft.com/library/windows/apps/br211386.aspx).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="bc724-107">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="bc724-107">Prerequisites</span></span>  
  
1.  [<span data-ttu-id="bc724-108">Microsoft Windows 8</span><span class="sxs-lookup"><span data-stu-id="bc724-108">Microsoft Windows 8</span></span>](http://go.microsoft.com/fwlink/p/?LinkId=266654)  
  
2.  [<span data-ttu-id="bc724-109">Microsoft Visual Studio 2012</span><span class="sxs-lookup"><span data-stu-id="bc724-109">Microsoft Visual Studio 2012</span></span>](http://go.microsoft.com/fwlink/p/?LinkId=266655)  
  
3.  [<span data-ttu-id="bc724-110">Службы данных WCF</span><span class="sxs-lookup"><span data-stu-id="bc724-110">WCF Data Services</span></span>](http://msdn.microsoft.com/data/bb931106)  
  
#### <a name="creating-the-default-windows-store-grid-application"></a><span data-ttu-id="bc724-111">Создание приложения Магазина Windows с сеткой по умолчанию</span><span class="sxs-lookup"><span data-stu-id="bc724-111">Creating the default Windows Store Grid Application</span></span>  
  
1.  <span data-ttu-id="bc724-112">Создайте новое приложение Магазина Windows с сеткой с помощью C# и XAML.</span><span class="sxs-lookup"><span data-stu-id="bc724-112">Create a new Windows Store Grid Application using C# and XAML.</span></span> <span data-ttu-id="bc724-113">Назовите приложение OData.WindowsStore.NetflixDemo:</span><span class="sxs-lookup"><span data-stu-id="bc724-113">Name the application OData.WindowsStore.NetflixDemo:</span></span>  
  
     <span data-ttu-id="bc724-114">![Диалоговое окно нового проекта](../../../../docs/framework/data/wcf/media/win8clientcreatenewproject.png "Win8ClientCreateNewProject")</span><span class="sxs-lookup"><span data-stu-id="bc724-114">![New Project Dialog](../../../../docs/framework/data/wcf/media/win8clientcreatenewproject.png "Win8ClientCreateNewProject")</span></span>  
  
2.  <span data-ttu-id="bc724-115">Откройте Package.appxmanifest и введите понятное имя в текстовом поле «Отображаемое имя».</span><span class="sxs-lookup"><span data-stu-id="bc724-115">Open the Package.appxmanifest and enter a friendly name in the Display name text box.</span></span> <span data-ttu-id="bc724-116">Оно задает имя приложения, используемое функциями поиска Windows 8.</span><span class="sxs-lookup"><span data-stu-id="bc724-116">This specifies the application name used with the Windows 8 search functionality.</span></span>  
  
     <span data-ttu-id="bc724-117">![Файл манифеста приложения](../../../../docs/framework/data/wcf/media/appxmanifest.png "appxmanifest")</span><span class="sxs-lookup"><span data-stu-id="bc724-117">![Application manifest file](../../../../docs/framework/data/wcf/media/appxmanifest.png "appxmanifest")</span></span>  
  
3.  <span data-ttu-id="bc724-118">Введите понятное имя в \<AppName > в файле App.xaml.</span><span class="sxs-lookup"><span data-stu-id="bc724-118">Enter a friendly name in the \<AppName> element in the App.xaml file.</span></span> <span data-ttu-id="bc724-119">Оно определяет имя приложения, которое будет отображаться при запуске приложения:</span><span class="sxs-lookup"><span data-stu-id="bc724-119">This sets the application name that is displayed when the application is launched:</span></span>  
  
     <span data-ttu-id="bc724-120">![Файл app.XAML](../../../../docs/framework/data/wcf/media/appxaml.png "appxaml")</span><span class="sxs-lookup"><span data-stu-id="bc724-120">![App.xaml file](../../../../docs/framework/data/wcf/media/appxaml.png "appxaml")</span></span>  
  
4.  <span data-ttu-id="bc724-121">Соберите и запустите приложение.</span><span class="sxs-lookup"><span data-stu-id="bc724-121">Build and launch the application.</span></span> <span data-ttu-id="bc724-122">Сначала отобразится заставка приложения.</span><span class="sxs-lookup"><span data-stu-id="bc724-122">You first see the application’s splash screen.</span></span> <span data-ttu-id="bc724-123">Заставка по умолчанию представлена на снимке экрана ниже.</span><span class="sxs-lookup"><span data-stu-id="bc724-123">The screenshot below displays the default splash screen.</span></span> <span data-ttu-id="bc724-124">Используемое изображение хранится в папке проекта «Assets».</span><span class="sxs-lookup"><span data-stu-id="bc724-124">The image used is stored in the project’s Assets folder.</span></span>  
  
     <span data-ttu-id="bc724-125">![Экран-заставка приложения по умолчанию](../../../../docs/framework/data/wcf/media/defualtappsplash.png "defualtAppSplash")</span><span class="sxs-lookup"><span data-stu-id="bc724-125">![The default app splash screen](../../../../docs/framework/data/wcf/media/defualtappsplash.png "defualtAppSplash")</span></span>  
  
     <span data-ttu-id="bc724-126">Затем появится приложение.</span><span class="sxs-lookup"><span data-stu-id="bc724-126">Then the application will be displayed.</span></span>  
  
     <span data-ttu-id="bc724-127">![Приложение по умолчанию](../../../../docs/framework/data/wcf/media/defaultapplication.png "DefaultApplication")</span><span class="sxs-lookup"><span data-stu-id="bc724-127">![The default application](../../../../docs/framework/data/wcf/media/defaultapplication.png "DefaultApplication")</span></span>  
  
     <span data-ttu-id="bc724-128">Приложение по умолчанию определяет набор классов в SampleDataSource.cs: SampleDataGroup и SampleDataItem, которые являются производными от SampleDataCommon, который, в свою очередь, является производным от BindableBase.</span><span class="sxs-lookup"><span data-stu-id="bc724-128">The default application defines a set of classes in SampleDataSource.cs: SampleDataGroup and SampleDataItem, both of which are derived from SampleDataCommon, which itself is derived from BindableBase.</span></span> <span data-ttu-id="bc724-129">SampleDataGroup и SampleDataItem привязаны к GridView по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="bc724-129">SampleDataGroup and SampleDataItem are bound to the default GridView.</span></span> <span data-ttu-id="bc724-130">SampleDataSource.cs расположен в папке DataModel в проекте NetflixDemo.</span><span class="sxs-lookup"><span data-stu-id="bc724-130">SampleDataSource.cs is located in the DataModel folder within the NetflixDemo project.</span></span> <span data-ttu-id="bc724-131">Приложение отображает сгруппированную коллекцию.</span><span class="sxs-lookup"><span data-stu-id="bc724-131">The application displays a grouped collection.</span></span> <span data-ttu-id="bc724-132">Каждая группа содержит произвольное количество элементов; их представляют SampleDataGroup и SampleDataItem соответственно.</span><span class="sxs-lookup"><span data-stu-id="bc724-132">Each group contains any number of items, represented by SampleDataGroup and SampleDataItem, respectively.</span></span> <span data-ttu-id="bc724-133">На предыдущем снимке экрана можно увидеть группу, озаглавленную как @@@Group Title 1, и все элементы в группе, отображаемые вместе.</span><span class="sxs-lookup"><span data-stu-id="bc724-133">In the previous screen shot you can see a group called Group Title 1 and all of the items in the group displayed together.</span></span>  
  
     <span data-ttu-id="bc724-134">Главная страница приложения — GroupedItemsPage.xaml.</span><span class="sxs-lookup"><span data-stu-id="bc724-134">The main page of the application is GroupedItemsPage.xaml.</span></span> <span data-ttu-id="bc724-135">Она содержит GridView, отображающий образец данных, созданный классом SampleDataSource.cs.</span><span class="sxs-lookup"><span data-stu-id="bc724-135">It contains a GridView that displays the sample data created by the SampleDataSource.cs class.</span></span> <span data-ttu-id="bc724-136">GroupedItemsPage загружается App.xaml.cs в вызове к rootFrame.Navigate:</span><span class="sxs-lookup"><span data-stu-id="bc724-136">The GroupedItemsPage is loaded by the App.xaml.cs in a call to rootFrame.Navigate:</span></span>  
  
    ```csharp  
    if (!rootFrame.Navigate(typeof(GroupedItemsPage), "AllGroups"))  
    {  
        throw new Exception("Failed to create initial page");  
    }  
    ```  
  
     <span data-ttu-id="bc724-137">Это приводит к созданию GroupedItemsPage и вызову ее метода LoadState.</span><span class="sxs-lookup"><span data-stu-id="bc724-137">This causes the GroupedItemsPage to be instantiated and it’s LoadState method is called.</span></span> <span data-ttu-id="bc724-138">LoadState вызывает создание статического экземпляра SampleDataSource, который создает коллекцию объектов SampleDataGroup.</span><span class="sxs-lookup"><span data-stu-id="bc724-138">LoadState causes the static SampleDataSource instance to be created, which creates a collection of SampleDataGroup objects.</span></span> <span data-ttu-id="bc724-139">Каждый объект SampleDataGroup содержит коллекцию объектов SampleDataItem.</span><span class="sxs-lookup"><span data-stu-id="bc724-139">Each SampleDataGroup object contains a collection of SampleDataItem objects.</span></span> <span data-ttu-id="bc724-140">LoadState хранит коллекцию объектов SampleDataGroup в DefaultViewModel:</span><span class="sxs-lookup"><span data-stu-id="bc724-140">LoadState stores the collection of SampleDataGroup objects in the DefaultViewModel:</span></span>  
  
    ```csharp  
    protected override void LoadState(Object navigationParameter, Dictionary<String, Object> pageState)  
    {  
        var sampleDataGroups = SampleDataSource.GetGroups((String)navigationParameter);  
        this.DefaultViewModel["Groups"] = sampleDataGroups;  
    }  
    ```  
  
     <span data-ttu-id="bc724-141">Затем DefaultViewModel привязывается к GridView.</span><span class="sxs-lookup"><span data-stu-id="bc724-141">The DefaultViewModel is then bound to the GridView.</span></span> <span data-ttu-id="bc724-142">При конфигурации привязки данных на него создается ссылка в файле GroupedItemsPage.xaml.</span><span class="sxs-lookup"><span data-stu-id="bc724-142">This is referenced in the GroupedItemsPage.xaml file when configuring the data binding.</span></span>  
  
    ```xaml
    <CollectionViewSource  
                x:Name="groupedItemsViewSource"  
                Source="{Binding Groups}"  
                IsSourceGrouped="true"  
                ItemsPath="TopItems"  
                d:Source="{Binding AllGroups, Source={d:DesignInstance Type=data:SampleDataSource, IsDesignTimeCreatable=True}}"/>  
    ```  
  
     <span data-ttu-id="bc724-143">CollectionViewSource используется в качестве посредника для обработки сгруппированных коллекций.</span><span class="sxs-lookup"><span data-stu-id="bc724-143">The CollectionViewSource is used as a proxy for handling grouped collections.</span></span> <span data-ttu-id="bc724-144">Когда происходит привязка, он проходит по коллекции объектов SampleDataGroup, заполняя GridView.</span><span class="sxs-lookup"><span data-stu-id="bc724-144">When binding occurs, it iterates through the collection of SampleDataGroup objects to populate the GridView.</span></span>  <span data-ttu-id="bc724-145">Атрибут ItemsPath указывает CollectionViewSource, какое свойство каждого объекта SampleDataGroup использовать для нахождения объектов SampleDataItem, которые он содержит.</span><span class="sxs-lookup"><span data-stu-id="bc724-145">The ItemsPath attribute tells the CollectionViewSource what property on each SampleDataGroup object to use to find the SampleDataItems it contains.</span></span> <span data-ttu-id="bc724-146">В этом случае каждый объект SampleDataGroup содержит коллекцию TopItems объектов SampleDataItem.</span><span class="sxs-lookup"><span data-stu-id="bc724-146">In this case each SampleDataGroup object contains a TopItems collection of SampleDataItem objects.</span></span>  
  
     <span data-ttu-id="bc724-147">Для приложения Netflix фильмы группируются по жанру.</span><span class="sxs-lookup"><span data-stu-id="bc724-147">For the Netflix application, movies are grouped by genre.</span></span> <span data-ttu-id="bc724-148">Таким образом, приложение отображает несколько жанров и список фильмов в этом жанре.</span><span class="sxs-lookup"><span data-stu-id="bc724-148">So the application displays a number of genres and a list of movies within that genre.</span></span>  
  
#### <a name="add-a-service-reference-to-the-netflix-odata-service"></a><span data-ttu-id="bc724-149">Добавить ссылку на службу в службу Netflix OData</span><span class="sxs-lookup"><span data-stu-id="bc724-149">Add a Service Reference to the Netflix OData Service</span></span>  
  
1.  <span data-ttu-id="bc724-150">Прежде чем можно будет совершать вызовы к службе Netflix OData, необходимо добавить ссылку на службу.</span><span class="sxs-lookup"><span data-stu-id="bc724-150">Before we can make any calls to the Netflix OData service we need to add a service reference.</span></span> <span data-ttu-id="bc724-151">В обозревателе решений щелкните проект правой кнопкой мыши и выберите команду «Добавить ссылку на службу...»</span><span class="sxs-lookup"><span data-stu-id="bc724-151">Right-click the project in the Solution Explorer and select Add Service Reference…</span></span>  
  
     <span data-ttu-id="bc724-152">![Добавить диалоговое окно ссылок на службы](../../../../docs/framework/data/wcf/media/addservicereferenceodata.png "AddServiceReferenceOData")</span><span class="sxs-lookup"><span data-stu-id="bc724-152">![Add Service Reference Dialog](../../../../docs/framework/data/wcf/media/addservicereferenceodata.png "AddServiceReferenceOData")</span></span>  
  
2.  <span data-ttu-id="bc724-153">Введите URL-адрес для службы Netflix OData в адресную строку и нажмите кнопку «Перейти».</span><span class="sxs-lookup"><span data-stu-id="bc724-153">Enter the URL for the Netflix OData service in the Address bar and click Go.</span></span> <span data-ttu-id="bc724-154">Задайте пространство имен ссылки на службу в Netflix и нажмите кнопку «ОК».</span><span class="sxs-lookup"><span data-stu-id="bc724-154">Set the Namespace of the service reference to Netflix and click OK.</span></span>  
  
     <span data-ttu-id="bc724-155">![Добавить ошибку ссылки на службу](../../../../docs/framework/data/wcf/media/addservicereferenceerror.png "AddServiceReferenceError")</span><span class="sxs-lookup"><span data-stu-id="bc724-155">![Add Service Reference Error](../../../../docs/framework/data/wcf/media/addservicereferenceerror.png "AddServiceReferenceError")</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="bc724-156">Если вы еще не установили [WCF данных службы средств для приложений магазина Windows](http://go.microsoft.com/fwlink/p/?LinkId=266652), появится сообщение, подобное показанному выше.</span><span class="sxs-lookup"><span data-stu-id="bc724-156">If you have not yet installed [WCF Data Services Tools for Windows Store Apps](http://go.microsoft.com/fwlink/p/?LinkId=266652), you will be prompted with a message such as the one above.</span></span> <span data-ttu-id="bc724-157">Для продолжения необходимо будет загрузить и установить средства по приведенной ссылке.</span><span class="sxs-lookup"><span data-stu-id="bc724-157">You will need to download and install the tools referenced in the link to continue.</span></span>  
  
 <span data-ttu-id="bc724-158">Добавление ссылки на службы создает строго типизированные классы, которые службы WCF Data Services будут использовать для синтаксического анализа OData возвращаемых службой Netflix OData.</span><span class="sxs-lookup"><span data-stu-id="bc724-158">Adding a service reference generates strongly typed classes that WCF Data Services will use to parse the OData returned by the Netflix OData service.</span></span> <span data-ttu-id="bc724-159">Классы, определенные в SampleDataSource.cs, можно привязать к GridView, поэтому необходимо передать данные из созданных клиентских классов OData в поддерживающие привязку классы, определенные в SampleDataSource.cs.</span><span class="sxs-lookup"><span data-stu-id="bc724-159">The classes defined in SampleDataSource.cs can be bound to the GridView so we need to transfer the data from the generated OData client classes into the bindable classes defined in SampleDataSource.cs.</span></span>  <span data-ttu-id="bc724-160">Чтобы сделать это, необходимо внести некоторые изменения в модель данных, определенную в SampleDataSource.cs.</span><span class="sxs-lookup"><span data-stu-id="bc724-160">In order to do this, we need to make some changes to the data model defined in SampleDataSource.cs.</span></span>  
  
#### <a name="update-the-data-model-for-the-application"></a><span data-ttu-id="bc724-161">Обновление модели данных для приложения</span><span class="sxs-lookup"><span data-stu-id="bc724-161">Update the data model for the application</span></span>  
  
1.  <span data-ttu-id="bc724-162">Замените существующий код в SampleDataSource.cs кодом из [этой страницы](https://gist.github.com/3419288).</span><span class="sxs-lookup"><span data-stu-id="bc724-162">Replace the existing code in SampleDataSource.cs with the code from [this gist](https://gist.github.com/3419288).</span></span> <span data-ttu-id="bc724-163">Обновленный код добавляет метод LoadMovies (в класс SampleDataSource), который выполняет запрос к службе Netflix OData и заполняет список жанров (allGroups), а в каждом жанре — список фильмов.</span><span class="sxs-lookup"><span data-stu-id="bc724-163">The updated code adds a LoadMovies method (to the SampleDataSource class)  that performs a query against the Netflix OData service and populates a list of genres (allGroups) and within each genre a list of movies.</span></span> <span data-ttu-id="bc724-164">Класс SampleDataGroup используется для представления жанра, а класс SampleDataItem — для представления фильма.</span><span class="sxs-lookup"><span data-stu-id="bc724-164">The SampleDataGroup class is used to represent a genre and the SampleDataItem class is used to represent a movie.</span></span>  
  
    ```csharp  
    public static async void LoadMovies()  
    {  
        IEnumerable<Title> titles = await ((DataServiceQuery<Title>)Context.Titles  
            .Expand("Genres,AudioFormats,AudioFormats/Language,Awards,Cast")  
            .Where(t => t.Rating == "PG")  
            .OrderByDescending(t => t.ReleaseYear)  
            .Take(300)).ExecuteAsync();  
  
        foreach (Title title in titles)  
        {  
            foreach (Genre netflixGenre in title.Genres)  
            {  
                SampleDataGroup genre = GetGroup(netflixGenre.Name);  
                if (genre == null)  
                {  
                    genre = new SampleDataGroup(netflixGenre.Name, netflixGenre.Name, String.Empty, title.BoxArt.LargeUrl, String.Empty);  
                    Instance.AllGroups.Add(genre);  
                }  
                var content = new StringBuilder();  
                // Write additional things to content here if you want them to display in the item detail.  
                genre.Items.Add(new SampleDataItem(title.Id, title.Name, String.Format("{0}rnrn{1} ({2})", title.Synopsis, title.Rating, title.ReleaseYear), title.BoxArt.HighDefinitionUrl ?? title.BoxArt.LargeUrl, "Description", content.ToString()));  
            }  
        }  
    }  
    ```  
  
     <span data-ttu-id="bc724-165">[Асинхронная модель на основе задач](http://go.microsoft.com/fwlink/p/?LinkId=266651) (TAP) используется для асинхронного получения 300 (Take) последних (OrderByDescending) PG-рейтингом фильмы обратно из Netflix.</span><span class="sxs-lookup"><span data-stu-id="bc724-165">The [Task-based Asynchronous Pattern](http://go.microsoft.com/fwlink/p/?LinkId=266651) (TAP) is used to asynchronously get 300 (Take) recent (OrderByDescending) PG-rated (Where) movies back from Netflix.</span></span> <span data-ttu-id="bc724-166">Оставшаяся часть кода создает SimpleDataItems и SimpleDataGroups из сущностей, которые были возвращены в канале OData.</span><span class="sxs-lookup"><span data-stu-id="bc724-166">The rest of the code constructs SimpleDataItems and SimpleDataGroups from the entities that were returned in the OData feed.</span></span>  
  
     <span data-ttu-id="bc724-167">Класс SampleDataSource также реализует простой метод поиска.</span><span class="sxs-lookup"><span data-stu-id="bc724-167">The SampleDataSource class also implements a simple search method.</span></span> <span data-ttu-id="bc724-168">В этом случае он выполняет простой поиск загруженных фильмов в памяти.</span><span class="sxs-lookup"><span data-stu-id="bc724-168">In this case, it does a simple in-memory search of the loaded movies.</span></span>  
  
    ```csharp  
    public static IEnumerable<SampleDataItem> Search(string searchString)  
    {  
            var regex = new Regex(searchString, RegexOptions.CultureInvariant | RegexOptions.IgnoreCase | RegexOptions.IgnorePatternWhitespace);  
            return Instance.AllGroups  
                .SelectMany(g => g.Items)  
                .Where(m => regex.IsMatch(m.Title) || regex.IsMatch(m.Subtitle))  
                    .Distinct(new SampleDataItemComparer());  
    }  
    ```  
  
     <span data-ttu-id="bc724-169">Также в SampleDataSource.cs определяется класс ExtensionMethods.</span><span class="sxs-lookup"><span data-stu-id="bc724-169">Also in SampleDataSource.cs a class called ExtensionMethods is defined.</span></span> <span data-ttu-id="bc724-170">Каждый из этих методов расширения использует шаблон TAP, чтобы разрешить SampleDataSource выполнить запрос OData без блокировки пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="bc724-170">Each of these extension methods uses the TAP pattern to allow the SampleDataSource to execute an OData query without blocking the UI.</span></span> <span data-ttu-id="bc724-171">Например, следующий код использует для реализации TAP метод Task.Factory.FromAsync.</span><span class="sxs-lookup"><span data-stu-id="bc724-171">For example, the following code uses the Task.Factory.FromAsync method to implement TAP.</span></span>  
  
    ```csharp  
    public static async Task<IEnumerable<T>> ExecuteAsync<T>(this DataServiceQuery<T> query)  
    {  
        return await Task.Factory.FromAsync<IEnumerable<T>>(query.BeginExecute(null, null), query.EndExecute);  
    }  
    ```  
  
     <span data-ttu-id="bc724-172">Как и в приложении по умолчанию, главная страница приложения — GroupedItemsPage.</span><span class="sxs-lookup"><span data-stu-id="bc724-172">As in the default application, the main page of the application is GroupedItemsPage.</span></span> <span data-ttu-id="bc724-173">В этот раз, однако, на ней отображаются фильмы, полученные из Netflix и сгруппированные по жанру.</span><span class="sxs-lookup"><span data-stu-id="bc724-173">This time, however, it displays the movies retrieved from Netflix grouped by genre.</span></span>  <span data-ttu-id="bc724-174">После создания GroupedItemsPage вызывается его метода LoadState.</span><span class="sxs-lookup"><span data-stu-id="bc724-174">When the GroupedItemsPage is instantiated, its LoadState method is called.</span></span> <span data-ttu-id="bc724-175">LoadState вызывает создание статического экземпляра SampleDataSource путем обращения к службе Netflix OData, как описано выше.</span><span class="sxs-lookup"><span data-stu-id="bc724-175">LoadState causes the static SampleDataSource instance to be created, making a call to the Netflix OData service as discussed previously.</span></span> <span data-ttu-id="bc724-176">LoadState хранит коллекцию жанров (объектов SampleDataGroup) в DefaultViewModel:</span><span class="sxs-lookup"><span data-stu-id="bc724-176">LoadState stores the collection of genres (SampleDataGroup objects) in the DefaultViewModel:</span></span>  
  
    ```csharp  
    protected override void LoadState(Object navigationParameter, Dictionary<String, Object> pageState)  
    {  
  
        var sampleDataGroups = SampleDataSource.GetGroups((String)navigationParameter);  
        this.DefaultViewModel["Groups"] = sampleDataGroups;  
    }  
    ```  
  
     <span data-ttu-id="bc724-177">Как описано выше, после этого используется DefaultViewModel для привязки данных к GridView.</span><span class="sxs-lookup"><span data-stu-id="bc724-177">As described previously, the DefaultViewModel is then used to bind the data to the GridView.</span></span>  
  
#### <a name="add-a-search-contract-to-allow-the-application-to-participate-in-windows-search"></a><span data-ttu-id="bc724-178">Добавьте контракт поиска, чтобы разрешить приложению участвовать в поиске Windows</span><span class="sxs-lookup"><span data-stu-id="bc724-178">Add a search contract to allow the application to participate in Windows search</span></span>  
  
1.  <span data-ttu-id="bc724-179">Добавьте контракт поиска в приложение.</span><span class="sxs-lookup"><span data-stu-id="bc724-179">Add a search contract to the application.</span></span> <span data-ttu-id="bc724-180">Это даст приложению возможность интеграции с интерфейсом поиска Windows 8.</span><span class="sxs-lookup"><span data-stu-id="bc724-180">This allows the application to integrate with the Windows 8 search experience.</span></span> <span data-ttu-id="bc724-181">Назовите контракт поиска SearchResultsPage.xaml</span><span class="sxs-lookup"><span data-stu-id="bc724-181">Name the search contract SearchResultsPage.xaml</span></span>  
  
     <span data-ttu-id="bc724-182">![Добавьте контракт поиска](../../../../docs/framework/data/wcf/media/addsearchcontract.png "AddSearchContract")</span><span class="sxs-lookup"><span data-stu-id="bc724-182">![Add a search contract](../../../../docs/framework/data/wcf/media/addsearchcontract.png "AddSearchContract")</span></span>  
  
2.  <span data-ttu-id="bc724-183">Измените строку 58 в SearchResultsPage.xaml.cs, удалив внутренние кавычки, в которые взят queryText.</span><span class="sxs-lookup"><span data-stu-id="bc724-183">Modify line 58 of SearchResultsPage.xaml.cs by removing the embedded quotes around queryText.</span></span>  
  
    ```csharp  
    // Communicate results through the view model  
    this.DefaultViewModel["QueryText"] = queryText;  
    this.DefaultViewModel["Filters"] = filterList;  
    this.DefaultViewModel["ShowFilters"] = filterList.Count > 1;  
    ```  
  
3.  <span data-ttu-id="bc724-184">Вставьте следующие две строки кода в строку 81 в SearchResultsPage.xaml.cs для получения результатов поиска.</span><span class="sxs-lookup"><span data-stu-id="bc724-184">Insert the following two lines of code at line 81 in SearchResultsPage.xaml.cs to retrieve the search results.</span></span>  
  
    ```csharp  
    // TODO: Respond to the change in active filter by setting this.DefaultViewModel["Results"]  
                    //       to a collection of items with bindable Image, Title, Subtitle, and Description properties  
                    var searchValue = (string)this.DefaultViewModel["QueryText"];  
                    this.DefaultViewModel["Results"] = new List<SampleDataItem>(SampleDataSource.Search(searchValue));  
    ```  
  
 <span data-ttu-id="bc724-185">Когда пользователь вызовет поиск Windows, введет поисковый запрос и нажмет значок демонстрационного приложения Netflix на панели поиска, будет выполнен метод LoadState в SearchResultsPage.</span><span class="sxs-lookup"><span data-stu-id="bc724-185">When a user invokes Windows search, types in a search term and then touches the Netflix Demo app icon in the search bar, the LoadState method of the SearchResultsPage is executed.</span></span> <span data-ttu-id="bc724-186">Параметр навигации, отправляемый в LoadState, содержит поисковый запрос.</span><span class="sxs-lookup"><span data-stu-id="bc724-186">The navigation parameter sent to LoadState contains the query text.</span></span> <span data-ttu-id="bc724-187">После этого будет вызван метод Filter_SelectionChanged, который вызовет метод Search класса SampleDataSource.</span><span class="sxs-lookup"><span data-stu-id="bc724-187">Next the Filter_SelectionChanged method is called which then calls the Search method on the SampleDataSource class.</span></span> <span data-ttu-id="bc724-188">Возвращенные результаты будут выведены на странице SearchResultsPage.xaml.</span><span class="sxs-lookup"><span data-stu-id="bc724-188">The results are returned and displayed in the SearchResultsPage.xaml page.</span></span>  
  
```csharp  
/// <summary>  
        /// Invoked when a filter is selected using the ComboBox in snapped view state.  
        /// </summary>  
        /// <param name="sender">The ComboBox instance.</param>  
        /// <param name="e">Event data describing how the selected filter was changed.</param>  
        void Filter_SelectionChanged(object sender, SelectionChangedEventArgs e)  
        {  
            // Determine what filter was selected  
            var selectedFilter = e.AddedItems.FirstOrDefault() as Filter;  
            if (selectedFilter != null)  
            {  
                // Mirror the results into the corresponding Filter object to allow the  
                // RadioButton representation used when not snapped to reflect the change  
                selectedFilter.Active = true;  
  
                // TODO: Respond to the change in active filter by setting this.DefaultViewModel["Results"]  
                //       to a collection of items with bindable Image, Title, Subtitle, and Description properties  
                var searchValue = (string)this.DefaultViewModel["QueryText"];  
                this.DefaultViewModel["Results"] = new List<SampleDataItem>(SampleDataSource.Search(searchValue));  
  
                // Ensure results are found  
                object results;  
                ICollection resultsCollection;  
                if (this.DefaultViewModel.TryGetValue("Results", out results) &&  
                    (resultsCollection = results as ICollection) != null &&  
                    resultsCollection.Count != 0)  
                {  
                    VisualStateManager.GoToState(this, "ResultsFound", true);  
                    return;  
                }  
            }  
  
            // Display informational text when there are no search results.  
            VisualStateManager.GoToState(this, "NoResultsFound", true);  
        }  
```  
  
 <span data-ttu-id="bc724-189">Дополнительные сведения об интеграции поиска в приложение см [поиск: интеграция в интерфейс поиска Windows 8](http://go.microsoft.com/fwlink/p/?LinkId=266650).</span><span class="sxs-lookup"><span data-stu-id="bc724-189">For more information on integrating search into an application see, [Search: integrating into the Windows 8 search experience](http://go.microsoft.com/fwlink/p/?LinkId=266650).</span></span>  
  
## <a name="run-the-application"></a><span data-ttu-id="bc724-190">Запуск приложения</span><span class="sxs-lookup"><span data-stu-id="bc724-190">Run the application</span></span>  
 <span data-ttu-id="bc724-191">Запустите приложение, нажав клавишу F5.</span><span class="sxs-lookup"><span data-stu-id="bc724-191">Launch the application by pressing F5.</span></span> <span data-ttu-id="bc724-192">Обратите внимание, что загрузка изображений при запуске приложения занимает несколько секунд.</span><span class="sxs-lookup"><span data-stu-id="bc724-192">Note that it will take a few seconds to load the images upon application launch.</span></span> <span data-ttu-id="bc724-193">Кроме того, первая попытка поиска может не вернуть никаких результатов.</span><span class="sxs-lookup"><span data-stu-id="bc724-193">Also, your first search attempt may not return any results.</span></span> <span data-ttu-id="bc724-194">В реальном приложении возникнет необходимость устранить обе эти проблемы.</span><span class="sxs-lookup"><span data-stu-id="bc724-194">In a real-world application, you would want to deal with both of these issues.</span></span>  
  
 <span data-ttu-id="bc724-195">Приложение вызывает службу Netflix OData, получает данные в создаваемых клиентских классах OData, а затем передает эти данные в поддерживающие привязку классы данных (SampleDataSource, SampleDataGroup и SampleDataItem).</span><span class="sxs-lookup"><span data-stu-id="bc724-195">The application calls the Netflix OData service, receives the data in the generated OData client classes and then transfers that data to bindable data classes (SampleDataSource, SampleDataGroup, and SampleDataItem).</span></span> <span data-ttu-id="bc724-196">Оно использует эти поддерживающие привязку классы для привязки данных к GridView.</span><span class="sxs-lookup"><span data-stu-id="bc724-196">It uses these bindable classes to bind the data to the GridView.</span></span> <span data-ttu-id="bc724-197">Если вы не знакомы с принципами работы системы привязки данных для XAML см. в разделе [как группировать элементы в списке или сетке (приложения магазина Windows с помощью C#, VB, C++ и XAML)](http://msdn.microsoft.com/library/windows/apps/xaml/hh780627).</span><span class="sxs-lookup"><span data-stu-id="bc724-197">If you are unfamiliar with how XAML databinding works see [How to group items in a list or grid (Windows Store apps using C#/VB/C++ and XAML)](http://msdn.microsoft.com/library/windows/apps/xaml/hh780627).</span></span>
