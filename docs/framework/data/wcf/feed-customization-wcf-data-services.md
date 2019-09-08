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
ms.openlocfilehash: b4ea05b0112af4c1dcb6308a08ab3b31c586fbe8
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70790862"
---
# <a name="feed-customization-wcf-data-services"></a>Настройка каналов (службы данных WCF)
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)][!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] использует для предоставления данных в виде веб-канала. [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]поддерживает форматы Atom и нотация объектов JavaScript (JSON) для веб-каналов данных. При использовании веб-канала [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] Atom предоставляет стандартный метод сериализации данных, таких как сущности и связи, в формат XML, который может быть добавлен в текст сообщения HTTP. [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]Определяет сопоставление по умолчанию для свойства сущности между данными, содержащимися в сущностях и элементах Atom. Дополнительные сведения см. в [разделе OData: Формат](https://go.microsoft.com/fwlink/?LinkID=185794)Atom.  
  
 Возможна ситуация, когда требуется сериализация данных свойства, возвращаемых службой данных, в настраиваемом виде, а не в стандартном формате канала. С [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]помощью можно настроить сериализацию в потоке данных таким образом, чтобы свойства сущности могли сопоставляться с неиспользуемыми элементами и атрибутами записи или с пользовательскими элементами записи в веб-канале.  
  
> [!NOTE]
> Настройка канала поддерживается только для каналов Atom. Специализированные каналы не возвращаются при запросе в формате JSON.  
  
 С помощью [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] можно определить альтернативное сопоставление «сущность-свойство» для полезных данных канала Atom путем применения атрибутов к типам сущностей в модели данных вручную. Поставщик источника данных службы данных определяет метод применения этих атрибутов.  
  
> [!IMPORTANT]
> При определении специализированных каналов необходимо убедиться, что все свойства сущности, которые имеют определенные пользовательские сопоставления, включены в проекцию. Если сопоставленное свойство сущности не включено в проекцию, может произойти потеря данных. Дополнительные сведения см. в разделе [проекции запросов](query-projections-wcf-data-services.md).  
  
## <a name="customizing-feeds-with-the-entity-framework-provider"></a>Настройка каналов с помощью поставщика Entity Framework  
 Модель данных, используемая с поставщиком [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)], представлена в виде XML в EDMX-файле. В данном случае атрибуты, определяющие специализированные каналы, добавляются к элементам `EntityType` и `Property`, представляющим типы сущностей и свойства в модели данных. Эти атрибуты настройки канала не определены в [ \[MC-CSDL\]: Формат](https://go.microsoft.com/fwlink/?LinkId=159072)файла определения концептуальной схемы — формат [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] , используемый поставщиком для определения модели данных. Поэтому атрибуты настройки канала должны быть объявлены в специальном пространстве имен схемы, определенном как `m="http://schemas.microsoft.com/ado/2007/08/dataservices/metadata"`. Следующий фрагмент XML иллюстрирует применение атрибутов настройки канала к элементам `Property` типа сущности `Products`, определяющего свойства `ProductName`, `ReorderLevel` и `UnitsInStock`.  
  
 [!code-xml[Astoria Custom Feeds#EdmFeedAttributes](../../../../samples/snippets/xml/VS_Snippets_Misc/astoria_custom_feeds/xml/northwind.csdl#edmfeedattributes)]  
  
 Эти атрибуты порождают следующий специализированный канал данных для набора сущностей `Products`. В данном специализированном канале данных значение свойства `ProductName` отображается как в элементе `author`, так и в свойстве `ProductName` элемента, а свойство `UnitsInStock` отображается в специализированном элементе с собственным уникальным пространством имен и со свойством `ReorderLevel` в качестве атрибута:  
  
 [!code-xml[Astoria Custom Feeds#EdmFeedResultProduct](../../../../samples/snippets/xml/VS_Snippets_Misc/astoria_custom_feeds/xml/edmfeedresult.xml#edmfeedresultproduct)]  
  
 Дополнительные сведения см. в разделе [Практическое руководство. Настройка веб-каналов с помощью](how-to-customize-feeds-with-ef-provider-wcf-data-services.md)поставщика Entity Framework.  
  
> [!NOTE]
> Поскольку расширения модели данных не поддерживаются конструктором сущностей, необходимо вручную модифицировать XML-файл, содержащий модель данных. Дополнительные сведения о EDMX-файле, создаваемом инструментами EDM, см. в разделе [Общие сведения о файле EDMX (Entity Framework)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100)).  
  
### <a name="custom-feed-attributes"></a>Настраиваемые атрибуты канала  
 В следующей таблице приведены XML-атрибуты, с помощью которых можно настроить каналы, добавляемые в язык определения концептуальной схемы (CSDL) с определением модели данных. Эти атрибуты эквивалентны свойствам объекта <xref:System.Data.Services.Common.EntityPropertyMappingAttribute>, используемым при работе с поставщиком отражения.  
  
|Имя атрибута|Описание|  
|--------------------|-----------------|  
|`FC_ContentKind`|Указывает тип содержимого. Следующие ключевые слова определяют типы содержимого синдикации.<br /><br /> `text:`Значение свойства отображается в веб-канале в виде текста.<br /><br /> `html:`Значение свойства отображается в веб-канале как HTML.<br /><br /> `xhtml:`Значение свойства отображается в веб-канале как HTML в формате XML.<br /><br /> Эти ключевые слова эквивалентны значениям перечисления <xref:System.Data.Services.Common.SyndicationTextContentKind>, используемым при работе с поставщиком отражения.<br /><br /> Этот атрибут не поддерживается, если используются атрибуты `FC_NsPrefix` и `FC_NsUri`.<br /><br /> Если задается значение `xhtml` для атрибута `FC_ContentKind`, то необходимо убедиться, что значение свойства содержит XML в правильном формате. Служба данных возвращает значение, не выполняя никаких преобразований. Необходимо также убедиться, что префиксы элементов XML в возвращаемом XML имеют URI-код пространства имен и префикс, определенный в сопоставленном канале.|  
|`FC_KeepInContent`|Указывает, что значение упомянутого свойства должно быть включено как в раздел содержимого канала, так и в сопоставленное расположение. Допустимые значения: `true` и `false`. Чтобы обеспечить обратную совместимость результирующего канала с более ранними [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]версиями, укажите `true` значение, чтобы убедиться, что значение включено в раздел содержимого веб-канала.|  
|`FC_NsPrefix`|Префикс пространства имен элемента XML в сопоставлении, не включенном в синдикацию. Этот атрибут должен быть использован с атрибутом `FC_NsUri` и не может быть использован с атрибутом `FC_ContentKind`.|  
|`FC_NsUri`|URI пространства имен элемента XML в сопоставлении, не включенном в синдикацию. Этот атрибут должен быть использован с атрибутом `FC_NsPrefix` и не может быть использован с атрибутом `FC_ContentKind`.|  
|`FC_SourcePath`|Путь свойства сущности, к которой применяется данное правило сопоставления. Этот атрибут поддерживается только при использовании в элементе `EntityType`.<br /><br /> Свойство <xref:System.Data.Services.Common.EntityPropertyMappingAttribute.SourcePath%2A> не может непосредственно ссылаться на сложный тип. Для сложных типов необходимо использовать выражение пути, свойства в котором разделены символом косой черты (`/`). Например, следующие значения разрешены для типа `Person` сущности с целочисленным свойством `Age` и сложным свойством.<br /><br /> `Address`:<br /><br /> `Age`<br /><br /> `Address/Street`<br /><br /> Свойству <xref:System.Data.Services.Common.EntityPropertyMappingAttribute.SourcePath%2A> нельзя задать значение, содержащее пробел или любой символ, недопустимый в имени свойства.|  
|`FC_TargetPath`|Имя целевого элемента результирующего канала, с которым сопоставляется данное свойство. Этот элемент может быть элементом, определенным в спецификации Atom, либо специализированным элементом.<br /><br /> Следующие ключевые слова соответствуют стандартным значениям целевых путей синдикации, указывающим на конкретные расположения в канале [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)].<br /><br /> `SyndicationAuthorEmail:`Дочерний элемент `atom:author`элемента. `atom:email`<br /><br /> `SyndicationAuthorName:`Дочерний элемент `atom:author`элемента. `atom:name`<br /><br /> `SyndicationAuthorUri:`Дочерний элемент `atom:author`элемента. `atom:uri`<br /><br /> `SyndicationContributorEmail:`Дочерний элемент `atom:contributor`элемента. `atom:email`<br /><br /> `SyndicationContributorName:`Дочерний элемент `atom:contributor`элемента. `atom:name`<br /><br /> `SyndicationContributorUri:`Дочерний элемент `atom:contributor`элемента. `atom:uri`<br /><br /> `SyndicationCustomProperty:`Настраиваемый элемент свойства. При сопоставлении с пользовательским элементом целевой объект должен быть выражением пути, в котором вложенные элементы разделяются обратной косой чертой (`/`), а атрибуты определяются амперсандом (`@`). В следующем примере строка `UnitsInStock/@ReorderLevel` сопоставляет значение свойства с атрибутом с именем `ReorderLevel` у обозначенного именем `UnitsInStock` дочернего элемента корневого элемента entry.<br /><br /> `<Property Name="ReorderLevel" Type="Int16"               m:FC_TargetPath="UnitsInStock/@ReorderLevel"               m:FC_NsPrefix="Northwind"               m:FC_NsUri="http://schemas.examples.microsoft.com/dataservices"               m:FC_KeepInContent="false"               />`<br /><br /> Если целью является имя специализированного элемента, необходимо также задать атрибуты `FC_NsPrefix` и `FC_NsUri`.<br /><br /> `SyndicationPublished:``atom:published` Элемент.<br /><br /> `SyndicationRights:``atom:rights` Элемент.<br /><br /> `SyndicationSummary:``atom:summary` Элемент.<br /><br /> `SyndicationTitle:``atom:title` Элемент.<br /><br /> `SyndicationUpdated:``atom:updated` Элемент.<br /><br /> Эти ключевые слова эквивалентны значениям перечисления <xref:System.Data.Services.Common.SyndicationItemProperty>, используемым при работе с поставщиком отражения.|  
  
> [!NOTE]
> В именах и значениях атрибутов учитывается регистр. Атрибуты можно применять либо к элементу `EntityType`, либо к одному или нескольким элементам `Property`, но не к тем и другим одновременно.  
  
## <a name="customizing-feeds-with-the-reflection-provider"></a>Настройка каналов с помощью поставщика отражения  
 Для настройки каналов в модели данных, реализованной с использованием поставщика отражения, добавьте один или несколько экземпляров атрибута <xref:System.Data.Services.Common.EntityPropertyMappingAttribute> к классам, представляющим типы сущностей в модели данных. Свойства класса <xref:System.Data.Services.Common.EntityPropertyMappingAttribute> соответствуют атрибутам настройки канала, описанным в предыдущем разделе. Следующий пример иллюстрирует объявление типа `Order` с сопоставлением специализированного канала, определенным для обоих свойств.  
  
> [!NOTE]
> Модель данных для этого примера определяется в разделе [как: Создание службы данных с помощью поставщика](create-a-data-service-using-rp-wcf-data-services.md)отражения.  
  
 [!code-csharp[Astoria Custom Feeds#CustomOrderFeed](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_custom_feeds/cs/orderitems.svc.cs#customorderfeed)]
 [!code-vb[Astoria Custom Feeds#CustomOrderFeed](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_custom_feeds/vb/orderitems.svc.vb#customorderfeed)]  
  
 Эти атрибуты порождают следующий специализированный канал данных для набора сущностей `Orders`. В этом настроенном канале `OrderId` значение свойства отображается только `title` в `Customer` элементе `entry` , `author` а значение свойства отображается как в элементе, так и в качестве `Customer` элемента свойства:  
  
 [!code-xml[Astoria Custom Feeds#IQueryableFeedResult](../../../../samples/snippets/xml/VS_Snippets_Misc/astoria_custom_feeds/xml/iqueryablefeedresult.xml#iqueryablefeedresult)]  
  
 Дополнительные сведения см. в разделе [Практическое руководство. Настройка веб-каналов с помощью](how-to-customize-feeds-with-the-reflection-provider-wcf-data-services.md)поставщика отражения.  
  
## <a name="customizing-feeds-with-a-custom-data-service-provider"></a>Настройка каналов с помощью специализированного поставщика служб данных  
 Настройка каналов для модели данных, определенной с использованием специализированного поставщика служб данных, осуществляется для типа ресурса путем вызова метода <xref:System.Data.Services.Providers.ResourceType.AddEntityPropertyMappingAttribute%2A> для типа <xref:System.Data.Services.Providers.ResourceType>, который представляет тип сущности в модели данных. Дополнительные сведения см. в разделе [пользовательские поставщики служб данных](custom-data-service-providers-wcf-data-services.md).  
  
## <a name="consuming-custom-feeds"></a>Использование специализированных каналов  
 Когда приложение непосредственно использует [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] веб-канал, оно должно иметь возможность обрабатывать любые настраиваемые элементы и атрибуты в возвращенном веб-канале. При реализации специализированных каналов в модели данных, независимо от поставщика службы данных, конечная точка `$metadata` возвращает сведения о специализированном канале в виде атрибутов специализированного канала в формате CSDL. При использовании диалогового окна **Добавление ссылки на службу** или средства [DataSvcUtil. exe](wcf-data-service-client-utility-datasvcutil-exe.md) для создания классов клиентских служб данных настроенные атрибуты веб-канала используются для обеспечения правильной обработки запросов и ответов службы данных.  
  
## <a name="feed-customization-considerations"></a>Рекомендации по настройке канала  
 При определении пользовательских сопоставлений канала необходимо учитывать следующее.  
  
- [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] Клиент считает сопоставленные элементы в веб-канале пустыми, если они содержат только пробелы. Из-за этого сопоставленные элементы, содержащие только пробелы, не сохранятся на клиенте с одинаковыми пробелами. Чтобы сохранить это пустое пространство на клиенте, необходимо присвоить параметру `true` значение `KeepInContext` в атрибуте сопоставления веб-канала.  
  
## <a name="versioning-requirements"></a>Требования к управлению версиями  
 При настройке канала предъявляются следующие требования к управлению версиями протокола [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]:  
  
- Для настройки канала требуется, чтобы и клиент, и служба данных поддерживали версию 2.0 протокола [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] и последующие версии.  
  
 Дополнительные сведения см. в разделе [Управление версиями службы данных](data-service-versioning-wcf-data-services.md).  
  
## <a name="see-also"></a>См. также

- [Поставщик отражений](reflection-provider-wcf-data-services.md)
- [Поставщик Entity Framework](entity-framework-provider-wcf-data-services.md)
