---
title: Элемент <iriParsing> (параметры URI)
ms.date: 03/30/2017
ms.assetid: 953d0b53-445e-41f9-b302-77c4030852ce
ms.openlocfilehash: 2c99edf2f1a03e0e510858c106cad43b0eaa27b4
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/21/2019
ms.locfileid: "69664090"
---
# <a name="iriparsing-element-uri-settings"></a><span data-ttu-id="ac2b3-102">\<Элемент > элемент iriParsing (Параметры URI)</span><span class="sxs-lookup"><span data-stu-id="ac2b3-102">\<iriParsing> Element (Uri Settings)</span></span>
<span data-ttu-id="ac2b3-103">Определяет, применяется ли к <xref:System.Uri> анализ международных идентификаторов ресурсов (IRI) и применяются ли правила анализа IRI.</span><span class="sxs-lookup"><span data-stu-id="ac2b3-103">Specifies if International Resource Identifier (IRI) parsing is applied to a <xref:System.Uri> and whether IRI parsing rules should be applied.</span></span>  
  
## <a name="schema-hierarchy"></a><span data-ttu-id="ac2b3-104">Схема иерархии</span><span class="sxs-lookup"><span data-stu-id="ac2b3-104">Schema Hierarchy</span></span>  
 [<span data-ttu-id="ac2b3-105">Элемент \<configuration></span><span class="sxs-lookup"><span data-stu-id="ac2b3-105">\<configuration> Element</span></span>](../configuration-element.md)  
  
 [<span data-ttu-id="ac2b3-106">\<Элемент > URI (Параметры URI)</span><span class="sxs-lookup"><span data-stu-id="ac2b3-106">\<Uri> Element (Uri Settings)</span></span>](uri-element-uri-settings.md)  
  
 [<span data-ttu-id="ac2b3-107">\<Элемент iriParsing ></span><span class="sxs-lookup"><span data-stu-id="ac2b3-107">\<iriParsing></span></span>](iriparsing-element-uri-settings.md)  
  
## <a name="syntax"></a><span data-ttu-id="ac2b3-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ac2b3-108">Syntax</span></span>  
  
```xml  
<iriParsing  
  enabled="true|false"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ac2b3-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="ac2b3-109">Attributes and Elements</span></span>  
 <span data-ttu-id="ac2b3-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="ac2b3-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ac2b3-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="ac2b3-111">Attributes</span></span>  
  
|<span data-ttu-id="ac2b3-112">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="ac2b3-112">**Element**</span></span>|<span data-ttu-id="ac2b3-113">**Описание**</span><span class="sxs-lookup"><span data-stu-id="ac2b3-113">**Description**</span></span>|  
|-----------------|---------------------|  
|`enabled`|<span data-ttu-id="ac2b3-114">Указывает, включен ли синтаксический анализ IRI.</span><span class="sxs-lookup"><span data-stu-id="ac2b3-114">Specifies whether IRI parsing is enabled.</span></span> <span data-ttu-id="ac2b3-115">Значение по умолчанию — `false`.</span><span class="sxs-lookup"><span data-stu-id="ac2b3-115">The default value is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ac2b3-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="ac2b3-116">Child Elements</span></span>  
 <span data-ttu-id="ac2b3-117">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="ac2b3-117">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ac2b3-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="ac2b3-118">Parent Elements</span></span>  
  
|<span data-ttu-id="ac2b3-119">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="ac2b3-119">**Element**</span></span>|<span data-ttu-id="ac2b3-120">**Описание**</span><span class="sxs-lookup"><span data-stu-id="ac2b3-120">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="ac2b3-121">URI</span><span class="sxs-lookup"><span data-stu-id="ac2b3-121">uri</span></span>](uri-element-uri-settings.md)|<span data-ttu-id="ac2b3-122">Содержит параметры, определяющие, как .NET Framework обрабатывает веб-адреса, выраженные с помощью универсальных идентификаторов ресурсов (URI).</span><span class="sxs-lookup"><span data-stu-id="ac2b3-122">Contains settings that specify how the .NET Framework handles web addresses expressed using uniform resource identifiers (URIs).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ac2b3-123">Примечания</span><span class="sxs-lookup"><span data-stu-id="ac2b3-123">Remarks</span></span>  
 <span data-ttu-id="ac2b3-124">Существующий <xref:System.Uri> класс был расширен в .NET Framework 3,5.</span><span class="sxs-lookup"><span data-stu-id="ac2b3-124">The existing <xref:System.Uri> class has been extended in .NET Framework 3.5.</span></span> <span data-ttu-id="ac2b3-125">3,0 с пакетом обновления 1 (SP1) и 2,0 SP1 для предоставления поддержки международных идентификаторов ресурсов (IRI) и международных доменных имен (IDN).</span><span class="sxs-lookup"><span data-stu-id="ac2b3-125">3.0 SP1, and 2.0 SP1 to provide support for International Resource Identifiers (IRI) and Internationalized Domain Names (IDN).</span></span> <span data-ttu-id="ac2b3-126">Текущие пользователи не увидят каких бы то ни было изменений в работе .NET Framework 2,0, если они специально не включают поддержку IRI и IDN.</span><span class="sxs-lookup"><span data-stu-id="ac2b3-126">Current users will not see any change from the .NET Framework 2.0 behavior unless they specifically enable IRI and IDN support.</span></span> <span data-ttu-id="ac2b3-127">Это обеспечивает совместимость приложений с предыдущими версиями платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ac2b3-127">This ensures application compatibility with prior versions of the .NET Framework.</span></span>  
  
 <span data-ttu-id="ac2b3-128">Чтобы включить поддержку IRI, требуются следующие два изменения:</span><span class="sxs-lookup"><span data-stu-id="ac2b3-128">To enable support for IRI, the following two changes are required:</span></span>  
  
1. <span data-ttu-id="ac2b3-129">Добавьте следующую строку в файл Machine. config в каталоге .NET Framework 2,0.</span><span class="sxs-lookup"><span data-stu-id="ac2b3-129">Add the following line to the machine.config file under the .NET Framework 2.0 directory</span></span>  
  
    ```xml  
    <section name="uri" type="System.Configuration.UriSection, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
    ```  
  
2. <span data-ttu-id="ac2b3-130">Укажите, следует ли применять правила синтаксического анализа IRI.</span><span class="sxs-lookup"><span data-stu-id="ac2b3-130">Specify whether IRI parsing rules should be applied.</span></span> <span data-ttu-id="ac2b3-131">Это можно сделать в файле machine.config или в файле app.config.</span><span class="sxs-lookup"><span data-stu-id="ac2b3-131">This can be done in the machine.config or in the app.config file.</span></span>  
  
 <span data-ttu-id="ac2b3-132">Включение синтаксического анализа IRI (элемент iriParsing enabled `true`=) выполняет нормализацию и проверку символов в соответствии с последними правилами IRI в RFC 3987.</span><span class="sxs-lookup"><span data-stu-id="ac2b3-132">Enabling IRI parsing (iriParsing enabled = `true`) will do normalization and character checking according to the latest IRI rules in RFC 3987.</span></span> <span data-ttu-id="ac2b3-133">Значение по умолчанию `false` — и будет выполнять нормализацию и проверку символов в соответствии с RFC 2396 и RFC 3986 (для литералов IPv6).</span><span class="sxs-lookup"><span data-stu-id="ac2b3-133">The default value is `false` and will do normalization and character checking according to RFC 2396 and RFC 3986 (for IPv6 literals).</span></span>  
  
### <a name="configuration-files"></a><span data-ttu-id="ac2b3-134">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="ac2b3-134">Configuration Files</span></span>  
 <span data-ttu-id="ac2b3-135">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="ac2b3-135">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ac2b3-136">Пример</span><span class="sxs-lookup"><span data-stu-id="ac2b3-136">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="ac2b3-137">Описание</span><span class="sxs-lookup"><span data-stu-id="ac2b3-137">Description</span></span>  
 <span data-ttu-id="ac2b3-138">В следующем примере показана конфигурация, используемая <xref:System.Uri> классом для поддержки синтаксического анализа IRI и имен IDN.</span><span class="sxs-lookup"><span data-stu-id="ac2b3-138">The following example shows a configuration used by the <xref:System.Uri> class to support IRI parsing and IDN names.</span></span>  
  
### <a name="code"></a><span data-ttu-id="ac2b3-139">Код</span><span class="sxs-lookup"><span data-stu-id="ac2b3-139">Code</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <idn enabled="All" />  
    <iriParsing enabled="true" />  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="ac2b3-140">См. также</span><span class="sxs-lookup"><span data-stu-id="ac2b3-140">See also</span></span>

- <xref:System.Configuration.IriParsingElement?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- [<span data-ttu-id="ac2b3-141">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="ac2b3-141">Network Settings Schema</span></span>](index.md)
