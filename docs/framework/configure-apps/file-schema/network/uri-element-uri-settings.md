---
title: Элемент <uri> (параметры URI)
ms.date: 03/30/2017
ms.assetid: c22bab8b-477c-4ae4-8498-65ad409e0847
ms.openlocfilehash: a492baf9951466383ca0277a2927b8554e5bb332
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2019
ms.locfileid: "71697442"
---
# <a name="uri-element-uri-settings"></a><span data-ttu-id="b489b-102">Элемент > \<URI (Параметры URI)</span><span class="sxs-lookup"><span data-stu-id="b489b-102">\<uri> Element (Uri Settings)</span></span>
<span data-ttu-id="b489b-103">Содержит параметры, определяющие, как .NET Framework обрабатывает веб-адреса, выраженные с помощью универсальных идентификаторов ресурсов (URI).</span><span class="sxs-lookup"><span data-stu-id="b489b-103">Contains settings that specify how the .NET Framework handles web addresses expressed using uniform resource identifiers (URIs).</span></span>  
  
[<span data-ttu-id="b489b-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="b489b-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="b489b-105">&nbsp;&nbsp; **\<uri >**</span><span class="sxs-lookup"><span data-stu-id="b489b-105">&nbsp;&nbsp;**\<uri>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b489b-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b489b-106">Syntax</span></span>  
  
```xml  
<uri>  
</uri>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b489b-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="b489b-107">Attributes and Elements</span></span>  
 <span data-ttu-id="b489b-108">Следующие разделы описывают атрибуты, дочерние элементы и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="b489b-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b489b-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="b489b-109">Attributes</span></span>  
 <span data-ttu-id="b489b-110">Нет</span><span class="sxs-lookup"><span data-stu-id="b489b-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="b489b-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="b489b-111">Child Elements</span></span>  
  
|<span data-ttu-id="b489b-112">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="b489b-112">**Element**</span></span>|<span data-ttu-id="b489b-113">**Описание**</span><span class="sxs-lookup"><span data-stu-id="b489b-113">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="b489b-114">IDN</span><span class="sxs-lookup"><span data-stu-id="b489b-114">idn</span></span>](idn-element-uri-settings.md)|<span data-ttu-id="b489b-115">Определяет, применяется ли к доменным именам анализ международных доменных имен (IDN).</span><span class="sxs-lookup"><span data-stu-id="b489b-115">Specifies if Internationalized Domain Name (IDN) parsing is applied to domain names.</span></span>|  
|[<span data-ttu-id="b489b-116">Элемент iriParsing</span><span class="sxs-lookup"><span data-stu-id="b489b-116">iriParsing</span></span>](iriparsing-element-uri-settings.md)|<span data-ttu-id="b489b-117">Указывает, применяется ли синтаксический анализ международного идентификатора ресурса (IRI) к <xref:System.Uri> и должны применяться правила синтаксического анализа IRI.</span><span class="sxs-lookup"><span data-stu-id="b489b-117">Specifies if International Resource Identifier (IRI) parsing is applied to <xref:System.Uri> and whether IRI parsing rules should be applied.</span></span>|  
|[<span data-ttu-id="b489b-118">schemeSettings</span><span class="sxs-lookup"><span data-stu-id="b489b-118">schemeSettings</span></span>](schemesettings-element-uri-settings.md)|<span data-ttu-id="b489b-119">Определяет, как <xref:System.Uri> анализируется для определенных схем.</span><span class="sxs-lookup"><span data-stu-id="b489b-119">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b489b-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="b489b-120">Parent Elements</span></span>  
  
|<span data-ttu-id="b489b-121">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="b489b-121">**Element**</span></span>|<span data-ttu-id="b489b-122">**Описание**</span><span class="sxs-lookup"><span data-stu-id="b489b-122">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="b489b-123">Настройка</span><span class="sxs-lookup"><span data-stu-id="b489b-123">configuration</span></span>](../configuration-element.md)|<span data-ttu-id="b489b-124">Содержит параметры для всех пространств имен.</span><span class="sxs-lookup"><span data-stu-id="b489b-124">Contains settings for all namespaces.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b489b-125">Примечания</span><span class="sxs-lookup"><span data-stu-id="b489b-125">Remarks</span></span>  
 <span data-ttu-id="b489b-126">Элемент `uri` содержит параметры для членов класса <xref:System.Uri>, используемых классами в пространстве имен <xref:System.Net>.</span><span class="sxs-lookup"><span data-stu-id="b489b-126">The `uri` element contains settings for members of the <xref:System.Uri> class used by classes in the <xref:System.Net> namespace.</span></span> <span data-ttu-id="b489b-127">Параметры настраивают поддержку для IRI и IDN.</span><span class="sxs-lookup"><span data-stu-id="b489b-127">The settings configure support for IRI and IDN.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b489b-128">Пример</span><span class="sxs-lookup"><span data-stu-id="b489b-128">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="b489b-129">Описание</span><span class="sxs-lookup"><span data-stu-id="b489b-129">Description</span></span>  
 <span data-ttu-id="b489b-130">В следующем примере показана конфигурация, используемая классом <xref:System.Uri> для поддержки синтаксического анализа IRI и имен IDN.</span><span class="sxs-lookup"><span data-stu-id="b489b-130">The following example shows a configuration used by the <xref:System.Uri> class to support IRI parsing and IDN names.</span></span> <span data-ttu-id="b489b-131">В этом примере также очищаются все параметры схемы, а затем добавляется поддержка не экранирования процентов для пути, закодированного для схемы HTTP.</span><span class="sxs-lookup"><span data-stu-id="b489b-131">The example also clears all scheme settings and then adds support for not escaping percent-encoded path delimiters for the http scheme.</span></span>  
  
### <a name="code"></a><span data-ttu-id="b489b-132">Код</span><span class="sxs-lookup"><span data-stu-id="b489b-132">Code</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="b489b-133">См. также:</span><span class="sxs-lookup"><span data-stu-id="b489b-133">See also</span></span>

- [<span data-ttu-id="b489b-134">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="b489b-134">Network Settings Schema</span></span>](index.md)
