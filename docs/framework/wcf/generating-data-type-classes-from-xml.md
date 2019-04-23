---
title: Формирование классов типов данных из XML
ms.date: 03/30/2017
ms.assetid: e4e5e4e8-527f-44d1-92fa-8904a08784ea
ms.openlocfilehash: c1b5dfda8aa5370dbc202ab90c75ab5677970467
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59309346"
---
# <a name="generating-data-type-classes-from-xml"></a>Формирование классов типов данных из XML
[!INCLUDE[net_v45](../../../includes/net-v45-md.md)] включает новую возможность для создания классов типа данных из XML. В этом разделе описывается, как для автоматического создания типов данных для веб-канала RSS блоге .NET.  
  
### <a name="obtaining-the-xml-from-the-net-blog-rss-feed"></a>Получение XML-данных из блога .NET RSS-канала  
  
1. В Internet Explorer, перейдите к [.NET блог RSS-канал](https://devblogs.microsoft.com/dotnet/feed/).  
  
2. Щелкните страницу правой кнопкой мыши и выберите **Просмотр исходного кода**.  
  
3. Скопируйте текст канала, нажав клавишу **Ctrl + A** выделит весь текст и **Ctrl + C** для копирования.  
  
### <a name="creating-the-data-types"></a>Создание типов данных  
  
1. Откройте файл кода, в котором будет использоваться прокси. Этот файл должен быть частью проекта [!INCLUDE[net_v45](../../../includes/net-v45-md.md)].  
  
2. Поместите курсор в такое место в файле, чтобы он был вне пределов описанных в файле классов.  
  
3. Выберите **изменить**, **Специальная вставка**, **вставке XML как классы**.  
  
4. Классы, называемые `link`, `rss`, `rssChannel`, `rssChannelImage`, `rssChannelItem` и `rssChannelItemGuid` создаются с необходимыми членами для доступа к элементам в RSS-канала.  
  
### <a name="using-the-generated-classes"></a>Использование созданных классов  
  
1. После создания классов их можно использовать в коде так же, как и любые другие классы. В следующем примере кода показана инициализация нового экземпляра класса `rssChannelImage`.  
  
    ```  
    var channelImage = new rssChannelImage()   
    {   
        title = "MyImage",   
        link = "http://www.contoso.com/images/channelImage.jpg",   
        url = "http://www.contoso.com/entries/myEntry.html"   
    };  
    ```
