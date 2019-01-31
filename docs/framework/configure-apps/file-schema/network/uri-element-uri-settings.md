---
title: Элемент <Uri> (параметры URI)
ms.date: 03/30/2017
ms.assetid: c22bab8b-477c-4ae4-8498-65ad409e0847
ms.openlocfilehash: f432be7594b1659dfcae0c6eee706358230f2cbb
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55269254"
---
# <a name="uri-element-uri-settings"></a><span data-ttu-id="b440f-102">\<URI > (параметры Uri)</span><span class="sxs-lookup"><span data-stu-id="b440f-102">\<Uri> Element (Uri Settings)</span></span>
<span data-ttu-id="b440f-103">Содержит параметры, определяющие, каким образом платформа .NET Framework обрабатывает веб-адреса, выраженные с использованием универсальных кодов ресурсов (URI).</span><span class="sxs-lookup"><span data-stu-id="b440f-103">Contains settings that specify how the .NET Framework handles web addresses expressed using uniform resource identifiers (URIs).</span></span>  
  
## <a name="schema-hierarchy"></a><span data-ttu-id="b440f-104">Схема иерархии</span><span class="sxs-lookup"><span data-stu-id="b440f-104">Schema Hierarchy</span></span>  
 [<span data-ttu-id="b440f-105">Элемент \<configuration></span><span class="sxs-lookup"><span data-stu-id="b440f-105">\<configuration> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)  
  
 [<span data-ttu-id="b440f-106">\<URI ></span><span class="sxs-lookup"><span data-stu-id="b440f-106">\<uri></span></span>](../../../../../docs/framework/configure-apps/file-schema/network/uri-element-uri-settings.md)  
  
## <a name="syntax"></a><span data-ttu-id="b440f-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b440f-107">Syntax</span></span>  
  
```xml  
<uri>  
</uri>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b440f-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="b440f-108">Attributes and Elements</span></span>  
 <span data-ttu-id="b440f-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="b440f-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b440f-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="b440f-110">Attributes</span></span>  
 <span data-ttu-id="b440f-111">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="b440f-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="b440f-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="b440f-112">Child Elements</span></span>  
  
|<span data-ttu-id="b440f-113">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="b440f-113">**Element**</span></span>|<span data-ttu-id="b440f-114">**Описание**</span><span class="sxs-lookup"><span data-stu-id="b440f-114">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="b440f-115">idn</span><span class="sxs-lookup"><span data-stu-id="b440f-115">idn</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/idn-element-uri-settings.md)|<span data-ttu-id="b440f-116">Определяет, применяется ли к доменным именам анализ международных доменных имен (IDN).</span><span class="sxs-lookup"><span data-stu-id="b440f-116">Specifies if Internationalized Domain Name (IDN) parsing is applied to domain names.</span></span>|  
|[<span data-ttu-id="b440f-117">iriParsing</span><span class="sxs-lookup"><span data-stu-id="b440f-117">iriParsing</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/iriparsing-element-uri-settings.md)|<span data-ttu-id="b440f-118">Указывает, применяется ли синтаксический анализ международного кода ресурса (IRI) к <xref:System.Uri> и должны ли применяться правила синтаксического анализа IRI.</span><span class="sxs-lookup"><span data-stu-id="b440f-118">Specifies if International Resource Identifier (IRI) parsing is applied to <xref:System.Uri> and whether IRI parsing rules should be applied.</span></span>|  
|[<span data-ttu-id="b440f-119">schemeSettings</span><span class="sxs-lookup"><span data-stu-id="b440f-119">schemeSettings</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/schemesettings-element-uri-settings.md)|<span data-ttu-id="b440f-120">Определяет, как <xref:System.Uri> анализируется для определенных схем.</span><span class="sxs-lookup"><span data-stu-id="b440f-120">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b440f-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="b440f-121">Parent Elements</span></span>  
  
|<span data-ttu-id="b440f-122">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="b440f-122">**Element**</span></span>|<span data-ttu-id="b440f-123">**Описание**</span><span class="sxs-lookup"><span data-stu-id="b440f-123">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="b440f-124">Конфигурации</span><span class="sxs-lookup"><span data-stu-id="b440f-124">configuration</span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|<span data-ttu-id="b440f-125">Содержит параметры для всех пространств имен.</span><span class="sxs-lookup"><span data-stu-id="b440f-125">Contains settings for all namespaces.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b440f-126">Примечания</span><span class="sxs-lookup"><span data-stu-id="b440f-126">Remarks</span></span>  
 <span data-ttu-id="b440f-127">`uri` Элемент содержит параметры для членов <xref:System.Uri> класс, используемый классами в <xref:System.Net> пространства имен.</span><span class="sxs-lookup"><span data-stu-id="b440f-127">The `uri` element contains settings for members of the <xref:System.Uri> class used by classes in the <xref:System.Net> namespace.</span></span> <span data-ttu-id="b440f-128">Параметры настраивать поддержку IRI и IDN.</span><span class="sxs-lookup"><span data-stu-id="b440f-128">The settings configure support for IRI and IDN.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b440f-129">Пример</span><span class="sxs-lookup"><span data-stu-id="b440f-129">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="b440f-130">Описание:</span><span class="sxs-lookup"><span data-stu-id="b440f-130">Description</span></span>  
 <span data-ttu-id="b440f-131">В следующем примере показано конфигурацию, используемую <xref:System.Uri> класс для поддержки синтаксического анализа IRI и IDN-имена.</span><span class="sxs-lookup"><span data-stu-id="b440f-131">The following example shows a configuration used by the <xref:System.Uri> class to support IRI parsing and IDN names.</span></span> <span data-ttu-id="b440f-132">В примере также удаляет все параметры схемы и затем добавляет поддержку не экранирования разделителей закодированные пути для схемы http.</span><span class="sxs-lookup"><span data-stu-id="b440f-132">The example also clears all scheme settings and then adds support for not escaping percent-encoded path delimiters for the http scheme.</span></span>  
  
### <a name="code"></a><span data-ttu-id="b440f-133">Код</span><span class="sxs-lookup"><span data-stu-id="b440f-133">Code</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="b440f-134">См. также</span><span class="sxs-lookup"><span data-stu-id="b440f-134">See also</span></span>
- [<span data-ttu-id="b440f-135">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="b440f-135">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
