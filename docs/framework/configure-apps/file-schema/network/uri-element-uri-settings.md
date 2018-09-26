---
title: '&lt;URI&gt; (параметры Uri)'
ms.date: 03/30/2017
ms.assetid: c22bab8b-477c-4ae4-8498-65ad409e0847
author: mcleblanc
ms.author: markl
ms.openlocfilehash: a58c27500c0258415c12a5fd8e552b3ee43f50e8
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/25/2018
ms.locfileid: "47108914"
---
# <a name="lturigt-element-uri-settings"></a><span data-ttu-id="2b21c-102">&lt;URI&gt; (параметры Uri)</span><span class="sxs-lookup"><span data-stu-id="2b21c-102">&lt;Uri&gt; Element (Uri Settings)</span></span>
<span data-ttu-id="2b21c-103">Содержит параметры, определяющие, каким образом платформа .NET Framework обрабатывает веб-адреса, выраженные с использованием универсальных кодов ресурсов (URI).</span><span class="sxs-lookup"><span data-stu-id="2b21c-103">Contains settings that specify how the .NET Framework handles web addresses expressed using uniform resource identifiers (URIs).</span></span>  
  
## <a name="schema-hierarchy"></a><span data-ttu-id="2b21c-104">Схема иерархии</span><span class="sxs-lookup"><span data-stu-id="2b21c-104">Schema Hierarchy</span></span>  
 [<span data-ttu-id="2b21c-105">Элемент \<configuration></span><span class="sxs-lookup"><span data-stu-id="2b21c-105">\<configuration> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)  
  
 [<span data-ttu-id="2b21c-106">\<URI ></span><span class="sxs-lookup"><span data-stu-id="2b21c-106">\<uri></span></span>](../../../../../docs/framework/configure-apps/file-schema/network/uri-element-uri-settings.md)  
  
## <a name="syntax"></a><span data-ttu-id="2b21c-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2b21c-107">Syntax</span></span>  
  
```xml  
<uri>  
</uri>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2b21c-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="2b21c-108">Attributes and Elements</span></span>  
 <span data-ttu-id="2b21c-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="2b21c-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2b21c-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="2b21c-110">Attributes</span></span>  
 <span data-ttu-id="2b21c-111">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="2b21c-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="2b21c-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="2b21c-112">Child Elements</span></span>  
  
|<span data-ttu-id="2b21c-113">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="2b21c-113">**Element**</span></span>|<span data-ttu-id="2b21c-114">**Описание**</span><span class="sxs-lookup"><span data-stu-id="2b21c-114">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="2b21c-115">IDN</span><span class="sxs-lookup"><span data-stu-id="2b21c-115">idn</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/idn-element-uri-settings.md)|<span data-ttu-id="2b21c-116">Определяет, применяется ли к доменным именам анализ международных доменных имен (IDN).</span><span class="sxs-lookup"><span data-stu-id="2b21c-116">Specifies if Internationalized Domain Name (IDN) parsing is applied to domain names.</span></span>|  
|[<span data-ttu-id="2b21c-117">iriParsing</span><span class="sxs-lookup"><span data-stu-id="2b21c-117">iriParsing</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/iriparsing-element-uri-settings.md)|<span data-ttu-id="2b21c-118">Указывает, применяется ли синтаксический анализ международного кода ресурса (IRI) к <xref:System.Uri> и должны ли применяться правила синтаксического анализа IRI.</span><span class="sxs-lookup"><span data-stu-id="2b21c-118">Specifies if International Resource Identifier (IRI) parsing is applied to <xref:System.Uri> and whether IRI parsing rules should be applied.</span></span>|  
|[<span data-ttu-id="2b21c-119">schemeSettings</span><span class="sxs-lookup"><span data-stu-id="2b21c-119">schemeSettings</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/schemesettings-element-uri-settings.md)|<span data-ttu-id="2b21c-120">Определяет, как <xref:System.Uri> анализируется для определенных схем.</span><span class="sxs-lookup"><span data-stu-id="2b21c-120">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2b21c-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="2b21c-121">Parent Elements</span></span>  
  
|<span data-ttu-id="2b21c-122">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="2b21c-122">**Element**</span></span>|<span data-ttu-id="2b21c-123">**Описание**</span><span class="sxs-lookup"><span data-stu-id="2b21c-123">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="2b21c-124">Конфигурации</span><span class="sxs-lookup"><span data-stu-id="2b21c-124">configuration</span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|<span data-ttu-id="2b21c-125">Содержит параметры для всех пространств имен.</span><span class="sxs-lookup"><span data-stu-id="2b21c-125">Contains settings for all namespaces.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2b21c-126">Примечания</span><span class="sxs-lookup"><span data-stu-id="2b21c-126">Remarks</span></span>  
 <span data-ttu-id="2b21c-127">`uri` Элемент содержит параметры для членов <xref:System.Uri> класс, используемый классами в <xref:System.Net> пространства имен.</span><span class="sxs-lookup"><span data-stu-id="2b21c-127">The `uri` element contains settings for members of the <xref:System.Uri> class used by classes in the <xref:System.Net> namespace.</span></span> <span data-ttu-id="2b21c-128">Параметры настраивать поддержку IRI и IDN.</span><span class="sxs-lookup"><span data-stu-id="2b21c-128">The settings configure support for IRI and IDN.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2b21c-129">Пример</span><span class="sxs-lookup"><span data-stu-id="2b21c-129">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="2b21c-130">Описание</span><span class="sxs-lookup"><span data-stu-id="2b21c-130">Description</span></span>  
 <span data-ttu-id="2b21c-131">В следующем примере показано конфигурацию, используемую <xref:System.Uri> класс для поддержки синтаксического анализа IRI и IDN-имена.</span><span class="sxs-lookup"><span data-stu-id="2b21c-131">The following example shows a configuration used by the <xref:System.Uri> class to support IRI parsing and IDN names.</span></span> <span data-ttu-id="2b21c-132">В примере также удаляет все параметры схемы и затем добавляет поддержку не экранирования разделителей закодированные пути для схемы http.</span><span class="sxs-lookup"><span data-stu-id="2b21c-132">The example also clears all scheme settings and then adds support for not escaping percent-encoded path delimiters for the http scheme.</span></span>  
  
### <a name="code"></a><span data-ttu-id="2b21c-133">Код</span><span class="sxs-lookup"><span data-stu-id="2b21c-133">Code</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="2b21c-134">См. также</span><span class="sxs-lookup"><span data-stu-id="2b21c-134">See Also</span></span>  
 [<span data-ttu-id="2b21c-135">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="2b21c-135">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
