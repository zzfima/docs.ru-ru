---
title: Элемент <iriParsing> (параметры URI)
ms.date: 03/30/2017
ms.assetid: 953d0b53-445e-41f9-b302-77c4030852ce
ms.openlocfilehash: fd617d1b4ac8e532c6f9aeaa01465e9866b059e9
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2019
ms.locfileid: "71698096"
---
# <a name="iriparsing-element-uri-settings"></a><span data-ttu-id="e3b39-102">Элемент \<элемент iriParsing > (Параметры URI)</span><span class="sxs-lookup"><span data-stu-id="e3b39-102">\<iriParsing> Element (Uri Settings)</span></span>
<span data-ttu-id="e3b39-103">Определяет, применяется ли к <xref:System.Uri> анализ международных идентификаторов ресурсов (IRI) и применяются ли правила анализа IRI.</span><span class="sxs-lookup"><span data-stu-id="e3b39-103">Specifies if International Resource Identifier (IRI) parsing is applied to a <xref:System.Uri> and whether IRI parsing rules should be applied.</span></span>  
  
[<span data-ttu-id="e3b39-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="e3b39-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="e3b39-105">&nbsp;&nbsp;[ **\<URI >** ](uri-element-uri-settings.md)</span><span class="sxs-lookup"><span data-stu-id="e3b39-105">&nbsp;&nbsp;[**\<uri>**](uri-element-uri-settings.md)</span></span>  
<span data-ttu-id="e3b39-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<элемент iriparsing >**</span><span class="sxs-lookup"><span data-stu-id="e3b39-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<iriParsing>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e3b39-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e3b39-107">Syntax</span></span>  
  
```xml  
<iriParsing  
  enabled="true|false"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e3b39-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="e3b39-108">Attributes and Elements</span></span>  
 <span data-ttu-id="e3b39-109">Следующие разделы описывают атрибуты, дочерние элементы и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="e3b39-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e3b39-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="e3b39-110">Attributes</span></span>  
  
|<span data-ttu-id="e3b39-111">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="e3b39-111">**Element**</span></span>|<span data-ttu-id="e3b39-112">**Описание**</span><span class="sxs-lookup"><span data-stu-id="e3b39-112">**Description**</span></span>|  
|-----------------|---------------------|  
|`enabled`|<span data-ttu-id="e3b39-113">Указывает, включен ли синтаксический анализ IRI.</span><span class="sxs-lookup"><span data-stu-id="e3b39-113">Specifies whether IRI parsing is enabled.</span></span> <span data-ttu-id="e3b39-114">Значение по умолчанию — `false`.</span><span class="sxs-lookup"><span data-stu-id="e3b39-114">The default value is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e3b39-115">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="e3b39-115">Child Elements</span></span>  
 <span data-ttu-id="e3b39-116">Нет</span><span class="sxs-lookup"><span data-stu-id="e3b39-116">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e3b39-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="e3b39-117">Parent Elements</span></span>  
  
|<span data-ttu-id="e3b39-118">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="e3b39-118">**Element**</span></span>|<span data-ttu-id="e3b39-119">**Описание**</span><span class="sxs-lookup"><span data-stu-id="e3b39-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="e3b39-120">URI</span><span class="sxs-lookup"><span data-stu-id="e3b39-120">uri</span></span>](uri-element-uri-settings.md)|<span data-ttu-id="e3b39-121">Содержит параметры, определяющие, как .NET Framework обрабатывает веб-адреса, выраженные с помощью универсальных идентификаторов ресурсов (URI).</span><span class="sxs-lookup"><span data-stu-id="e3b39-121">Contains settings that specify how the .NET Framework handles web addresses expressed using uniform resource identifiers (URIs).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e3b39-122">Примечания</span><span class="sxs-lookup"><span data-stu-id="e3b39-122">Remarks</span></span>  
 <span data-ttu-id="e3b39-123">Существующий класс <xref:System.Uri> был расширен в .NET Framework 3,5.</span><span class="sxs-lookup"><span data-stu-id="e3b39-123">The existing <xref:System.Uri> class has been extended in .NET Framework 3.5.</span></span> <span data-ttu-id="e3b39-124">3,0 с пакетом обновления 1 (SP1) и 2,0 SP1 для предоставления поддержки международных идентификаторов ресурсов (IRI) и международных доменных имен (IDN).</span><span class="sxs-lookup"><span data-stu-id="e3b39-124">3.0 SP1, and 2.0 SP1 to provide support for International Resource Identifiers (IRI) and Internationalized Domain Names (IDN).</span></span> <span data-ttu-id="e3b39-125">Текущие пользователи не увидят каких бы то ни было изменений в работе .NET Framework 2,0, если они специально не включают поддержку IRI и IDN.</span><span class="sxs-lookup"><span data-stu-id="e3b39-125">Current users will not see any change from the .NET Framework 2.0 behavior unless they specifically enable IRI and IDN support.</span></span> <span data-ttu-id="e3b39-126">Это обеспечивает совместимость приложений с предыдущими версиями платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e3b39-126">This ensures application compatibility with prior versions of the .NET Framework.</span></span>  
  
 <span data-ttu-id="e3b39-127">Чтобы включить поддержку IRI, требуются следующие два изменения:</span><span class="sxs-lookup"><span data-stu-id="e3b39-127">To enable support for IRI, the following two changes are required:</span></span>  
  
1. <span data-ttu-id="e3b39-128">Добавьте следующую строку в файл Machine. config в каталоге .NET Framework 2,0.</span><span class="sxs-lookup"><span data-stu-id="e3b39-128">Add the following line to the machine.config file under the .NET Framework 2.0 directory</span></span>  
  
    ```xml  
    <section name="uri" type="System.Configuration.UriSection, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
    ```  
  
2. <span data-ttu-id="e3b39-129">Укажите, следует ли применять правила синтаксического анализа IRI.</span><span class="sxs-lookup"><span data-stu-id="e3b39-129">Specify whether IRI parsing rules should be applied.</span></span> <span data-ttu-id="e3b39-130">Это можно сделать в файле machine.config или в файле app.config.</span><span class="sxs-lookup"><span data-stu-id="e3b39-130">This can be done in the machine.config or in the app.config file.</span></span>  
  
 <span data-ttu-id="e3b39-131">Включение синтаксического анализа IRI (элемент iriParsing enabled = `true`) будет выполнять нормализацию и проверку символов в соответствии с последними правилами IRI в RFC 3987.</span><span class="sxs-lookup"><span data-stu-id="e3b39-131">Enabling IRI parsing (iriParsing enabled = `true`) will do normalization and character checking according to the latest IRI rules in RFC 3987.</span></span> <span data-ttu-id="e3b39-132">Значение по умолчанию — `false` и будет выполнять нормализацию и проверку символов в соответствии с RFC 2396 и RFC 3986 (для литералов IPv6).</span><span class="sxs-lookup"><span data-stu-id="e3b39-132">The default value is `false` and will do normalization and character checking according to RFC 2396 and RFC 3986 (for IPv6 literals).</span></span>  
  
### <a name="configuration-files"></a><span data-ttu-id="e3b39-133">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="e3b39-133">Configuration Files</span></span>  
 <span data-ttu-id="e3b39-134">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="e3b39-134">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e3b39-135">Пример</span><span class="sxs-lookup"><span data-stu-id="e3b39-135">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="e3b39-136">Описание</span><span class="sxs-lookup"><span data-stu-id="e3b39-136">Description</span></span>  
 <span data-ttu-id="e3b39-137">В следующем примере показана конфигурация, используемая классом <xref:System.Uri> для поддержки синтаксического анализа IRI и имен IDN.</span><span class="sxs-lookup"><span data-stu-id="e3b39-137">The following example shows a configuration used by the <xref:System.Uri> class to support IRI parsing and IDN names.</span></span>  
  
### <a name="code"></a><span data-ttu-id="e3b39-138">Код</span><span class="sxs-lookup"><span data-stu-id="e3b39-138">Code</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <idn enabled="All" />  
    <iriParsing enabled="true" />  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e3b39-139">См. также:</span><span class="sxs-lookup"><span data-stu-id="e3b39-139">See also</span></span>

- <xref:System.Configuration.IriParsingElement?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- [<span data-ttu-id="e3b39-140">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="e3b39-140">Network Settings Schema</span></span>](index.md)
