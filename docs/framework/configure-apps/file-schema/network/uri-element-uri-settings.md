---
title: Элемент <Uri> (параметры URI)
ms.date: 03/30/2017
ms.assetid: c22bab8b-477c-4ae4-8498-65ad409e0847
ms.openlocfilehash: 80d71da5ca680872e4948fa8ff135fbbdf08cffe
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/21/2019
ms.locfileid: "69663962"
---
# <a name="uri-element-uri-settings"></a><span data-ttu-id="56a25-102">\<Элемент > URI (Параметры URI)</span><span class="sxs-lookup"><span data-stu-id="56a25-102">\<Uri> Element (Uri Settings)</span></span>
<span data-ttu-id="56a25-103">Содержит параметры, определяющие, как .NET Framework обрабатывает веб-адреса, выраженные с помощью универсальных идентификаторов ресурсов (URI).</span><span class="sxs-lookup"><span data-stu-id="56a25-103">Contains settings that specify how the .NET Framework handles web addresses expressed using uniform resource identifiers (URIs).</span></span>  
  
## <a name="schema-hierarchy"></a><span data-ttu-id="56a25-104">Схема иерархии</span><span class="sxs-lookup"><span data-stu-id="56a25-104">Schema Hierarchy</span></span>  
 [<span data-ttu-id="56a25-105">Элемент \<configuration></span><span class="sxs-lookup"><span data-stu-id="56a25-105">\<configuration> Element</span></span>](../configuration-element.md)  
  
 [<span data-ttu-id="56a25-106">\<> URI</span><span class="sxs-lookup"><span data-stu-id="56a25-106">\<uri></span></span>](uri-element-uri-settings.md)  
  
## <a name="syntax"></a><span data-ttu-id="56a25-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="56a25-107">Syntax</span></span>  
  
```xml  
<uri>  
</uri>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="56a25-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="56a25-108">Attributes and Elements</span></span>  
 <span data-ttu-id="56a25-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="56a25-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="56a25-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="56a25-110">Attributes</span></span>  
 <span data-ttu-id="56a25-111">Нет.</span><span class="sxs-lookup"><span data-stu-id="56a25-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="56a25-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="56a25-112">Child Elements</span></span>  
  
|<span data-ttu-id="56a25-113">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="56a25-113">**Element**</span></span>|<span data-ttu-id="56a25-114">**Описание**</span><span class="sxs-lookup"><span data-stu-id="56a25-114">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="56a25-115">IDN</span><span class="sxs-lookup"><span data-stu-id="56a25-115">idn</span></span>](idn-element-uri-settings.md)|<span data-ttu-id="56a25-116">Определяет, применяется ли к доменным именам анализ международных доменных имен (IDN).</span><span class="sxs-lookup"><span data-stu-id="56a25-116">Specifies if Internationalized Domain Name (IDN) parsing is applied to domain names.</span></span>|  
|[<span data-ttu-id="56a25-117">Элемент iriParsing</span><span class="sxs-lookup"><span data-stu-id="56a25-117">iriParsing</span></span>](iriparsing-element-uri-settings.md)|<span data-ttu-id="56a25-118">Указывает, применяется <xref:System.Uri> ли синтаксический анализ международного идентификатора ресурса (IRI), и должны применяться правила синтаксического анализа IRI.</span><span class="sxs-lookup"><span data-stu-id="56a25-118">Specifies if International Resource Identifier (IRI) parsing is applied to <xref:System.Uri> and whether IRI parsing rules should be applied.</span></span>|  
|[<span data-ttu-id="56a25-119">schemeSettings</span><span class="sxs-lookup"><span data-stu-id="56a25-119">schemeSettings</span></span>](schemesettings-element-uri-settings.md)|<span data-ttu-id="56a25-120">Определяет, как <xref:System.Uri> анализируется для определенных схем.</span><span class="sxs-lookup"><span data-stu-id="56a25-120">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="56a25-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="56a25-121">Parent Elements</span></span>  
  
|<span data-ttu-id="56a25-122">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="56a25-122">**Element**</span></span>|<span data-ttu-id="56a25-123">**Описание**</span><span class="sxs-lookup"><span data-stu-id="56a25-123">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="56a25-124">Настройка</span><span class="sxs-lookup"><span data-stu-id="56a25-124">configuration</span></span>](../configuration-element.md)|<span data-ttu-id="56a25-125">Содержит параметры для всех пространств имен.</span><span class="sxs-lookup"><span data-stu-id="56a25-125">Contains settings for all namespaces.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="56a25-126">Примечания</span><span class="sxs-lookup"><span data-stu-id="56a25-126">Remarks</span></span>  
 <span data-ttu-id="56a25-127">Элемент содержит параметры для элементов <xref:System.Uri> класса, <xref:System.Net> используемых классами в пространстве имен. `uri`</span><span class="sxs-lookup"><span data-stu-id="56a25-127">The `uri` element contains settings for members of the <xref:System.Uri> class used by classes in the <xref:System.Net> namespace.</span></span> <span data-ttu-id="56a25-128">Параметры настраивают поддержку для IRI и IDN.</span><span class="sxs-lookup"><span data-stu-id="56a25-128">The settings configure support for IRI and IDN.</span></span>  
  
## <a name="example"></a><span data-ttu-id="56a25-129">Пример</span><span class="sxs-lookup"><span data-stu-id="56a25-129">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="56a25-130">Описание</span><span class="sxs-lookup"><span data-stu-id="56a25-130">Description</span></span>  
 <span data-ttu-id="56a25-131">В следующем примере показана конфигурация, используемая <xref:System.Uri> классом для поддержки синтаксического анализа IRI и имен IDN.</span><span class="sxs-lookup"><span data-stu-id="56a25-131">The following example shows a configuration used by the <xref:System.Uri> class to support IRI parsing and IDN names.</span></span> <span data-ttu-id="56a25-132">В этом примере также очищаются все параметры схемы, а затем добавляется поддержка не экранирования процентов для пути, закодированного для схемы HTTP.</span><span class="sxs-lookup"><span data-stu-id="56a25-132">The example also clears all scheme settings and then adds support for not escaping percent-encoded path delimiters for the http scheme.</span></span>  
  
### <a name="code"></a><span data-ttu-id="56a25-133">Код</span><span class="sxs-lookup"><span data-stu-id="56a25-133">Code</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <idn enabled="All" />  
    <iriParsing enabled="true" />  
    <schemeSettings>  
      <clear/>  
      <add name="http" genericUriParserOptions="DontUnescapePathDotsAndSlashes"/>  
    </schemeSettings>  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="56a25-134">См. также</span><span class="sxs-lookup"><span data-stu-id="56a25-134">See also</span></span>

- [<span data-ttu-id="56a25-135">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="56a25-135">Network Settings Schema</span></span>](index.md)
