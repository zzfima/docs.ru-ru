---
title: Расширяемость синдикации
ms.date: 03/30/2017
ms.assetid: 4d941175-74a2-4b15-81b3-086e8a95d25f
ms.openlocfilehash: eaa3c3644dc6ad6a749a24051064b04bfa43e284
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54705888"
---
# <a name="syndication-extensibility"></a>Расширяемость синдикации
API синдикации предназначен для обеспечения независимой от формата модели программирования, которая позволяет передавать сводный контент по каналам связи в различных форматах. Абстрактная модель данных состоит из следующих классов:  
  
-   <xref:System.ServiceModel.Syndication.SyndicationCategory>  
  
-   <xref:System.ServiceModel.Syndication.SyndicationFeed>  
  
-   <xref:System.ServiceModel.Syndication.SyndicationItem>  
  
-   <xref:System.ServiceModel.Syndication.SyndicationLink>  
  
-   <xref:System.ServiceModel.Syndication.SyndicationPerson>  
  
 Эти классы тесно сопоставлены с конструкциями, определенными в спецификации Atom 1.0, хотя некоторые имена различаются.  
  
 Ключевой особенностью протоколов синдикации является их расширяемость. Оба протокола, Atom 1.0 и RSS 2.0, добавляют в RSS-каналы атрибуты и элементы, не определенные в спецификациях. Модель программирования синдикации Windows Communication Foundation (WCF) предоставляет следующие способы работы с настраиваемыми атрибутами и расширениями, использования слабо типизированного доступа и создания нового производного класса.  
  
## <a name="loosely-typed-access"></a>Слабо типизированный доступ  
 Чтобы добавить расширения путем создания нового производного класса, требуется написать дополнительный код. Другим вариантом является слабо типизированный доступ к расширениям. Все типы, определенные в абстрактной модели данных синдикации, содержат свойства `AttributeExtensions` и `ElementExtensions` (с одним исключением - <xref:System.ServiceModel.Syndication.SyndicationContent> имеет свойство `AttributeExtensions`, но не имеет свойства `ElementExtensions`). Эти свойства представляют собой коллекции расширений, не обрабатываемых методами `TryParseAttribute` и `TryParseElement` соответственно. Доступ к этим необработанным расширениям можно получить, вызвав метод <xref:System.ServiceModel.Syndication.SyndicationElementExtensionCollection.ReadElementExtensions%2A?displayProperty=nameWithType> для свойства `ElementExtensions` классов <xref:System.ServiceModel.Syndication.SyndicationFeed>, <xref:System.ServiceModel.Syndication.SyndicationItem>, <xref:System.ServiceModel.Syndication.SyndicationLink>, <xref:System.ServiceModel.Syndication.SyndicationPerson> и <xref:System.ServiceModel.Syndication.SyndicationCategory>. Этот набор методов находит все расширения с указанными именем и пространством имен, индивидуально десериализует их в экземпляры `TExtension` и возвращает в виде коллекции объектов `TExtension`.  
  
## <a name="deriving-a-new-class"></a>Создание нового производного класса  
 Новый производный класс можно создать на основе любого существующего класса абстрактной модели данных. Используйте это при реализации приложения, в котором большинство веб-каналов, с которыми вы работаете, имеют определенное расширение. В данном разделе большинство веб-каналов, с которыми работает программа, содержат расширение `MyExtension`. Для упрощения программирования выполните следующие шаги:  
  
-   Создайте класс, который будет содержать данные приложения. В данном случае создайте класс с именем MyExtension.  
  
-   Создайте класс MyExtensionItem, наследующий от класса <xref:System.ServiceModel.Syndication.SyndicationItem>, чтобы сделать доступным для программирования свойство типа MyExtension.  
  
-   Переопределите метод <xref:System.ServiceModel.Syndication.SyndicationItem.TryParseElement%28System.Xml.XmlReader%2CSystem.String%29> класса MyExtensionItem, чтобы при считывании MyExtension присваивать значение новому экземпляру MyExtension.  
  
-   Переопределите метод <xref:System.ServiceModel.Syndication.SyndicationItem.WriteElementExtensions%28System.Xml.XmlWriter%2CSystem.String%29> класса MyExtensionItem, чтобы записывать содержимое свойства MyExtension в средство записи XML.  
  
-   Создайте класс MyExtensionFeed, наследующий от класса <xref:System.ServiceModel.Syndication.SyndicationFeed>.  
  
-   Переопределите метод <xref:System.ServiceModel.Syndication.SyndicationFeed.CreateItem> класса MyExtensionFeed, чтобы он присваивал значение MyExtensionItem, а не значение по умолчанию <xref:System.ServiceModel.Syndication.SyndicationItem>. В классах <xref:System.ServiceModel.Syndication.SyndicationFeed> и <xref:System.ServiceModel.Syndication.SyndicationItem> определен ряд методов, которые могут создавать объекты <xref:System.ServiceModel.Syndication.SyndicationLink>, <xref:System.ServiceModel.Syndication.SyndicationCategory> и <xref:System.ServiceModel.Syndication.SyndicationPerson> (например, <xref:System.ServiceModel.Syndication.SyndicationFeed.CreateLink>, <xref:System.ServiceModel.Syndication.SyndicationFeed.CreateCategory> и <xref:System.ServiceModel.Syndication.SyndicationFeed.CreatePerson>). Любой из этих методов может быть переопределен для создания пользовательского производного класса.  
  
## <a name="see-also"></a>См. также
- [Общие сведения о синдикации WCF](../../../../docs/framework/wcf/feature-details/wcf-syndication-overview.md)
- [Архитектура синдикации](../../../../docs/framework/wcf/feature-details/architecture-of-syndication.md)
