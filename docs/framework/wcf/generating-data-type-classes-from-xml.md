---
title: Формирование классов типов данных из XML
ms.date: 03/30/2017
ms.assetid: e4e5e4e8-527f-44d1-92fa-8904a08784ea
ms.openlocfilehash: 977b12b5c61c196a4f033361d37785e4ed0af73a
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/12/2019
ms.locfileid: "73975855"
---
# <a name="generating-data-type-classes-from-xml"></a><span data-ttu-id="e31ec-102">Формирование классов типов данных из XML</span><span class="sxs-lookup"><span data-stu-id="e31ec-102">Generating Data Type Classes from XML</span></span>
<span data-ttu-id="e31ec-103">.NET Framework 4,5 включает новую функцию для создания классов типов данных из XML.</span><span class="sxs-lookup"><span data-stu-id="e31ec-103">.NET Framework 4.5 includes a new feature to generate data type classes from XML.</span></span> <span data-ttu-id="e31ec-104">В этом разделе описывается автоматическое создание типов данных для RSS-канала блога .NET.</span><span class="sxs-lookup"><span data-stu-id="e31ec-104">This topic describes how to automatically generate data types for the .NET Blog RSS feed.</span></span>  
  
### <a name="obtaining-the-xml-from-the-net-blog-rss-feed"></a><span data-ttu-id="e31ec-105">Получение XML из RSS-канала блога .NET</span><span class="sxs-lookup"><span data-stu-id="e31ec-105">Obtaining the XML from the .NET Blog RSS feed</span></span>  
  
1. <span data-ttu-id="e31ec-106">В Internet Explorer перейдите к RSS- [каналу блога в блоге .NET](https://devblogs.microsoft.com/dotnet/feed/).</span><span class="sxs-lookup"><span data-stu-id="e31ec-106">In Internet Explorer, navigate to the [.NET Blog RSS feed](https://devblogs.microsoft.com/dotnet/feed/).</span></span>  
  
2. <span data-ttu-id="e31ec-107">Щелкните страницу правой кнопкой мыши и выберите пункт **Просмотр источника**.</span><span class="sxs-lookup"><span data-stu-id="e31ec-107">Right-click the page and select **View Source**.</span></span>  
  
3. <span data-ttu-id="e31ec-108">Скопируйте текст веб-канала, нажав клавиши **CTRL + A** , чтобы выделить весь текст, и **CTRL + C** для копирования.</span><span class="sxs-lookup"><span data-stu-id="e31ec-108">Copy the text of the feed by pressing **Ctrl+A** to select all text, and **Ctrl+C** to copy.</span></span>  
  
### <a name="creating-the-data-types"></a><span data-ttu-id="e31ec-109">Создание типов данных</span><span class="sxs-lookup"><span data-stu-id="e31ec-109">Creating the data types</span></span>  
  
1. <span data-ttu-id="e31ec-110">Откройте файл кода, в котором будет использоваться прокси.</span><span class="sxs-lookup"><span data-stu-id="e31ec-110">Open a code file where the proxy is to be used.</span></span> <span data-ttu-id="e31ec-111">Этот файл должен быть частью проекта .NET Framework 4,5.</span><span class="sxs-lookup"><span data-stu-id="e31ec-111">This file should be part of a .NET Framework 4.5 project.</span></span>  
  
2. <span data-ttu-id="e31ec-112">Поместите курсор в такое место в файле, чтобы он был вне пределов описанных в файле классов.</span><span class="sxs-lookup"><span data-stu-id="e31ec-112">Place the cursor in a location in the file outside any existing classes.</span></span>  
  
3. <span data-ttu-id="e31ec-113">Выберите **Правка**, **Специальная вставка**, **Вставить XML как классы**.</span><span class="sxs-lookup"><span data-stu-id="e31ec-113">Select **Edit**, **Paste Special**, **Paste XML as Classes**.</span></span>  
  
4. <span data-ttu-id="e31ec-114">Классы с именами `link`, `rss`, `rssChannel`, `rssChannelImage`, `rssChannelItem` и `rssChannelItemGuid` создаются с необходимыми элементами для доступа к элементам RSS-канала.</span><span class="sxs-lookup"><span data-stu-id="e31ec-114">Classes called `link`, `rss`, `rssChannel`, `rssChannelImage`, `rssChannelItem` and `rssChannelItemGuid` are created with the necessary members for accessing the elements in the RSS feed.</span></span>  
  
### <a name="using-the-generated-classes"></a><span data-ttu-id="e31ec-115">Использование созданных классов</span><span class="sxs-lookup"><span data-stu-id="e31ec-115">Using the generated classes</span></span>  
  
1. <span data-ttu-id="e31ec-116">После создания классов их можно использовать в коде так же, как и любые другие классы.</span><span class="sxs-lookup"><span data-stu-id="e31ec-116">Once the classes are generated, they can be used in code like any other classes.</span></span> <span data-ttu-id="e31ec-117">В следующем примере кода показана инициализация нового экземпляра класса `rssChannelImage`.</span><span class="sxs-lookup"><span data-stu-id="e31ec-117">The following code example returns a new instance of the `rssChannelImage` class.</span></span>  
  
    ```csharp
    var channelImage = new rssChannelImage()   
    {   
        title = "MyImage",   
        link = "http://www.contoso.com/images/channelImage.jpg",   
        url = "http://www.contoso.com/entries/myEntry.html"   
    };  
    ```
