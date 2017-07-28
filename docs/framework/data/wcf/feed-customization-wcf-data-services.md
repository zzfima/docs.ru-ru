---
title: "Настройка каналов (службы данных WCF) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-oob"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Службы данных WCF, веб-каналы"
  - "Службы данных WCF, протокол Atom"
  - "Atom Publishing Protocol [Службы данных WCF]"
  - "Службы данных WCF, Настройка каналов"
ms.assetid: 0d1a39bc-6462-4683-bd7d-e74e0fd28a85
caps.latest.revision: 11
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 11
---
# Настройка каналов (службы данных WCF)
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]использует [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] для предоставления данных в виде канала. [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]поддерживает форматы Atom и нотации объектов JavaScript (JSON) для каналов данных. При использовании канала Atom [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] предоставляет стандартный метод сериализации данных, таких как сущности и связи в формате XML, которое может быть включено в тексте HTTP-сообщения. [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]Определяет свойства сущности сопоставление по умолчанию между данными, содержащимися в сущностях и элементах Atom. Дополнительные сведения см. в разделе [OData: формат Atom](http://go.microsoft.com/fwlink/?LinkID=185794).  
  
 Возможна ситуация, когда требуется сериализация данных свойства, возвращаемых службой данных, в настраиваемом виде, а не в стандартном формате канала. С [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)], можно настроить сериализацию в канале данных, чтобы свойства сущности сопоставлялись с неиспользуемыми элементами и атрибутами сущности или с пользовательскими элементами записи в канал.  
  
> [!NOTE]
>  Настройка канала поддерживается только для каналов Atom. Специализированные каналы не возвращаются при запросе в формате JSON.  
  
 С помощью [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] можно определить альтернативное сопоставление «сущность-свойство» для полезных данных канала Atom путем применения атрибутов к типам сущностей в модели данных вручную. Поставщик источника данных службы данных определяет метод применения этих атрибутов.  
  
> [!IMPORTANT]
>  При определении специализированных каналов необходимо убедиться, что все свойства сущности, которые имеют определенные пользовательские сопоставления, включены в проекцию. Если сопоставленное свойство сущности не включено в проекцию, может произойти потеря данных. Дополнительные сведения см. в разделе [проекций запросов](../../../../docs/framework/data/wcf/query-projections-wcf-data-services.md).  
  
## <a name="customizing-feeds-with-the-entity-framework-provider"></a>Настройка каналов с помощью поставщика Entity Framework  
 Модель данных, используемая с поставщиком [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)], представлена в виде XML в EDMX-файле. В данном случае атрибуты, определяющие специализированные каналы, добавляются к элементам `EntityType` и `Property`, представляющим типы сущностей и свойства в модели данных. Эти атрибуты настройки потока не определены в [ \[MC-CSDL\]: формат файла определения концептуальной схемы](http://go.microsoft.com/fwlink/?LinkId=159072), который является форматом, [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] поставщик использует для определения модели данных. Поэтому атрибуты настройки канала должны быть объявлены в специальном пространстве имен схемы, определенном как `m="http://schemas.microsoft.com/ado/2007/08/dataservices/metadata"`. Следующий фрагмент XML иллюстрирует применение атрибутов настройки канала к элементам `Property` типа сущности `Products`, определяющего свойства `ProductName`, `ReorderLevel` и `UnitsInStock`.  
  
  [Astoria пользовательские каналы #EdmFeedAttributes](../CodeSnippet/VS_Snippets_Misc/astoria custom feeds#edmfeedattributes)]  
  
 Эти атрибуты порождают следующий специализированный канал данных для набора сущностей `Products`. В данном специализированном канале данных значение свойства `ProductName` отображается как в элементе `author`, так и в свойстве `ProductName` элемента, а свойство `UnitsInStock` отображается в специализированном элементе с собственным уникальным пространством имен и со свойством `ReorderLevel` в качестве атрибута:  
  
  [Astoria пользовательские каналы #EdmFeedResultProduct](../CodeSnippet/VS_Snippets_Misc/astoria custom feeds#edmfeedresultproduct)]  
  
 Дополнительные сведения см. в разделе [Практическое руководство: Настройка каналов с поставщиком Entity Framework](../../../../docs/framework/data/wcf/how-to-customize-feeds-with-ef-provider-wcf-data-services.md).  
  
> [!NOTE]
>  Поскольку расширения модели данных не поддерживаются конструктором сущностей, необходимо вручную модифицировать XML-файл, содержащий модель данных. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]EDMX-файл, создаваемый [!INCLUDE[adonet_edm](../../../../includes/adonet-edm-md.md)] средств, в разделе [.edmx Обзор файла](http://msdn.microsoft.com/ru-ru/f4c8e7ce-1db6-417e-9759-15f8b55155d4).  
  
### <a name="custom-feed-attributes"></a>Настраиваемые атрибуты канала  
 В следующей таблице приведены XML-атрибуты, с помощью которых можно настроить каналы, добавляемые в язык определения концептуальной схемы (CSDL) с определением модели данных. Эти атрибуты эквивалентны свойствам <xref:System.Data.Services.Common.EntityPropertyMappingAttribute> использования с поставщиком отражения.  
  
|Имя атрибута|Описание|  
|--------------------|-----------------|  
|`FC_ContentKind`|Указывает тип содержимого. Следующие ключевые слова определяют типы содержимого синдикации.<br /><br /> `text:`Значение свойства отображается в канале как текст.<br /><br /> `html:`Значение свойства отображается в канале как HTML.<br /><br /> `xhtml:`Значение свойства отображается в канале как HTML-текст в формате XML.<br /><br /> Эти ключевые слова эквивалентны значениям <xref:System.Data.Services.Common.SyndicationTextContentKind> перечисление, используемое с поставщиком отражения.<br /><br /> Этот атрибут не поддерживается, если используются атрибуты `FC_NsPrefix` и `FC_NsUri`.<br /><br /> Если задается значение `xhtml` для атрибута `FC_ContentKind`, то необходимо убедиться, что значение свойства содержит XML в правильном формате. Служба данных возвращает значение, не выполняя никаких преобразований. Необходимо также убедиться, что префиксы элементов XML в возвращаемом XML имеют URI-код пространства имен и префикс, определенный в сопоставленном канале.|  
|`FC_KeepInContent`|Указывает, что значение упомянутого свойства должно быть включено как в раздел содержимого канала, так и в сопоставленное расположение. Допустимые значения: `true` и `false`. Чтобы результирующий канал обратной совместимостью с более ранними версиями [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)], укажите значение `true` чтобы убедиться в том, что значение включено в раздел содержимого канала.|  
|`FC_NsPrefix`|Префикс пространства имен элемента XML в сопоставлении, не включенном в синдикацию. Этот атрибут должен быть использован с атрибутом `FC_NsUri` и не может быть использован с атрибутом `FC_ContentKind`.|  
|`FC_NsUri`|URI пространства имен элемента XML в сопоставлении, не включенном в синдикацию. Этот атрибут должен быть использован с атрибутом `FC_NsPrefix` и не может быть использован с атрибутом `FC_ContentKind`.|  
|`FC_SourcePath`|Путь свойства сущности, к которой применяется данное правило сопоставления. Этот атрибут поддерживается только при использовании в элементе `EntityType`.<br /><br /> <xref:System.Data.Services.Common.EntityPropertyMappingAttribute.SourcePath%2A> свойства нельзя напрямую ссылаться на сложный тип. Для сложных типов необходимо использовать выражение пути, свойства в котором разделены символом косой черты (`/`). Например, следующие значения допустимы для типа сущности `Person` с целочисленным свойством `Age` и сложным свойством<br /><br /> `Address`:<br /><br /> `Age`<br /><br /> `Address/Street`<br /><br /> <xref:System.Data.Services.Common.EntityPropertyMappingAttribute.SourcePath%2A> свойство не может быть присвоено значение, содержащее пробел или любой символ, недопустимый в имени свойства.|  
|`FC_TargetPath`|Имя целевого элемента результирующего канала, с которым сопоставляется данное свойство. Этот элемент может быть элементом, определенным в спецификации Atom, либо специализированным элементом.<br /><br /> Следующие ключевые слова соответствуют стандартным значениям целевых путей синдикации, указывающим на конкретные расположения в канале [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)].<br /><br /> `SyndicationAuthorEmail:``atom:email` Дочерний элемент элемента `atom:author` элемент.<br /><br /> `SyndicationAuthorName:``atom:name` Дочерний элемент элемента `atom:author` элемент.<br /><br /> `SyndicationAuthorUri:``atom:uri` Дочерний элемент элемента `atom:author` элемент.<br /><br /> `SyndicationContributorEmail:``atom:email` Дочерний элемент элемента `atom:contributor` элемент.<br /><br /> `SyndicationContributorName:``atom:name` Дочерний элемент элемента `atom:contributor` элемент.<br /><br /> `SyndicationContributorUri:``atom:uri` Дочерний элемент элемента `atom:contributor` элемент.<br /><br /> `SyndicationCustomProperty:`Элемент пользовательского свойства. При сопоставлении с пользовательским элементом целевой объект должен быть выражением пути, в котором вложенные элементы разделяются обратной косой чертой (`/`), а атрибуты определяются амперсандом (`@`). В следующем примере строка `UnitsInStock/@ReorderLevel` сопоставляет значение свойства с атрибутом с именем `ReorderLevel` у обозначенного именем `UnitsInStock` дочернего элемента корневого элемента entry.<br /><br /> `<Property Name="ReorderLevel" Type="Int16"               m:FC_TargetPath="UnitsInStock/@ReorderLevel"               m:FC_NsPrefix="Northwind"               m:FC_NsUri="http://schemas.examples.microsoft.com/dataservices"               m:FC_KeepInContent="false"               />`<br /><br /> Если целью является имя специализированного элемента, необходимо также задать атрибуты `FC_NsPrefix` и `FC_NsUri`.<br /><br /> `SyndicationPublished:``atom:published` Элемент.<br /><br /> `SyndicationRights:``atom:rights` Элемент.<br /><br /> `SyndicationSummary:``atom:summary` Элемент.<br /><br /> `SyndicationTitle:``atom:title` Элемент.<br /><br /> `SyndicationUpdated:``atom:updated` Элемент.<br /><br /> Эти ключевые слова эквивалентны значениям <xref:System.Data.Services.Common.SyndicationItemProperty> перечисление, используемое с поставщиком отражения.|  
  
> [!NOTE]
>  В именах и значениях атрибутов учитывается регистр. Атрибуты можно применять либо к элементу `EntityType`, либо к одному или нескольким элементам `Property`, но не к тем и другим одновременно.  
  
## <a name="customizing-feeds-with-the-reflection-provider"></a>Настройка каналов с помощью поставщика отражения  
 Для настройки каналов в модели данных, реализованной с помощью поставщика отражения, добавьте один или несколько экземпляров <xref:System.Data.Services.Common.EntityPropertyMappingAttribute> атрибута к классам, которые представляют типы сущностей в модели данных. Свойства <xref:System.Data.Services.Common.EntityPropertyMappingAttribute> класса соответствуют атрибутам настройки канала, описанных в предыдущем разделе. Следующий пример иллюстрирует объявление типа `Order` с сопоставлением специализированного канала, определенным для обоих свойств.  
  
> [!NOTE]
>  Модель данных, в этом примере определяется в разделе [Практическое руководство: создание службы данных с помощью поставщика отражения](../../../../docs/framework/data/wcf/create-a-data-service-using-rp-wcf-data-services.md).  
  
  [Astoria пользовательские каналы #CustomOrderFeed](../CodeSnippet/VS_Snippets_Misc/astoria custom feeds#customorderfeed)]  
  
 Эти атрибуты порождают следующий специализированный канал данных для набора сущностей `Orders`. В этом специализированном канале, `OrderId`значение свойства отображается только в `title` элемент `entry` и `Customer` значение свойства отображается как в `author` элемент и `Customer` свойство элемента:  
  
  [Astoria пользовательские каналы #IQueryableFeedResult](../CodeSnippet/VS_Snippets_Misc/astoria custom feeds#iqueryablefeedresult)]  
  
 Дополнительные сведения см. в разделе [Практическое руководство: Настройка каналов с поставщиком отражения](../../../../docs/framework/data/wcf/how-to-customize-feeds-with-the-reflection-provider-wcf-data-services.md).  
  
## <a name="customizing-feeds-with-a-custom-data-service-provider"></a>Настройка каналов с помощью специализированного поставщика служб данных  
 Настройка каналов для модели данных, определенной с помощью пользовательского поставщика службы данных определяется для типа ресурса путем вызова <xref:System.Data.Services.Providers.ResourceType.AddEntityPropertyMappingAttribute%2A> на <xref:System.Data.Services.Providers.ResourceType> , который представляет тип сущности в модели данных. Дополнительные сведения см. в разделе [специализированные поставщики служб данных](../../../../docs/framework/data/wcf/custom-data-service-providers-wcf-data-services.md).  
  
## <a name="consuming-custom-feeds"></a>Использование специализированных каналов  
 Если приложение напрямую использует [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] канала, он должен иметь доступ для обработки любого специализированными элементами и атрибутами возвращенного канала. При реализации специализированных каналов в модели данных, независимо от поставщика службы данных, конечная точка `$metadata` возвращает сведения о специализированном канале в виде атрибутов специализированного канала в формате CSDL. При использовании **Add Service Reference** диалогового окна или [datasvcutil.exe](../../../../docs/framework/data/wcf/wcf-data-service-client-utility-datasvcutil-exe.md) инструмент для создания клиентских классов службы данных, атрибуты специализированного канала используются, чтобы гарантировать правильность обработки запросов и ответов службы данных.  
  
## <a name="feed-customization-considerations"></a>Рекомендации по настройке канала  
 При определении пользовательских сопоставлений канала необходимо учитывать следующее.  
  
-   Клиент [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] рассматривает сопоставленные элементы в канале как пустые, если они содержат только пробел. Поэтому сопоставленные элементы, которые содержат только пробел, не материализуются клиентом с применением того же пробела. Для сохранения пробела клиентом необходимо присвоить параметру `KeepInContext` значение `true` в атрибуте сопоставления канала.  
  
## <a name="versioning-requirements"></a>Требования к управлению версиями  
 При настройке канала предъявляются следующие требования к управлению версиями протокола [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]:  
  
-   Для настройки канала требуется, чтобы и клиент, и служба данных поддерживали версию 2.0 протокола [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] и последующие версии.  
  
 Дополнительные сведения см. в разделе [управление версиями службы данных](../../../../docs/framework/data/wcf/data-service-versioning-wcf-data-services.md).  
  
## <a name="see-also"></a>См. также  
 [Поставщик отражения](../../../../docs/framework/data/wcf/reflection-provider-wcf-data-services.md)   
 [Поставщик Entity Framework](../../../../docs/framework/data/wcf/entity-framework-provider-wcf-data-services.md)