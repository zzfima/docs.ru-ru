---
title: Формирование классов типов данных из XML
ms.date: 03/30/2017
ms.assetid: e4e5e4e8-527f-44d1-92fa-8904a08784ea
ms.openlocfilehash: d66cbd1806b90d21a483d0c470f953ddfb9c4fca
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184136"
---
# <a name="generating-data-type-classes-from-xml"></a>Формирование классов типов данных из XML
.NET Framework 4.5 включает в себя новую функцию для генерации классов типа данных от XML. В этой теме описывается, как автоматически генерировать типы данных для RSS-канала блога .NET.  
  
### <a name="obtaining-the-xml-from-the-net-blog-rss-feed"></a>Получение XML из канала .NET блог RSS  
  
1. В Internet Explorer перейдите на [канал .NET Блог RSS](https://devblogs.microsoft.com/dotnet/feed/).  
  
2. Нажмите правой кнопкой мыши на странице и выберите **Источник просмотра**.  
  
3. Копируйте текст канала, нажав **на Ctrl-A,** чтобы выбрать весь текст, и **Ctrl'C** для копирования.  
  
### <a name="creating-the-data-types"></a>Создание типов данных  
  
1. Откройте файл кода, в котором будет использоваться прокси. Этот файл должен быть частью проекта .NET Framework 4.5.  
  
2. Поместите курсор в такое место в файле, чтобы он был вне пределов описанных в файле классов.  
  
3. Выберите **Edit,** **Паста Специальный**, **Вставить XML как классы**.  
  
4. Классы `link` `rss`под `rssChannel` `rssChannelImage`названием , , , `rssChannelItem` и `rssChannelItemGuid` создаются с необходимыми членами для доступа к элементам в RSS канал.  
  
### <a name="using-the-generated-classes"></a>Использование созданных классов  
  
1. После создания классов их можно использовать в коде так же, как и любые другие классы. В следующем примере кода показана инициализация нового экземпляра класса `rssChannelImage`.  
  
    ```csharp
    var channelImage = new rssChannelImage()
    {
        title = "MyImage",
        link = "http://www.contoso.com/images/channelImage.jpg",
        url = "http://www.contoso.com/entries/myEntry.html"
    };  
    ```
