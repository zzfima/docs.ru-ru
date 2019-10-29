---
title: Спецификация манифеста поставщика
ms.date: 03/30/2017
ms.assetid: bb450b47-8951-4f99-9350-26f05a4d4e46
ms.openlocfilehash: bef4868ccc52d287baaceca32c4943723be7531f
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2019
ms.locfileid: "73040493"
---
# <a name="provider-manifest-specification"></a><span data-ttu-id="ddb91-102">Спецификация манифеста поставщика</span><span class="sxs-lookup"><span data-stu-id="ddb91-102">Provider Manifest Specification</span></span>
<span data-ttu-id="ddb91-103">В этом разделе описывается поддержка типов и функций в хранилище данных, представляемая поставщиком хранилища данных.</span><span class="sxs-lookup"><span data-stu-id="ddb91-103">This section discusses how a data store provider can support the types and functions in the data store.</span></span>  
  
 <span data-ttu-id="ddb91-104">Службы сущностей работают независимо от поставщика хранилища данных, однако позволяют поставщику явно определять порядок взаимодействия моделей, сопоставлений и запросов с базовым хранилищем данных.</span><span class="sxs-lookup"><span data-stu-id="ddb91-104">Entity Services operates independently of a specific data store provider yet still allows a data provider to explicitly define how models, mappings, and queries interact with an underlying data store.</span></span> <span data-ttu-id="ddb91-105">Без реализованного уровня абстракции службы сущностей могли бы работать только с поставщиком данных или хранилищем данных определенного типа.</span><span class="sxs-lookup"><span data-stu-id="ddb91-105">Without a layer of abstraction, Entity Services could only be targeted at a specific data store or data provider.</span></span>  
  
 <span data-ttu-id="ddb91-106">Типы, поддерживаемые поставщиком, явно или неявно поддерживаются базовой базой данных.</span><span class="sxs-lookup"><span data-stu-id="ddb91-106">Types that the provider supports are directly or indirectly supported by the underlying database.</span></span> <span data-ttu-id="ddb91-107">Эти типы необязательно являются типами хранения, но типы, которые поставщик использует для поддержки Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="ddb91-107">These types are not necessarily the exact store types, but the types the provider uses to support the Entity Framework.</span></span> <span data-ttu-id="ddb91-108">Типы поставщика и хранилища описываются в терминах модели EDM.</span><span class="sxs-lookup"><span data-stu-id="ddb91-108">Provider/store types are described in the Entity Data Model (EDM) terms.</span></span>  
  
 <span data-ttu-id="ddb91-109">Типы параметров и возвращаемых значений для функций, поддерживаемые хранилищем данных, выражаются в терминах модели EDM.</span><span class="sxs-lookup"><span data-stu-id="ddb91-109">Parameter and return types for the functions supported by the data store are specified in EDM terms.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ddb91-110">Требования</span><span class="sxs-lookup"><span data-stu-id="ddb91-110">Requirements</span></span>  
 <span data-ttu-id="ddb91-111">Entity Framework и хранилище данных должны иметь возможность передавать данные назад и вперед в известных типах без потери данных или усечения.</span><span class="sxs-lookup"><span data-stu-id="ddb91-111">The Entity Framework and the data store need to be able to pass data back and forth in known types without any data loss or truncation.</span></span>  
  
 <span data-ttu-id="ddb91-112">Манифест поставщика должен загружаться средствами во время разработки без необходимости установления соединения с хранилищем данных.</span><span class="sxs-lookup"><span data-stu-id="ddb91-112">The provider manifest must be loadable by tools at design time without having to open a connection to the data store.</span></span>  
  
 <span data-ttu-id="ddb91-113">Entity Framework учитывается регистр, но базовое хранилище данных может быть недоступно.</span><span class="sxs-lookup"><span data-stu-id="ddb91-113">The Entity Framework is case sensitive, but the underlying data store may not be.</span></span> <span data-ttu-id="ddb91-114">Если артефакты модели EDM (например, идентификаторы и имена типов) определены и используются в манифесте, они должны использовать Entity Framework учет регистра.</span><span class="sxs-lookup"><span data-stu-id="ddb91-114">When EDM artifacts (identifiers and type names, for example) are defined and used in the manifest, they must use the Entity Framework case sensitivity.</span></span> <span data-ttu-id="ddb91-115">Если в манифесте поставщика встречаются элементы хранилища данных, в которых может учитываться регистр, то в манифесте поставщика необходимо сохранять регистр.</span><span class="sxs-lookup"><span data-stu-id="ddb91-115">If data store elements that may be case sensitive appear in the provider manifest, that casing needs to be maintained in the provider manifest.</span></span>  
  
 <span data-ttu-id="ddb91-116">Entity Framework требуется манифест поставщика для всех поставщиков данных.</span><span class="sxs-lookup"><span data-stu-id="ddb91-116">The Entity Framework requires a provider manifest for all data providers.</span></span> <span data-ttu-id="ddb91-117">При попытке использовать поставщик, не имеющий манифеста поставщика с Entity Framework, возникнет ошибка.</span><span class="sxs-lookup"><span data-stu-id="ddb91-117">If you try to use a provider that does not have a provider manifest with the Entity Framework, you will get an error.</span></span>  
  
 <span data-ttu-id="ddb91-118">В следующей таблице описаны виды исключений, которые будут выдаваться Entity Framework при возникновении исключений при взаимодействии с поставщиком.</span><span class="sxs-lookup"><span data-stu-id="ddb91-118">The following table describes the kinds of exceptions the Entity Framework would throw when exceptions arise through provider interaction:</span></span>  
  
|<span data-ttu-id="ddb91-119">Проблемы</span><span class="sxs-lookup"><span data-stu-id="ddb91-119">Issue</span></span>|<span data-ttu-id="ddb91-120">Исключение</span><span class="sxs-lookup"><span data-stu-id="ddb91-120">Exception</span></span>|  
|-----------|---------------|  
|<span data-ttu-id="ddb91-121">Поставщик не поддерживает GetProviderManifest в DbProviderServices.</span><span class="sxs-lookup"><span data-stu-id="ddb91-121">The Provider does not support GetProviderManifest in DbProviderServices.</span></span>|<span data-ttu-id="ddb91-122">ProviderIncompatibleException</span><span class="sxs-lookup"><span data-stu-id="ddb91-122">ProviderIncompatibleException</span></span>|  
|<span data-ttu-id="ddb91-123">Отсутствует манифест поставщика: поставщик возвращает значение `null` при попытке получить манифест поставщика.</span><span class="sxs-lookup"><span data-stu-id="ddb91-123">Missing provider manifest: the provider returns `null` when attempting to retrieve the provider manifest.</span></span>|<span data-ttu-id="ddb91-124">ProviderIncompatibleException</span><span class="sxs-lookup"><span data-stu-id="ddb91-124">ProviderIncompatibleException</span></span>|  
|<span data-ttu-id="ddb91-125">Недопустимый манифест поставщика: поставщик возвращает недопустимый XML-код при попытке получить манифест поставщика.</span><span class="sxs-lookup"><span data-stu-id="ddb91-125">Invalid provider manifest: the provider returns invalid XML when attempting to retrieve the provider manifest.</span></span>|<span data-ttu-id="ddb91-126">ProviderIncompatibleException</span><span class="sxs-lookup"><span data-stu-id="ddb91-126">ProviderIncompatibleException</span></span>|  
  
## <a name="scenarios"></a><span data-ttu-id="ddb91-127">Сценарии</span><span class="sxs-lookup"><span data-stu-id="ddb91-127">Scenarios</span></span>  
 <span data-ttu-id="ddb91-128">Поставщик должен поддерживать следующие сценарии:</span><span class="sxs-lookup"><span data-stu-id="ddb91-128">A provider should support the following scenarios:</span></span>  
  
### <a name="writing-a-provider-with-symmetric-type-mapping"></a><span data-ttu-id="ddb91-129">Разработка поставщика с симметричным сопоставлением типов</span><span class="sxs-lookup"><span data-stu-id="ddb91-129">Writing a Provider with Symmetric Type Mapping</span></span>  
 <span data-ttu-id="ddb91-130">Можно написать поставщик для Entity Framework, где каждый тип хранилища сопоставляется с одним типом EDM, независимо от направления сопоставления.</span><span class="sxs-lookup"><span data-stu-id="ddb91-130">You can write a provider for the Entity Framework where each store type maps to a single EDM type, regardless of the mapping direction.</span></span> <span data-ttu-id="ddb91-131">Для типа поставщика, имеющего простое сопоставление с типом модели EDM, можно использовать симметричное решение, поскольку система типов проста или совпадает с системой типов модели EDM.</span><span class="sxs-lookup"><span data-stu-id="ddb91-131">For a provider type that has very simple mapping that corresponds with an EDM type, you can use a symmetric solution because the type system is simple or matches EDM types.</span></span>  
  
 <span data-ttu-id="ddb91-132">В случае простой структуры домена можно создать статический манифест поставщика в декларативном стиле.</span><span class="sxs-lookup"><span data-stu-id="ddb91-132">You can use the simplicity of their domain and produce a static declarative provider manifest.</span></span>  
  
 <span data-ttu-id="ddb91-133">Создайте XML-файл с двумя разделами.</span><span class="sxs-lookup"><span data-stu-id="ddb91-133">You write an XML file that has two sections:</span></span>  
  
- <span data-ttu-id="ddb91-134">Список типов поставщика в терминах эквивалентов EDM для типа или функции хранилища.</span><span class="sxs-lookup"><span data-stu-id="ddb91-134">A list of provider types expressed in terms of the "EDM counterpart" of a store type or function.</span></span> <span data-ttu-id="ddb91-135">Для типов хранилища имеются эквиваленты в модели EDM.</span><span class="sxs-lookup"><span data-stu-id="ddb91-135">Store types have counterpart EDM types.</span></span> <span data-ttu-id="ddb91-136">Для функций хранилища имеются соответствующие функции в модели EDM.</span><span class="sxs-lookup"><span data-stu-id="ddb91-136">Store functions have corresponding EDM functions.</span></span> <span data-ttu-id="ddb91-137">Например, тип varchar является типом SQL Server, а в модели EDM ему соответствует тип string.</span><span class="sxs-lookup"><span data-stu-id="ddb91-137">For example, varchar is a SQL Server type but the corresponding EDM type is string.</span></span>  
  
- <span data-ttu-id="ddb91-138">Список функций, поддерживаемых поставщиком, с указанием типов параметров и возвращаемых значений в терминах модели EDM.</span><span class="sxs-lookup"><span data-stu-id="ddb91-138">A list of functions supported by the provider where parameter and return types are expressed in EDM terms.</span></span>  
  
### <a name="writing-a-provider-with-asymmetric-type-mapping"></a><span data-ttu-id="ddb91-139">Разработка поставщика с асимметричным сопоставлением типов</span><span class="sxs-lookup"><span data-stu-id="ddb91-139">Writing a Provider with Asymmetric Type Mapping</span></span>  
 <span data-ttu-id="ddb91-140">При записи поставщика хранилища данных для Entity Framework сопоставление типов "модель EDM — поставщик" для некоторых типов может отличаться от сопоставления типов "поставщик-модель EDM".</span><span class="sxs-lookup"><span data-stu-id="ddb91-140">When writing a data store provider for the Entity Framework, the EDM-to-provider type mapping for some types may be different from provider-to-EDM type mapping.</span></span> <span data-ttu-id="ddb91-141">Например, непривязанный тип EDM PrimitiveTypeKind.String может сопоставляться с типом nvarchar(4000) в поставщике, а тип nvarchar(4000) сопоставляется с типом EDM PrimitiveTypeKind.String(MaxLength=4000).</span><span class="sxs-lookup"><span data-stu-id="ddb91-141">For instance, unbounded EDM PrimitiveTypeKind.String may map to nvarchar(4000) on the provider, while nvarchar(4000) maps to the EDM PrimitiveTypeKind.String(MaxLength=4000).</span></span>  
  
 <span data-ttu-id="ddb91-142">Создайте XML-файл с двумя разделами.</span><span class="sxs-lookup"><span data-stu-id="ddb91-142">You write an XML file that has two sections:</span></span>  
  
- <span data-ttu-id="ddb91-143">Список типов поставщика в терминах модели EDM и определение сопоставления в обоих направлениях: от модели EDM к поставщику и наоборот.</span><span class="sxs-lookup"><span data-stu-id="ddb91-143">A list of provider types expressed in EDM terms and define mapping for both direction: EDM-to-provider and provider-to-EDM.</span></span>  
  
- <span data-ttu-id="ddb91-144">Список функций, поддерживаемых поставщиком, с указанием типов параметров и возвращаемых значений в терминах модели EDM.</span><span class="sxs-lookup"><span data-stu-id="ddb91-144">A list of functions supported by the provider where parameter and return types are expressed in EDM terms.</span></span>  
  
## <a name="provider-manifest-discoverability"></a><span data-ttu-id="ddb91-145">Возможность обнаружения манифеста поставщика</span><span class="sxs-lookup"><span data-stu-id="ddb91-145">Provider Manifest Discoverability</span></span>  
 <span data-ttu-id="ddb91-146">Манифест неявно используется несколькими типами компонентов в службах сущностей (например, средствами и запросами), а также непосредственно используется в метаданных с помощью загрузчика метаданных хранилища.</span><span class="sxs-lookup"><span data-stu-id="ddb91-146">The manifest is used indirectly by several component types in Entity Services (for example Tools or Query) but more directly leveraged by metadata through the use of the data store metadata loader.</span></span>  
  
 <span data-ttu-id="ddb91-147">![dfb3d02b&#45;7a8c&#45;4d51&#45;ac5a&#45;a73d8aa145e6](./media/dfb3d02b-7a8c-4d51-ac5a-a73d8aa145e6.gif "dfb3d02b-7a8c-4d51-ac5a-a73d8aa145e6")</span><span class="sxs-lookup"><span data-stu-id="ddb91-147">![dfb3d02b&#45;7a8c&#45;4d51&#45;ac5a&#45;a73d8aa145e6](./media/dfb3d02b-7a8c-4d51-ac5a-a73d8aa145e6.gif "dfb3d02b-7a8c-4d51-ac5a-a73d8aa145e6")</span></span>  
  
 <span data-ttu-id="ddb91-148">При этом заданный поставщик может поддерживать различные хранилища или различные версии одного хранилища.</span><span class="sxs-lookup"><span data-stu-id="ddb91-148">However, a given provider may support different stores or different versions of the same store.</span></span> <span data-ttu-id="ddb91-149">Поэтому поставщик должен передавать различный манифест для каждого из поддерживаемых хранилищ данных.</span><span class="sxs-lookup"><span data-stu-id="ddb91-149">Therefore, a provider must report a different manifest for each supported data store.</span></span>  
  
### <a name="provider-manifest-token"></a><span data-ttu-id="ddb91-150">Маркер манифеста поставщика</span><span class="sxs-lookup"><span data-stu-id="ddb91-150">Provider Manifest Token</span></span>  
 <span data-ttu-id="ddb91-151">Если установлено соединение с хранилищем данных, поставщик может запросить сведения, чтобы вернуть правильный манифест.</span><span class="sxs-lookup"><span data-stu-id="ddb91-151">When a data store connection is opened, the provider can query for information to return the right manifest.</span></span> <span data-ttu-id="ddb91-152">Это может быть невозможно при автономном использовании, когда недоступны сведения о соединении или невозможно подключиться к хранилищу.</span><span class="sxs-lookup"><span data-stu-id="ddb91-152">This may not be possible in offline scenarios where connection information is not available or when it is not possible to connect to the store.</span></span> <span data-ttu-id="ddb91-153">Определите манифест с помощью атрибута `ProviderManifestToken` элемента `Schema` в SSDL-файле.</span><span class="sxs-lookup"><span data-stu-id="ddb91-153">Identify the manifest by using the `ProviderManifestToken` attribute of the `Schema` element in the .ssdl file.</span></span> <span data-ttu-id="ddb91-154">Формат этого атрибута не задан жестко. Поставщик выбирает минимально необходимые сведения для определения манифеста без соединения с хранилищем.</span><span class="sxs-lookup"><span data-stu-id="ddb91-154">There is no required format for this attribute; the provider chooses the minimum information needed to identify a manifest without opening a connection to the store.</span></span>  
  
 <span data-ttu-id="ddb91-155">Пример:</span><span class="sxs-lookup"><span data-stu-id="ddb91-155">For example:</span></span>  
  
```xml  
<Schema Namespace="Northwind" Provider="System.Data.SqlClient" ProviderManifestToken="2005" xmlns:edm="http://schemas.microsoft.com/ado/2006/04/edm/ssdl" xmlns="http://schemas.microsoft.com/ado/2006/04/edm/ssdl">  
```  
  
## <a name="provider-manifest-programming-model"></a><span data-ttu-id="ddb91-156">Модель программирования манифеста поставщика</span><span class="sxs-lookup"><span data-stu-id="ddb91-156">Provider Manifest Programming Model</span></span>  
 <span data-ttu-id="ddb91-157">Поставщики являются производными от класса <xref:System.Data.Common.DbXmlEnabledProviderManifest> и поэтому могут указывать манифесты декларативно.</span><span class="sxs-lookup"><span data-stu-id="ddb91-157">Providers derive from <xref:System.Data.Common.DbXmlEnabledProviderManifest>, which allows them to specify their manifests declaratively.</span></span> <span data-ttu-id="ddb91-158">На следующем рисунке показана иерархия классов поставщика.</span><span class="sxs-lookup"><span data-stu-id="ddb91-158">The following illustration shows the class hierarchy of a provider:</span></span>  
  
 <span data-ttu-id="ddb91-159">![None](./media/d541eba3-2ee6-4cd1-88f5-89d0b2582a6c.gif "d541eba3-2ee6-4cd1-88f5-89d0b2582a6c")</span><span class="sxs-lookup"><span data-stu-id="ddb91-159">![None](./media/d541eba3-2ee6-4cd1-88f5-89d0b2582a6c.gif "d541eba3-2ee6-4cd1-88f5-89d0b2582a6c")</span></span>  
  
### <a name="discoverability-api"></a><span data-ttu-id="ddb91-160">API обнаружения</span><span class="sxs-lookup"><span data-stu-id="ddb91-160">Discoverability API</span></span>  
 <span data-ttu-id="ddb91-161">Манифест поставщика загружается загрузчиком метаданных хранилища (StoreItemCollection) с помощью соединения с хранилищем данных или маркера манифеста поставщика.</span><span class="sxs-lookup"><span data-stu-id="ddb91-161">The provider manifest is loaded by the Store Metadata loader (StoreItemCollection), either by using a data store connection or a provider manifest token.</span></span>  
  
#### <a name="using-a-data-store-connection"></a><span data-ttu-id="ddb91-162">Использование соединения с хранилищем данных</span><span class="sxs-lookup"><span data-stu-id="ddb91-162">Using a Data Store Connection</span></span>  
 <span data-ttu-id="ddb91-163">Если подключение к хранилищу данных доступно, вызовите <xref:System.Data.Common.DbProviderServices.GetProviderManifestToken%2A?displayProperty=nameWithType>, чтобы вернуть маркер, который передается методу <xref:System.Data.Common.DbProviderServices.GetProviderManifest%2A>, который возвращает <xref:System.Data.Common.DbProviderManifest>.</span><span class="sxs-lookup"><span data-stu-id="ddb91-163">When the data store connection is available, call <xref:System.Data.Common.DbProviderServices.GetProviderManifestToken%2A?displayProperty=nameWithType> to return the token that is passed to the <xref:System.Data.Common.DbProviderServices.GetProviderManifest%2A> method, which returns <xref:System.Data.Common.DbProviderManifest>.</span></span> <span data-ttu-id="ddb91-164">Этот метод делегирует реализацию `GetDbProviderManifestToken`поставщика.</span><span class="sxs-lookup"><span data-stu-id="ddb91-164">This method delegates to the provider's implementation of `GetDbProviderManifestToken`.</span></span>  
  
```csharp
public string GetProviderManifestToken(DbConnection connection);  
public DbProviderManifest GetProviderManifest(string manifestToken);  
```  
  
#### <a name="using-a-provider-manifest-token"></a><span data-ttu-id="ddb91-165">Использование маркера манифеста поставщика</span><span class="sxs-lookup"><span data-stu-id="ddb91-165">Using a Provider Manifest Token</span></span>  
 <span data-ttu-id="ddb91-166">В случае автономной работы маркер берется из представления SSDL.</span><span class="sxs-lookup"><span data-stu-id="ddb91-166">For the offline scenario, the token is picked from SSDL representation.</span></span> <span data-ttu-id="ddb91-167">Язык SSDL позволяет указать ProviderManifestToken (Дополнительные сведения см. в разделе [Schema Element (SSDL)](/ef/ef6/modeling/designer/advanced/edmx/ssdl-spec#schema-element-ssdl) ).</span><span class="sxs-lookup"><span data-stu-id="ddb91-167">The SSDL allows you to specify a ProviderManifestToken (see [Schema Element (SSDL)](/ef/ef6/modeling/designer/advanced/edmx/ssdl-spec#schema-element-ssdl) for more information).</span></span> <span data-ttu-id="ddb91-168">Например, если не удается открыть соединение, то в SSDL используется маркер манифеста поставщика, в котором указываются сведения о манифесте.</span><span class="sxs-lookup"><span data-stu-id="ddb91-168">For example, if a connection cannot be opened, the SSDL has a provider manifest token that specifies information about the manifest.</span></span>  
  
```csharp  
public DbProviderManifest GetProviderManifest(string manifestToken);  
```  
  
### <a name="provider-manifest-schema"></a><span data-ttu-id="ddb91-169">Схема манифеста поставщика</span><span class="sxs-lookup"><span data-stu-id="ddb91-169">Provider Manifest Schema</span></span>  
 <span data-ttu-id="ddb91-170">Схема данных, определенных для каждого поставщика, содержит статические данные для обработки в метаданных.</span><span class="sxs-lookup"><span data-stu-id="ddb91-170">The schema of information defined for each provider contains the static information to be consumed by metadata:</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<xs:schema elementFormDefault="qualified"  
   xmlns:xs="http://www.w3.org/2001/XMLSchema"  
   targetNamespace="http://schemas.microsoft.com/ado/2006/04/edm/providermanifest"  
   xmlns:pm="http://schemas.microsoft.com/ado/2006/04/edm/providermanifest">  
  
  <xs:element name="ProviderManifest">  
    <xs:complexType>  
      <xs:sequence>  
        <xs:element name="Types" type="pm:TTypes" minOccurs="1" maxOccurs="1" />  
        <xs:element name="Functions" type="pm:TFunctions" minOccurs="0" maxOccurs="1"/>  
      </xs:sequence>  
      <xs:attribute name="Namespace" type="xs:string" use="required"/>  
    </xs:complexType>  
  </xs:element>  
  <xs:complexType name="TVersion">  
    <xs:attribute name="Major" type="xs:int" use="required" />  
    <xs:attribute name="Minor" type="xs:int" use="required" />  
    <xs:attribute name="Build" type="xs:int" use="required" />  
    <xs:attribute name="Revision" type="xs:int" use="required" />  
  </xs:complexType>  
  
  <xs:complexType name="TIntegerFacetDescription">  
    <xs:attribute name="Minimum" type="xs:int" use="optional" />  
    <xs:attribute name="Maximum" type="xs:int" use="optional" />  
    <xs:attribute name="DefaultValue" type="xs:int" use="optional" />  
    <xs:attribute name="Constant" type="xs:boolean" default="false" />  
  </xs:complexType>  
  
  <xs:complexType name="TBooleanFacetDescription">  
    <xs:attribute name="DefaultValue" type="xs:boolean" use="optional" />  
    <xs:attribute name="Constant" type="xs:boolean" default="true" />  
  </xs:complexType>  
  
  <xs:complexType name="TDateTimeFacetDescription">  
    <xs:attribute name="Constant" type="xs:boolean" default="false" />  
  </xs:complexType>  
  
  <xs:complexType name="TFacetDescriptions">  
    <xs:choice maxOccurs="unbounded">  
      <xs:element name="Precision" minOccurs="0" maxOccurs="1" type="pm:TIntegerFacetDescription"/>  
      <xs:element name="Scale" minOccurs="0" maxOccurs="1" type="pm:TIntegerFacetDescription"/>  
      <xs:element name="MaxLength" minOccurs="0" maxOccurs="1" type="pm:TIntegerFacetDescription"/>  
      <xs:element name="Unicode" minOccurs="0" maxOccurs="1" type="pm:TBooleanFacetDescription"/>  
      <xs:element name="FixedLength" minOccurs="0" maxOccurs="1" type="pm:TBooleanFacetDescription"/>  
    </xs:choice>  
  </xs:complexType>  
  
  <xs:complexType name="TType">  
    <xs:sequence>  
      <xs:element name="FacetDescriptions" type="pm:TFacetDescriptions" minOccurs="0" maxOccurs="1"/>  
    </xs:sequence>  
    <xs:attribute name="Name" type="xs:string" use="required"/>  
    <xs:attribute name="PrimitiveTypeKind" type="pm:TPrimitiveTypeKind" use="required" />  
  </xs:complexType>  
  
  <xs:complexType name="TTypes">  
    <xs:sequence>  
      <xs:element name="Type" type="pm:TType" minOccurs="0" maxOccurs="unbounded"/>  
    </xs:sequence>  
  </xs:complexType>  
  
  <xs:attributeGroup name="TFacetAttribute">  
    <xs:attribute name="Precision" type="xs:int" use="optional"/>  
    <xs:attribute name="Scale" type="xs:int" use="optional"/>  
    <xs:attribute name="MaxLength" type="xs:int" use="optional"/>  
    <xs:attribute name="Unicode" type="xs:boolean" use="optional"/>  
    <xs:attribute name="FixedLength" type="xs:boolean" use="optional"/>  
  </xs:attributeGroup>  
  
  <xs:complexType name="TFunctionParameter">  
    <xs:attribute name="Name" type="xs:string" use="required" />  
    <xs:attribute name="Type" type="xs:string" use="required" />  
    <xs:attributeGroup ref="pm:TFacetAttribute" />  
    <xs:attribute name="Mode" type="pm:TParameterDirection" use="required" />  
  </xs:complexType>  
  
  <xs:complexType name="TReturnType">  
    <xs:attribute name="Type" type="xs:string" use="required" />  
    <xs:attributeGroup ref="pm:TFacetAttribute" />  
  </xs:complexType>  
  
  <xs:complexType name="TFunction">  
    <xs:choice minOccurs="0" maxOccurs ="unbounded">  
      <xs:element name ="ReturnType" type="pm:TReturnType" minOccurs="0" maxOccurs="1" />  
      <xs:element name="Parameter" type="pm:TFunctionParameter" minOccurs="0" maxOccurs="unbounded"/>  
    </xs:choice>  
    <xs:attribute name="Name" type="xs:string" use="required" />  
    <xs:attribute name="Aggregate" type="xs:boolean" use="optional" />  
    <xs:attribute name="BuiltIn" type="xs:boolean" use="optional" />  
    <xs:attribute name="StoreFunctionName" type="xs:string" use="optional" />  
    <xs:attribute name="NiladicFunction" type="xs:boolean" use="optional" />  
    <xs:attribute name="ParameterTypeSemantics" type="pm:TParameterTypeSemantics" use="optional" default="AllowImplicitConversion" />  
  </xs:complexType>  
  
  <xs:complexType name="TFunctions">  
    <xs:sequence>  
      <xs:element name="Function" type="pm:TFunction" minOccurs="0" maxOccurs="unbounded"/>  
    </xs:sequence>  
  </xs:complexType>  
  
  <xs:simpleType name="TPrimitiveTypeKind">  
    <xs:restriction base="xs:string">  
      <xs:enumeration value="Binary"/>  
      <xs:enumeration value="Boolean"/>  
      <xs:enumeration value="Byte"/>  
      <xs:enumeration value="Decimal"/>  
      <xs:enumeration value="DateTime"/>  
      <xs:enumeration value="Time"/>  
      <xs:enumeration value="DateTimeOffset"/>          
      <xs:enumeration value="Double"/>  
      <xs:enumeration value="Guid"/>  
      <xs:enumeration value="Single"/>  
      <xs:enumeration value="SByte"/>  
      <xs:enumeration value="Int16"/>  
      <xs:enumeration value="Int32"/>  
      <xs:enumeration value="Int64"/>  
      <xs:enumeration value="String"/>  
    </xs:restriction>  
  </xs:simpleType>  
  
  <xs:simpleType name="TParameterDirection">  
    <xs:restriction base="xs:string">  
      <xs:enumeration value="In"/>  
      <xs:enumeration value="Out"/>  
      <xs:enumeration value="InOut"/>  
    </xs:restriction>  
  </xs:simpleType>  
  
  <xs:simpleType name="TParameterTypeSemantics">  
    <xs:restriction base="xs:string">  
      <xs:enumeration value="ExactMatchOnly" />  
      <xs:enumeration value="AllowImplicitPromotion" />  
      <xs:enumeration value="AllowImplicitConversion" />  
    </xs:restriction>  
  </xs:simpleType>  
</xs:schema>  
```  
  
#### <a name="types-node"></a><span data-ttu-id="ddb91-171">Узел типов</span><span class="sxs-lookup"><span data-stu-id="ddb91-171">Types Node</span></span>  
 <span data-ttu-id="ddb91-172">Узел типов в манифесте поставщика содержит сведения о типах, которые поддерживаются хранилищем данных непосредственно или с помощью поставщика.</span><span class="sxs-lookup"><span data-stu-id="ddb91-172">The Types node in the provider manifest contains information about the Types that are supported natively by the data store or through the provider.</span></span>  
  
##### <a name="type-node"></a><span data-ttu-id="ddb91-173">Узел типа</span><span class="sxs-lookup"><span data-stu-id="ddb91-173">Type Node</span></span>  
 <span data-ttu-id="ddb91-174">В каждом узле типа определяется тип поставщика в терминах модели EDM.</span><span class="sxs-lookup"><span data-stu-id="ddb91-174">Each Type node defines a provider type in terms of EDM.</span></span> <span data-ttu-id="ddb91-175">В узле типа описывается имя типа поставщика и сведения, связанные с типом модели, который сопоставляется с типом поставщика, и с аспектами, описывающими это сопоставление.</span><span class="sxs-lookup"><span data-stu-id="ddb91-175">The Type node describes the name of the provider type, and information related to the model type it maps to and facets to describe that type mapping.</span></span>  
  
 <span data-ttu-id="ddb91-176">Для выражения этих сведений о типе в манифесте поставщика каждое определение TypeInformation должно определять несколько аспектов для каждого типа.</span><span class="sxs-lookup"><span data-stu-id="ddb91-176">In order to express this type information in the provider manifest, each TypeInformation declaration must define several facet descriptions for each Type:</span></span>  
  
|<span data-ttu-id="ddb91-177">Имя атрибута</span><span class="sxs-lookup"><span data-stu-id="ddb91-177">Attribute Name</span></span>|<span data-ttu-id="ddb91-178">Тип данных</span><span class="sxs-lookup"><span data-stu-id="ddb91-178">Data Type</span></span>|<span data-ttu-id="ddb91-179">Обязательное значение</span><span class="sxs-lookup"><span data-stu-id="ddb91-179">Required</span></span>|<span data-ttu-id="ddb91-180">Значение по умолчанию</span><span class="sxs-lookup"><span data-stu-id="ddb91-180">Default Value</span></span>|<span data-ttu-id="ddb91-181">Описание</span><span class="sxs-lookup"><span data-stu-id="ddb91-181">Description</span></span>|  
|--------------------|---------------|--------------|-------------------|-----------------|  
|<span data-ttu-id="ddb91-182">Название</span><span class="sxs-lookup"><span data-stu-id="ddb91-182">Name</span></span>|<span data-ttu-id="ddb91-183">Строковое</span><span class="sxs-lookup"><span data-stu-id="ddb91-183">String</span></span>|<span data-ttu-id="ddb91-184">Да</span><span class="sxs-lookup"><span data-stu-id="ddb91-184">Yes</span></span>|<span data-ttu-id="ddb91-185">Н/Д</span><span class="sxs-lookup"><span data-stu-id="ddb91-185">n/a</span></span>|<span data-ttu-id="ddb91-186">Имя типа данных, зависящего от поставщика</span><span class="sxs-lookup"><span data-stu-id="ddb91-186">Provider-specific data type name</span></span>|  
|<span data-ttu-id="ddb91-187">PrimitiveTypeKind</span><span class="sxs-lookup"><span data-stu-id="ddb91-187">PrimitiveTypeKind</span></span>|<span data-ttu-id="ddb91-188">PrimitiveTypeKind</span><span class="sxs-lookup"><span data-stu-id="ddb91-188">PrimitiveTypeKind</span></span>|<span data-ttu-id="ddb91-189">Да</span><span class="sxs-lookup"><span data-stu-id="ddb91-189">Yes</span></span>|<span data-ttu-id="ddb91-190">Н/Д</span><span class="sxs-lookup"><span data-stu-id="ddb91-190">n/a</span></span>|<span data-ttu-id="ddb91-191">Имя типа в модели EDM</span><span class="sxs-lookup"><span data-stu-id="ddb91-191">EDM type name</span></span>|  
  
###### <a name="function-node"></a><span data-ttu-id="ddb91-192">Узел функции</span><span class="sxs-lookup"><span data-stu-id="ddb91-192">Function Node</span></span>  
 <span data-ttu-id="ddb91-193">В каждом узле функции определяется функция, доступная посредством поставщика.</span><span class="sxs-lookup"><span data-stu-id="ddb91-193">Each Function defines a single function available through the provider.</span></span>  
  
|<span data-ttu-id="ddb91-194">Имя атрибута</span><span class="sxs-lookup"><span data-stu-id="ddb91-194">Attribute Name</span></span>|<span data-ttu-id="ddb91-195">Тип данных</span><span class="sxs-lookup"><span data-stu-id="ddb91-195">Data Type</span></span>|<span data-ttu-id="ddb91-196">Обязательное значение</span><span class="sxs-lookup"><span data-stu-id="ddb91-196">Required</span></span>|<span data-ttu-id="ddb91-197">Значение по умолчанию</span><span class="sxs-lookup"><span data-stu-id="ddb91-197">Default Value</span></span>|<span data-ttu-id="ddb91-198">Описание</span><span class="sxs-lookup"><span data-stu-id="ddb91-198">Description</span></span>|  
|--------------------|---------------|--------------|-------------------|-----------------|  
|<span data-ttu-id="ddb91-199">Название</span><span class="sxs-lookup"><span data-stu-id="ddb91-199">Name</span></span>|<span data-ttu-id="ddb91-200">Строковое</span><span class="sxs-lookup"><span data-stu-id="ddb91-200">String</span></span>|<span data-ttu-id="ddb91-201">Да</span><span class="sxs-lookup"><span data-stu-id="ddb91-201">Yes</span></span>|<span data-ttu-id="ddb91-202">Н/Д</span><span class="sxs-lookup"><span data-stu-id="ddb91-202">n/a</span></span>|<span data-ttu-id="ddb91-203">Идентификатор или имя функции</span><span class="sxs-lookup"><span data-stu-id="ddb91-203">Identifier/name of the function</span></span>|  
|<span data-ttu-id="ddb91-204">ReturnType</span><span class="sxs-lookup"><span data-stu-id="ddb91-204">ReturnType</span></span>|<span data-ttu-id="ddb91-205">Строковое</span><span class="sxs-lookup"><span data-stu-id="ddb91-205">String</span></span>|<span data-ttu-id="ddb91-206">Нет</span><span class="sxs-lookup"><span data-stu-id="ddb91-206">No</span></span>|<span data-ttu-id="ddb91-207">Void</span><span class="sxs-lookup"><span data-stu-id="ddb91-207">Void</span></span>|<span data-ttu-id="ddb91-208">Тип возвращаемого значения функции в модели EDM</span><span class="sxs-lookup"><span data-stu-id="ddb91-208">The EDM return type of the function</span></span>|  
|<span data-ttu-id="ddb91-209">Aggregate</span><span class="sxs-lookup"><span data-stu-id="ddb91-209">Aggregate</span></span>|<span data-ttu-id="ddb91-210">логический</span><span class="sxs-lookup"><span data-stu-id="ddb91-210">Boolean</span></span>|<span data-ttu-id="ddb91-211">Нет</span><span class="sxs-lookup"><span data-stu-id="ddb91-211">No</span></span>|<span data-ttu-id="ddb91-212">False</span><span class="sxs-lookup"><span data-stu-id="ddb91-212">False</span></span>|<span data-ttu-id="ddb91-213">Значение True, если функция является агрегатной</span><span class="sxs-lookup"><span data-stu-id="ddb91-213">True if the function is an aggregate function</span></span>|  
|<span data-ttu-id="ddb91-214">BuiltIn</span><span class="sxs-lookup"><span data-stu-id="ddb91-214">BuiltIn</span></span>|<span data-ttu-id="ddb91-215">логический</span><span class="sxs-lookup"><span data-stu-id="ddb91-215">Boolean</span></span>|<span data-ttu-id="ddb91-216">Нет</span><span class="sxs-lookup"><span data-stu-id="ddb91-216">No</span></span>|<span data-ttu-id="ddb91-217">True</span><span class="sxs-lookup"><span data-stu-id="ddb91-217">True</span></span>|<span data-ttu-id="ddb91-218">Значение True, если функция встроена в хранилище данных</span><span class="sxs-lookup"><span data-stu-id="ddb91-218">True if the function is built into the data store</span></span>|  
|<span data-ttu-id="ddb91-219">StoreFunctionName</span><span class="sxs-lookup"><span data-stu-id="ddb91-219">StoreFunctionName</span></span>|<span data-ttu-id="ddb91-220">Строковое</span><span class="sxs-lookup"><span data-stu-id="ddb91-220">String</span></span>|<span data-ttu-id="ddb91-221">Нет</span><span class="sxs-lookup"><span data-stu-id="ddb91-221">No</span></span>|<span data-ttu-id="ddb91-222">Имя \<</span><span class="sxs-lookup"><span data-stu-id="ddb91-222">\<Name></span></span>|<span data-ttu-id="ddb91-223">Имя функции в хранилище данных.</span><span class="sxs-lookup"><span data-stu-id="ddb91-223">Function Name in the data store.</span></span>  <span data-ttu-id="ddb91-224">Реализует уровень перенаправления для имен функций.</span><span class="sxs-lookup"><span data-stu-id="ddb91-224">Allows for a level of redirection of function names.</span></span>|  
|<span data-ttu-id="ddb91-225">NiladicFunction</span><span class="sxs-lookup"><span data-stu-id="ddb91-225">NiladicFunction</span></span>|<span data-ttu-id="ddb91-226">логический</span><span class="sxs-lookup"><span data-stu-id="ddb91-226">Boolean</span></span>|<span data-ttu-id="ddb91-227">Нет</span><span class="sxs-lookup"><span data-stu-id="ddb91-227">No</span></span>|<span data-ttu-id="ddb91-228">False</span><span class="sxs-lookup"><span data-stu-id="ddb91-228">False</span></span>|<span data-ttu-id="ddb91-229">Значение True, если функция не требует параметров и вызывается без параметров</span><span class="sxs-lookup"><span data-stu-id="ddb91-229">True if the function does not require parameters and is called without any parameters</span></span>|  
|<span data-ttu-id="ddb91-230">ParameterType</span><span class="sxs-lookup"><span data-stu-id="ddb91-230">ParameterType</span></span><br /><br /> <span data-ttu-id="ddb91-231">Семантика</span><span class="sxs-lookup"><span data-stu-id="ddb91-231">Semantics</span></span>|<span data-ttu-id="ddb91-232">ParameterSemantics</span><span class="sxs-lookup"><span data-stu-id="ddb91-232">ParameterSemantics</span></span>|<span data-ttu-id="ddb91-233">Нет</span><span class="sxs-lookup"><span data-stu-id="ddb91-233">No</span></span>|<span data-ttu-id="ddb91-234">AllowImplicit</span><span class="sxs-lookup"><span data-stu-id="ddb91-234">AllowImplicit</span></span><br /><br /> <span data-ttu-id="ddb91-235">Преобразование</span><span class="sxs-lookup"><span data-stu-id="ddb91-235">Conversion</span></span>|<span data-ttu-id="ddb91-236">Выберите, как конвейер запросов должен обрабатывать замену типов параметров:</span><span class="sxs-lookup"><span data-stu-id="ddb91-236">Choice of how the query pipeline should deal with parameter type substitution:</span></span><br /><br /> <span data-ttu-id="ddb91-237">-Ексактматчонли</span><span class="sxs-lookup"><span data-stu-id="ddb91-237">-   ExactMatchOnly</span></span><br /><span data-ttu-id="ddb91-238">-АлловимплиЦитпромотион</span><span class="sxs-lookup"><span data-stu-id="ddb91-238">-   AllowImplicitPromotion</span></span><br /><span data-ttu-id="ddb91-239">-АлловимплиЦитконверсион</span><span class="sxs-lookup"><span data-stu-id="ddb91-239">-   AllowImplicitConversion</span></span>|  
  
 <span data-ttu-id="ddb91-240">**Узел параметров**</span><span class="sxs-lookup"><span data-stu-id="ddb91-240">**Parameters Node**</span></span>  
  
 <span data-ttu-id="ddb91-241">Каждая функция имеет коллекцию из одного или нескольких узлов параметров.</span><span class="sxs-lookup"><span data-stu-id="ddb91-241">Each function has a collection of one or more Parameter nodes.</span></span>  
  
|<span data-ttu-id="ddb91-242">Имя атрибута</span><span class="sxs-lookup"><span data-stu-id="ddb91-242">Attribute Name</span></span>|<span data-ttu-id="ddb91-243">Тип данных</span><span class="sxs-lookup"><span data-stu-id="ddb91-243">Data Type</span></span>|<span data-ttu-id="ddb91-244">Обязательное значение</span><span class="sxs-lookup"><span data-stu-id="ddb91-244">Required</span></span>|<span data-ttu-id="ddb91-245">Значение по умолчанию</span><span class="sxs-lookup"><span data-stu-id="ddb91-245">Default Value</span></span>|<span data-ttu-id="ddb91-246">Описание</span><span class="sxs-lookup"><span data-stu-id="ddb91-246">Description</span></span>|  
|--------------------|---------------|--------------|-------------------|-----------------|  
|<span data-ttu-id="ddb91-247">Название</span><span class="sxs-lookup"><span data-stu-id="ddb91-247">Name</span></span>|<span data-ttu-id="ddb91-248">Строковое</span><span class="sxs-lookup"><span data-stu-id="ddb91-248">String</span></span>|<span data-ttu-id="ddb91-249">Да</span><span class="sxs-lookup"><span data-stu-id="ddb91-249">Yes</span></span>|<span data-ttu-id="ddb91-250">Н/Д</span><span class="sxs-lookup"><span data-stu-id="ddb91-250">n/a</span></span>|<span data-ttu-id="ddb91-251">Идентификатор или имя параметра.</span><span class="sxs-lookup"><span data-stu-id="ddb91-251">Identifier/name of the parameter.</span></span>|  
|<span data-ttu-id="ddb91-252">Type</span><span class="sxs-lookup"><span data-stu-id="ddb91-252">Type</span></span>|<span data-ttu-id="ddb91-253">Строковое</span><span class="sxs-lookup"><span data-stu-id="ddb91-253">String</span></span>|<span data-ttu-id="ddb91-254">Да</span><span class="sxs-lookup"><span data-stu-id="ddb91-254">Yes</span></span>|<span data-ttu-id="ddb91-255">Н/Д</span><span class="sxs-lookup"><span data-stu-id="ddb91-255">n/a</span></span>|<span data-ttu-id="ddb91-256">Тип параметра в модели EDM.</span><span class="sxs-lookup"><span data-stu-id="ddb91-256">The EDM type of the parameter.</span></span>|  
|<span data-ttu-id="ddb91-257">Режим</span><span class="sxs-lookup"><span data-stu-id="ddb91-257">Mode</span></span>|<span data-ttu-id="ddb91-258">Параметр</span><span class="sxs-lookup"><span data-stu-id="ddb91-258">Parameter</span></span><br /><br /> <span data-ttu-id="ddb91-259">Направление</span><span class="sxs-lookup"><span data-stu-id="ddb91-259">Direction</span></span>|<span data-ttu-id="ddb91-260">Да</span><span class="sxs-lookup"><span data-stu-id="ddb91-260">Yes</span></span>|<span data-ttu-id="ddb91-261">Н/Д</span><span class="sxs-lookup"><span data-stu-id="ddb91-261">n/a</span></span>|<span data-ttu-id="ddb91-262">Направление параметра:</span><span class="sxs-lookup"><span data-stu-id="ddb91-262">Direction of parameter:</span></span><br /><br /> <span data-ttu-id="ddb91-263">— в</span><span class="sxs-lookup"><span data-stu-id="ddb91-263">-   in</span></span><br /><span data-ttu-id="ddb91-264">-out</span><span class="sxs-lookup"><span data-stu-id="ddb91-264">-   out</span></span><br /><span data-ttu-id="ddb91-265">-Inout</span><span class="sxs-lookup"><span data-stu-id="ddb91-265">-   inout</span></span>|  
  
##### <a name="namespace-attribute"></a><span data-ttu-id="ddb91-266">Атрибут Namespace</span><span class="sxs-lookup"><span data-stu-id="ddb91-266">Namespace Attribute</span></span>  
 <span data-ttu-id="ddb91-267">В каждом поставщике хранилища данных должно определяться пространство имен или группа пространств имен для сведений, определяемых в манифесте.</span><span class="sxs-lookup"><span data-stu-id="ddb91-267">Each data store provider must define a namespace or group of namespaces for information defined in the manifest.</span></span> <span data-ttu-id="ddb91-268">Это пространство имен можно использовать в запросах Entity SQL для разрешения имен функций и типов.</span><span class="sxs-lookup"><span data-stu-id="ddb91-268">This namespace can be used in Entity SQL queries to resolve names of functions and types.</span></span> <span data-ttu-id="ddb91-269">Пример: SqlServer.</span><span class="sxs-lookup"><span data-stu-id="ddb91-269">For instance: SqlServer.</span></span> <span data-ttu-id="ddb91-270">Это пространство имен должно отличаться от канонического пространства имен EDM, определенного в службах сущностей для стандартных функций, поддерживаемых запросами Entity SQL.</span><span class="sxs-lookup"><span data-stu-id="ddb91-270">That namespace must be different from the canonical namespace, EDM, defined by Entity Services for standard functions to be supported by Entity SQL queries.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ddb91-271">См. также</span><span class="sxs-lookup"><span data-stu-id="ddb91-271">See also</span></span>

- [<span data-ttu-id="ddb91-272">Создание поставщика данных Entity Framework</span><span class="sxs-lookup"><span data-stu-id="ddb91-272">Writing an Entity Framework Data Provider</span></span>](writing-an-ef-data-provider.md)
