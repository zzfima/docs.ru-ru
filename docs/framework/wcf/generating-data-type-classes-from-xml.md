---
title: Формирование классов типов данных из XML
ms.date: 03/30/2017
ms.assetid: e4e5e4e8-527f-44d1-92fa-8904a08784ea
ms.openlocfilehash: a6666f1ba23dd563bd7a005d458cd7fe8253c3af
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/08/2019
ms.locfileid: "57679090"
---
# <a name="generating-data-type-classes-from-xml"></a><span data-ttu-id="2a045-102">Формирование классов типов данных из XML</span><span class="sxs-lookup"><span data-stu-id="2a045-102">Generating Data Type Classes from XML</span></span>
[!INCLUDE[net_v45](../../../includes/net-v45-md.md)] <span data-ttu-id="2a045-103">включает новую функцию для создания классов типа данных из XML.</span><span class="sxs-lookup"><span data-stu-id="2a045-103">includes a new feature to generate data type classes from XML.</span></span> <span data-ttu-id="2a045-104">В этом разделе описывается, как для автоматического создания типов данных для веб-канала RSS блоге .NET.</span><span class="sxs-lookup"><span data-stu-id="2a045-104">This topic describes how to automatically generate data types for the .NET Blog RSS feed.</span></span>  
  
### <a name="obtaining-the-xml-from-the-net-blog-rss-feed"></a><span data-ttu-id="2a045-105">Получение XML-данных из блога .NET RSS-канала</span><span class="sxs-lookup"><span data-stu-id="2a045-105">Obtaining the XML from the .NET Blog RSS feed</span></span>  
  
1.  <span data-ttu-id="2a045-106">В Internet Explorer, перейдите к [.NET блог RSS-канал](https://devblogs.microsoft.com/dotnet/feed/).</span><span class="sxs-lookup"><span data-stu-id="2a045-106">In Internet Explorer, navigate to the [.NET Blog RSS feed](https://devblogs.microsoft.com/dotnet/feed/).</span></span>  
  
2.  <span data-ttu-id="2a045-107">Щелкните страницу правой кнопкой мыши и выберите **Просмотр исходного кода**.</span><span class="sxs-lookup"><span data-stu-id="2a045-107">Right-click the page and select **View Source**.</span></span>  
  
3.  <span data-ttu-id="2a045-108">Скопируйте текст канала, нажав клавишу **Ctrl + A** выделит весь текст и **Ctrl + C** для копирования.</span><span class="sxs-lookup"><span data-stu-id="2a045-108">Copy the text of the feed by pressing **Ctrl+A** to select all text, and **Ctrl+C** to copy.</span></span>  
  
### <a name="creating-the-data-types"></a><span data-ttu-id="2a045-109">Создание типов данных</span><span class="sxs-lookup"><span data-stu-id="2a045-109">Creating the data types</span></span>  
  
1.  <span data-ttu-id="2a045-110">Откройте файл кода, в котором будет использоваться прокси.</span><span class="sxs-lookup"><span data-stu-id="2a045-110">Open a code file where the proxy is to be used.</span></span> <span data-ttu-id="2a045-111">Этот файл должен быть частью проекта [!INCLUDE[net_v45](../../../includes/net-v45-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2a045-111">This file should be part of a [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] project.</span></span>  
  
2.  <span data-ttu-id="2a045-112">Поместите курсор в такое место в файле, чтобы он был вне пределов описанных в файле классов.</span><span class="sxs-lookup"><span data-stu-id="2a045-112">Place the cursor in a location in the file outside any existing classes.</span></span>  
  
3.  <span data-ttu-id="2a045-113">Выберите **изменить**, **Специальная вставка**, **вставке XML как классы**.</span><span class="sxs-lookup"><span data-stu-id="2a045-113">Select **Edit**, **Paste Special**, **Paste XML as Classes**.</span></span>  
  
4.  <span data-ttu-id="2a045-114">Классы, называемые `link`, `rss`, `rssChannel`, `rssChannelImage`, `rssChannelItem` и `rssChannelItemGuid` создаются с необходимыми членами для доступа к элементам в RSS-канала.</span><span class="sxs-lookup"><span data-stu-id="2a045-114">Classes called `link`, `rss`, `rssChannel`, `rssChannelImage`, `rssChannelItem` and `rssChannelItemGuid` are created with the necessary members for accessing the elements in the RSS feed.</span></span>  
  
### <a name="using-the-generated-classes"></a><span data-ttu-id="2a045-115">Использование созданных классов</span><span class="sxs-lookup"><span data-stu-id="2a045-115">Using the generated classes</span></span>  
  
1.  <span data-ttu-id="2a045-116">После создания классов их можно использовать в коде так же, как и любые другие классы.</span><span class="sxs-lookup"><span data-stu-id="2a045-116">Once the classes are generated, they can be used in code like any other classes.</span></span> <span data-ttu-id="2a045-117">В следующем примере кода показана инициализация нового экземпляра класса `rssChannelImage`.</span><span class="sxs-lookup"><span data-stu-id="2a045-117">The following code example returns a new instance of the `rssChannelImage` class.</span></span>  
  
    ```  
    var channelImage = new rssChannelImage()   
    {   
        title = "MyImage",   
        link = "http://www.contoso.com/images/channelImage.jpg",   
        url = "http://www.contoso.com/entries/myEntry.html"   
    };  
    ```
