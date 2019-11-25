---
title: Настройка каналов (службы данных WCF)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, feeds
- WCF Data Services, Atom protocol
- Atom Publishing Protocol [WCF Data Services]
- WCF Data Services, customizing feeds
ms.assetid: 0d1a39bc-6462-4683-bd7d-e74e0fd28a85
ms.openlocfilehash: 56c91fd1e9ea4a2e35bacbebab0f489e337cfec5
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/12/2019
ms.locfileid: "73975287"
---
# <a name="feed-customization-wcf-data-services"></a>Настройка каналов (службы данных WCF)
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] использует Open Data Protocol (OData) для предоставления данных в виде веб-канала. OData поддерживает форматы Atom и нотация объектов JavaScript (JSON) для веб-каналов данных. При использовании канала Atom OData предоставляет стандартный метод сериализации данных, таких как сущности и связи, в формат XML, который можно включать в тело сообщения HTTP. OData определяет сопоставление объекта по умолчанию между данными, содержащимися в сущностях и элементах Atom. Дополнительные сведения см. в разделе [OData: формат Atom](https://go.microsoft.com/fwlink/?LinkID=185794).  
  
 Возможна ситуация, когда требуется сериализация данных свойства, возвращаемых службой данных, в настраиваемом виде, а не в стандартном формате канала. С помощью OData можно настроить сериализацию в веб-канале данных таким образом, чтобы свойства сущности могли сопоставляться с неиспользуемыми элементами и атрибутами записи или с пользовательскими элементами записи в веб-канале.  
  
> [!NOTE]
> Настройка канала поддерживается только для каналов Atom. Специализированные каналы не возвращаются при запросе в формате JSON.  
  
 С помощью [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] можно определить альтернативное сопоставление «сущность-свойство» для полезных данных канала Atom путем применения атрибутов к типам сущностей в модели данных вручную. Поставщик источника данных службы данных определяет метод применения этих атрибутов.  
  
> [!IMPORTANT]
> При определении специализированных каналов необходимо убедиться, что все свойства сущности, которые имеют определенные пользовательские сопоставления, включены в проекцию. Если сопоставленное свойство сущности не включено в проекцию, может произойти потеря данных. Дополнительные сведения см. в разделе [проекции запросов](query-projections-wcf-data-services.md).  
  
## <a name="customizing-feeds-with-the-entity-framework-provider"></a>Настройка каналов с помощью поставщика Entity Framework  
 Модель данных, используемая поставщиком Entity Framework, представлена в виде XML в EDMX-файле. В данном случае атрибуты, определяющие специализированные каналы, добавляются к элементам `EntityType` и `Property`, представляющим типы сущностей и свойства в модели данных. Эти атрибуты настройки канала не определены в [\[MC-CSDL\]: формат файла определения концептуальной схемы](https://go.microsoft.com/fwlink/?LinkId=159072), который используется поставщиком Entity Framework для определения модели данных. Поэтому атрибуты настройки канала должны быть объявлены в специальном пространстве имен схемы, определенном как `m="http://schemas.microsoft.com/ado/2007/08/dataservices/metadata"`. Следующий фрагмент XML иллюстрирует применение атрибутов настройки канала к элементам `Property` типа сущности `Products`, определяющего свойства `ProductName`, `ReorderLevel` и `UnitsInStock`.  
  
 [!code-xml[Astoria Custom Feeds#EdmFeedAttributes](../../../../samples/snippets/xml/VS_Snippets_Misc/astoria_custom_feeds/xml/northwind.csdl#edmfeedattributes)]  
  
 Эти атрибуты порождают следующий специализированный канал данных для набора сущностей `Products`. В данном специализированном канале данных значение свойства `ProductName` отображается как в элементе `author`, так и в свойстве `ProductName` элемента, а свойство `UnitsInStock` отображается в специализированном элементе с собственным уникальным пространством имен и со свойством `ReorderLevel` в качестве атрибута:  
  
 [!code-xml[Astoria Custom Feeds#EdmFeedResultProduct](../../../../samples/snippets/xml/VS_Snippets_Misc/astoria_custom_feeds/xml/edmfeedresult.xml#edmfeedresultproduct)]  
  
 Дополнительные сведения см. в разделе [руководство. Настройка каналов с помощью поставщика Entity Framework](how-to-customize-feeds-with-ef-provider-wcf-data-services.md).  
  
> [!NOTE]
> Поскольку расширения модели данных не поддерживаются конструктором сущностей, необходимо вручную модифицировать XML-файл, содержащий модель данных. Дополнительные сведения о EDMX-файле, создаваемом инструментами EDM, см. в разделе [Общие сведения о файле EDMX (Entity Framework)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100)).  
  
### <a name="custom-feed-attributes"></a>Настраиваемые атрибуты канала  
 В следующей таблице приведены XML-атрибуты, с помощью которых можно настроить каналы, добавляемые в язык определения концептуальной схемы (CSDL) с определением модели данных. Эти атрибуты эквивалентны свойствам объекта <xref:System.Data.Services.Common.EntityPropertyMappingAttribute>, используемым при работе с поставщиком отражения.  
  
|Имя атрибута|Описание|  
|--------------------|-----------------|  
|`FC_ContentKind`|Указывает тип содержимого. Следующие ключевые слова определяют типы содержимого синдикации.<br /><br /> `text:` значение свойства отображается в веб-канале как текст.<br /><br /> `html:` значение свойства отображается в веб-канале как HTML.<br /><br /> `xhtml:` значение свойства отображается в веб-канале как HTML в формате XML.<br /><br /> Эти ключевые слова эквивалентны значениям перечисления <xref:System.Data.Services.Common.SyndicationTextContentKind>, используемым при работе с поставщиком отражения.<br /><br /> Этот атрибут не поддерживается, если используются атрибуты `FC_NsPrefix` и `FC_NsUri`.<br /><br /> Если задается значение `xhtml` для атрибута `FC_ContentKind`, то необходимо убедиться, что значение свойства содержит XML в правильном формате. Служба данных возвращает значение, не выполняя никаких преобразований. Необходимо также убедиться, что префиксы элементов XML в возвращаемом XML имеют URI-код пространства имен и префикс, определенный в сопоставленном канале.|  
|`FC_KeepInContent`|Указывает, что значение упомянутого свойства должно быть включено как в раздел содержимого канала, так и в сопоставленное расположение. Допустимые значения: `true` и `false`. Чтобы обеспечить обратную совместимость результирующего канала с более ранними версиями [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)], укажите значение `true`, чтобы убедиться в том, что значение включено в раздел содержимого веб-канала.|  
|`FC_NsPrefix`|Префикс пространства имен элемента XML в сопоставлении, не включенном в синдикацию. Этот атрибут должен быть использован с атрибутом `FC_NsUri` и не может быть использован с атрибутом `FC_ContentKind`.|  
|`FC_NsUri`|URI пространства имен элемента XML в сопоставлении, не включенном в синдикацию. Этот атрибут должен быть использован с атрибутом `FC_NsPrefix` и не может быть использован с атрибутом `FC_ContentKind`.|  
|`FC_SourcePath`|Путь свойства сущности, к которой применяется данное правило сопоставления. Этот атрибут поддерживается только при использовании в элементе `EntityType`.<br /><br /> Свойство <xref:System.Data.Services.Common.EntityPropertyMappingAttribute.SourcePath%2A> не может непосредственно ссылаться на сложный тип. Для сложных типов необходимо использовать выражение пути, свойства в котором разделены символом косой черты (`/`). Например, следующие значения разрешены для типа сущности `Person` с целочисленным свойством `Age` и сложным свойством.<br /><br /> `Address`.<br /><br /> `Age`<br /><br /> `Address/Street`<br /><br /> Свойству <xref:System.Data.Services.Common.EntityPropertyMappingAttribute.SourcePath%2A> нельзя задать значение, содержащее пробел или любой символ, недопустимый в имени свойства.|  
|`FC_TargetPath`|Имя целевого элемента результирующего канала, с которым сопоставляется данное свойство. Этот элемент может быть элементом, определенным в спецификации Atom, либо специализированным элементом.<br /><br /> Следующие ключевые слова — это стандартные значения целевого пути синдикации, указывающие на определенное расположение в веб-канале OData.<br /><br /> `SyndicationAuthorEmail:` `atom:email` дочерний элемент элемента `atom:author`.<br /><br /> `SyndicationAuthorName:` `atom:name` дочерний элемент элемента `atom:author`.<br /><br /> `SyndicationAuthorUri:` `atom:uri` дочерний элемент элемента `atom:author`.<br /><br /> `SyndicationContributorEmail:` `atom:email` дочерний элемент элемента `atom:contributor`.<br /><br /> `SyndicationContributorName:` `atom:name` дочерний элемент элемента `atom:contributor`.<br /><br /> `SyndicationContributorUri:` `atom:uri` дочерний элемент элемента `atom:contributor`.<br /><br /> `SyndicationCustomProperty:` настраиваемого элемента свойства. При сопоставлении с пользовательским элементом целевой объект должен быть выражением пути, в котором вложенные элементы разделяются обратной косой чертой (`/`), а атрибуты определяются амперсандом (`@`). В следующем примере строка `UnitsInStock/@ReorderLevel` сопоставляет значение свойства с атрибутом с именем `ReorderLevel` у обозначенного именем `UnitsInStock` дочернего элемента корневого элемента entry.<br /><br /> `<Property Name="ReorderLevel" Type="Int16"               m:FC_TargetPath="UnitsInStock/@ReorderLevel"               m:FC_NsPrefix="Northwind"               m:FC_NsUri="http://schemas.examples.microsoft.com/dataservices"               m:FC_KeepInContent="false"               />`<br /><br /> Если целью является имя специализированного элемента, необходимо также задать атрибуты `FC_NsPrefix` и `FC_NsUri`.<br /><br /> `SyndicationPublished:` элемент `atom:published`.<br /><br /> `SyndicationRights:` элемент `atom:rights`.<br /><br /> `SyndicationSummary:` элемент `atom:summary`.<br /><br /> `SyndicationTitle:` элемент `atom:title`.<br /><br /> `SyndicationUpdated:` элемент `atom:updated`.<br /><br /> Эти ключевые слова эквивалентны значениям перечисления <xref:System.Data.Services.Common.SyndicationItemProperty>, используемым при работе с поставщиком отражения.|  
  
> [!NOTE]
> В именах и значениях атрибутов учитывается регистр. Атрибуты можно применять либо к элементу `EntityType`, либо к одному или нескольким элементам `Property`, но не к тем и другим одновременно.  
  
## <a name="customizing-feeds-with-the-reflection-provider"></a>Настройка каналов с помощью поставщика отражения  
 Для настройки каналов в модели данных, реализованной с использованием поставщика отражения, добавьте один или несколько экземпляров атрибута <xref:System.Data.Services.Common.EntityPropertyMappingAttribute> к классам, представляющим типы сущностей в модели данных. Свойства класса <xref:System.Data.Services.Common.EntityPropertyMappingAttribute> соответствуют атрибутам настройки канала, описанным в предыдущем разделе. Следующий пример иллюстрирует объявление типа `Order` с сопоставлением специализированного канала, определенным для обоих свойств.  
  
> [!NOTE]
> Модель данных для этого примера определяется в разделе [как создать службу данных с помощью поставщика отражения](create-a-data-service-using-rp-wcf-data-services.md).  
  
 [!code-csharp[Astoria Custom Feeds#CustomOrderFeed](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_custom_feeds/cs/orderitems.svc.cs#customorderfeed)]
 [!code-vb[Astoria Custom Feeds#CustomOrderFeed](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_custom_feeds/vb/orderitems.svc.vb#customorderfeed)]  
  
 Эти атрибуты порождают следующий специализированный канал данных для набора сущностей `Orders`. В этом настроенном канале значение свойства `OrderId` отображается только в `title` элементе `entry`, а значение свойства `Customer` отображается как в элементе `author`, так и в качестве элемента свойства `Customer`:  
  
 [!code-xml[Astoria Custom Feeds#IQueryableFeedResult](../../../../samples/snippets/xml/VS_Snippets_Misc/astoria_custom_feeds/xml/iqueryablefeedresult.xml#iqueryablefeedresult)]  
  
 Дополнительные сведения см. в разделе [инструкции. Настройка веб-каналов с помощью поставщика отражения](how-to-customize-feeds-with-the-reflection-provider-wcf-data-services.md).  
  
## <a name="customizing-feeds-with-a-custom-data-service-provider"></a>Настройка каналов с помощью специализированного поставщика служб данных  
 Настройка каналов для модели данных, определенной с использованием специализированного поставщика служб данных, осуществляется для типа ресурса путем вызова метода <xref:System.Data.Services.Providers.ResourceType.AddEntityPropertyMappingAttribute%2A> для типа <xref:System.Data.Services.Providers.ResourceType>, который представляет тип сущности в модели данных. Дополнительные сведения см. в разделе [пользовательские поставщики служб данных](custom-data-service-providers-wcf-data-services.md).  
  
## <a name="consuming-custom-feeds"></a>Использование специализированных каналов  
 Когда приложение напрямую использует веб-канал OData, оно должно иметь возможность обрабатывать любые настраиваемые элементы и атрибуты в возвращенном веб-канале. При реализации специализированных каналов в модели данных, независимо от поставщика службы данных, конечная точка `$metadata` возвращает сведения о специализированном канале в виде атрибутов специализированного канала в формате CSDL. При использовании диалогового окна **Добавление ссылки на службу** или средства [DataSvcUtil. exe](wcf-data-service-client-utility-datasvcutil-exe.md) для создания классов клиентских служб данных настроенные атрибуты веб-канала используются для обеспечения правильной обработки запросов и ответов службы данных.  
  
## <a name="feed-customization-considerations"></a>Рекомендации по настройке канала  
 При определении пользовательских сопоставлений канала необходимо учитывать следующее.  
  
- Клиент [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] обрабатывает сопоставленные элементы в веб-канале как пустые, если они содержат только пробелы. Из-за этого сопоставленные элементы, содержащие только пробелы, не сохранятся на клиенте с одинаковыми пробелами. Чтобы сохранить это пустое пространство на клиенте, необходимо присвоить параметру `KeepInContext` значение `true` в атрибуте сопоставления веб-канала.  
  
## <a name="versioning-requirements"></a>Требования к управлению версиями  
 Настройка веб-канала имеет следующие требования к версии протокола OData:  
  
- Для настройки веб-канала требуется, чтобы служба клиента и данных поддерживала версию 2,0 протокола OData и более поздних версий.  
  
 Дополнительные сведения см. в разделе [Управление версиями службы данных](data-service-versioning-wcf-data-services.md).  
  
## <a name="see-also"></a>См. также

- [Поставщик отражений](reflection-provider-wcf-data-services.md)
- [Поставщик Entity Framework](entity-framework-provider-wcf-data-services.md)
