---
title: "&lt;URI&gt; элемент (параметры Uri)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c22bab8b-477c-4ae4-8498-65ad409e0847
caps.latest.revision: "11"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 735a6596b22e6d6fdcff776dd79224230db5b7b3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="lturigt-element-uri-settings"></a><span data-ttu-id="fccf4-102">&lt;URI&gt; элемент (параметры Uri)</span><span class="sxs-lookup"><span data-stu-id="fccf4-102">&lt;Uri&gt; Element (Uri Settings)</span></span>
<span data-ttu-id="fccf4-103">Содержит параметры, определяющие, как платформа .NET Framework обрабатывает веб-адреса, выраженные с использованием универсальных кодов ресурсов (URI).</span><span class="sxs-lookup"><span data-stu-id="fccf4-103">Contains settings that specify how the .NET Framework handles web addresses expressed using uniform resource identifiers (URIs).</span></span>  
  
## <a name="schema-hierarchy"></a><span data-ttu-id="fccf4-104">Схема иерархии</span><span class="sxs-lookup"><span data-stu-id="fccf4-104">Schema Hierarchy</span></span>  
 [<span data-ttu-id="fccf4-105">Элемент \<configuration></span><span class="sxs-lookup"><span data-stu-id="fccf4-105">\<configuration> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)  
  
 [<span data-ttu-id="fccf4-106">\<URI ></span><span class="sxs-lookup"><span data-stu-id="fccf4-106">\<uri></span></span>](../../../../../docs/framework/configure-apps/file-schema/network/uri-element-uri-settings.md)  
  
## <a name="syntax"></a><span data-ttu-id="fccf4-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fccf4-107">Syntax</span></span>  
  
```xml  
<uri>  
</uri>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fccf4-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="fccf4-108">Attributes and Elements</span></span>  
 <span data-ttu-id="fccf4-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="fccf4-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fccf4-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="fccf4-110">Attributes</span></span>  
 <span data-ttu-id="fccf4-111">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="fccf4-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="fccf4-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="fccf4-112">Child Elements</span></span>  
  
|<span data-ttu-id="fccf4-113">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="fccf4-113">**Element**</span></span>|<span data-ttu-id="fccf4-114">**Описание**</span><span class="sxs-lookup"><span data-stu-id="fccf4-114">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="fccf4-115">IDN</span><span class="sxs-lookup"><span data-stu-id="fccf4-115">idn</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/idn-element-uri-settings.md)|<span data-ttu-id="fccf4-116">Определяет, применяется ли к доменным именам анализ международных доменных имен (IDN).</span><span class="sxs-lookup"><span data-stu-id="fccf4-116">Specifies if Internationalized Domain Name (IDN) parsing is applied to domain names.</span></span>|  
|[<span data-ttu-id="fccf4-117">iriParsing</span><span class="sxs-lookup"><span data-stu-id="fccf4-117">iriParsing</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/iriparsing-element-uri-settings.md)|<span data-ttu-id="fccf4-118">Указывает, применяется ли синтаксический анализ международного кода ресурса (IRI) к <xref:System.Uri> и следует ли применять правила синтаксического анализа IRI.</span><span class="sxs-lookup"><span data-stu-id="fccf4-118">Specifies if International Resource Identifier (IRI) parsing is applied to <xref:System.Uri> and whether IRI parsing rules should be applied.</span></span>|  
|[<span data-ttu-id="fccf4-119">schemeSettings</span><span class="sxs-lookup"><span data-stu-id="fccf4-119">schemeSettings</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/schemesettings-element-uri-settings.md)|<span data-ttu-id="fccf4-120">Определяет, как <xref:System.Uri> анализируется для определенных схем.</span><span class="sxs-lookup"><span data-stu-id="fccf4-120">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="fccf4-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="fccf4-121">Parent Elements</span></span>  
  
|<span data-ttu-id="fccf4-122">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="fccf4-122">**Element**</span></span>|<span data-ttu-id="fccf4-123">**Описание**</span><span class="sxs-lookup"><span data-stu-id="fccf4-123">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="fccf4-124">конфигурации</span><span class="sxs-lookup"><span data-stu-id="fccf4-124">configuration</span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|<span data-ttu-id="fccf4-125">Содержит параметры для всех пространств имен.</span><span class="sxs-lookup"><span data-stu-id="fccf4-125">Contains settings for all namespaces.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fccf4-126">Примечания</span><span class="sxs-lookup"><span data-stu-id="fccf4-126">Remarks</span></span>  
 <span data-ttu-id="fccf4-127">`uri` Элемент содержит настройки для членов <xref:System.Uri> класс, используемый классами в <xref:System.Net> пространства имен.</span><span class="sxs-lookup"><span data-stu-id="fccf4-127">The `uri` element contains settings for members of the <xref:System.Uri> class used by classes in the <xref:System.Net> namespace.</span></span> <span data-ttu-id="fccf4-128">Параметры настройки поддержки IRI и IDN.</span><span class="sxs-lookup"><span data-stu-id="fccf4-128">The settings configure support for IRI and IDN.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fccf4-129">Пример</span><span class="sxs-lookup"><span data-stu-id="fccf4-129">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="fccf4-130">Описание:</span><span class="sxs-lookup"><span data-stu-id="fccf4-130">Description</span></span>  
 <span data-ttu-id="fccf4-131">В следующем примере показано конфигурацию, используемую <xref:System.Uri> класс для поддержки синтаксического анализа IRI и имен IDN.</span><span class="sxs-lookup"><span data-stu-id="fccf4-131">The following example shows a configuration used by the <xref:System.Uri> class to support IRI parsing and IDN names.</span></span> <span data-ttu-id="fccf4-132">В примере также сбрасываются все параметры схем и добавляется поддержка не экранирования разделителей закодированные пути для схемы http.</span><span class="sxs-lookup"><span data-stu-id="fccf4-132">The example also clears all scheme settings and then adds support for not escaping percent-encoded path delimiters for the http scheme.</span></span>  
  
### <a name="code"></a><span data-ttu-id="fccf4-133">Код</span><span class="sxs-lookup"><span data-stu-id="fccf4-133">Code</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="fccf4-134">См. также</span><span class="sxs-lookup"><span data-stu-id="fccf4-134">See Also</span></span>  
 [<span data-ttu-id="fccf4-135">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="fccf4-135">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
