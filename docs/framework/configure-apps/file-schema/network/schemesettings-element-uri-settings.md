---
title: Элемент <schemeSettings> (параметры URI)
ms.date: 03/30/2017
ms.assetid: 0ae45c6e-8c4c-4c0d-8b9f-a93824648890
ms.openlocfilehash: 498aef77a1dfd8cffcac73b704b8d1bb6df5d165
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2019
ms.locfileid: "71697761"
---
# <a name="schemesettings-element-uri-settings"></a><span data-ttu-id="8481a-102">Элемент \<schemeSettings > (Параметры URI)</span><span class="sxs-lookup"><span data-stu-id="8481a-102">\<schemeSettings> Element (Uri Settings)</span></span>
<span data-ttu-id="8481a-103">Определяет, как <xref:System.Uri> анализируется для определенных схем.</span><span class="sxs-lookup"><span data-stu-id="8481a-103">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>  
  
[<span data-ttu-id="8481a-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="8481a-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="8481a-105">&nbsp;&nbsp;[ **\<URI >** ](uri-element-uri-settings.md)</span><span class="sxs-lookup"><span data-stu-id="8481a-105">&nbsp;&nbsp;[**\<uri>**](uri-element-uri-settings.md)</span></span>  
<span data-ttu-id="8481a-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<schemeSettings >**</span><span class="sxs-lookup"><span data-stu-id="8481a-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<schemeSettings>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8481a-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8481a-107">Syntax</span></span>  
  
```xml  
<schemeSettings>   
</schemeSettings>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8481a-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="8481a-108">Attributes and Elements</span></span>  
 <span data-ttu-id="8481a-109">Следующие разделы описывают атрибуты, дочерние элементы и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="8481a-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8481a-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="8481a-110">Attributes</span></span>  
 <span data-ttu-id="8481a-111">Нет</span><span class="sxs-lookup"><span data-stu-id="8481a-111">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="8481a-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="8481a-112">Child Elements</span></span>  
  
|<span data-ttu-id="8481a-113">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="8481a-113">**Element**</span></span>|<span data-ttu-id="8481a-114">**Описание**</span><span class="sxs-lookup"><span data-stu-id="8481a-114">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="8481a-115">add</span><span class="sxs-lookup"><span data-stu-id="8481a-115">add</span></span>](add-element-for-schemesettings-uri-settings.md)|<span data-ttu-id="8481a-116">Добавляет параметр схемы для имени схемы.</span><span class="sxs-lookup"><span data-stu-id="8481a-116">Adds a scheme setting for a scheme name.</span></span>|  
|[<span data-ttu-id="8481a-117">clear</span><span class="sxs-lookup"><span data-stu-id="8481a-117">clear</span></span>](clear-element-for-schemesettings-uri-settings.md)|<span data-ttu-id="8481a-118">Удаляет все существующие параметры схемы.</span><span class="sxs-lookup"><span data-stu-id="8481a-118">Clears all existing scheme settings.</span></span>|  
|[<span data-ttu-id="8481a-119">remove</span><span class="sxs-lookup"><span data-stu-id="8481a-119">remove</span></span>](remove-element-for-schemesettings-uri-settings.md)|<span data-ttu-id="8481a-120">Удаляет параметр схемы для имени схемы.</span><span class="sxs-lookup"><span data-stu-id="8481a-120">Removes a scheme setting for a scheme name.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8481a-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="8481a-121">Parent Elements</span></span>  
  
|<span data-ttu-id="8481a-122">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="8481a-122">**Element**</span></span>|<span data-ttu-id="8481a-123">**Описание**</span><span class="sxs-lookup"><span data-stu-id="8481a-123">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="8481a-124">URI</span><span class="sxs-lookup"><span data-stu-id="8481a-124">uri</span></span>](uri-element-uri-settings.md)|<span data-ttu-id="8481a-125">Содержит параметры, определяющие, как .NET Framework обрабатывает веб-адреса, выраженные с помощью универсальных идентификаторов ресурсов (URI).</span><span class="sxs-lookup"><span data-stu-id="8481a-125">Contains settings that specify how the .NET Framework handles web addresses expressed using uniform resource identifiers (URIs).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8481a-126">Примечания</span><span class="sxs-lookup"><span data-stu-id="8481a-126">Remarks</span></span>  
 <span data-ttu-id="8481a-127">По умолчанию класс <xref:System.Uri?displayProperty=nameWithType> отменяет escape-символы в процентах от разделителей закодированного пути перед выполнением сжатия пути.</span><span class="sxs-lookup"><span data-stu-id="8481a-127">By default, the <xref:System.Uri?displayProperty=nameWithType> class un-escapes percent encoded path delimiters before executing path compression.</span></span> <span data-ttu-id="8481a-128">Это было реализовано в качестве механизма безопасности для атак, подобных следующим:</span><span class="sxs-lookup"><span data-stu-id="8481a-128">This was implemented as a security mechanism against attacks like the following:</span></span>  
  
 `http://www.contoso.com/..%2F..%2F/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="8481a-129">Если этот URI передается в модули, которые неправильно обрабатывают закодированные символы процента, это может привести к выполнению следующей команды на сервере:</span><span class="sxs-lookup"><span data-stu-id="8481a-129">If this URI gets passed down to modules not handling percent encoded characters correctly, it could result in the following command being executed by the server:</span></span>  
  
 `c:\Windows\System32\cmd.exe /c dir c:\`  
  
 <span data-ttu-id="8481a-130">По этой причине <xref:System.Uri?displayProperty=nameWithType> класс сначала отменяет escape-разделители путей, а затем применяет сжатие пути.</span><span class="sxs-lookup"><span data-stu-id="8481a-130">For this reason, <xref:System.Uri?displayProperty=nameWithType> class first un-escapes path delimiters and then applies path compression.</span></span> <span data-ttu-id="8481a-131">Результат передачи вредоносного URL-адреса выше в <xref:System.Uri?displayProperty=nameWithType> конструктор класса приводит к следующему URI:</span><span class="sxs-lookup"><span data-stu-id="8481a-131">The result of passing the malicious URL above to <xref:System.Uri?displayProperty=nameWithType> class constructor results in the following URI:</span></span>  
  
 `http://www.microsoft.com/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="8481a-132">Это поведение по умолчанию можно изменить, чтобы не отменять escape-символы в процентах с помощью параметра конфигурации schemeSettings для определенной схемы.</span><span class="sxs-lookup"><span data-stu-id="8481a-132">This default behavior can be modified to not un-escape percent encoded path delimiters using the schemeSettings configuration option for a specific scheme.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="8481a-133">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="8481a-133">Configuration Files</span></span>  
 <span data-ttu-id="8481a-134">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="8481a-134">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="8481a-135">Пример</span><span class="sxs-lookup"><span data-stu-id="8481a-135">Example</span></span>  
 <span data-ttu-id="8481a-136">В следующем примере показана конфигурация, используемая классом <xref:System.Uri> для поддержки не экранирования разделителей пути в кодировке% для схемы HTTP.</span><span class="sxs-lookup"><span data-stu-id="8481a-136">The following example shows a configuration used by the <xref:System.Uri> class to support not escaping percent-encoded path delimiters for the http scheme.</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <schemeSettings>  
      <add name="http" genericUriParserOptions="DontUnescapePathDotsAndSlashes"/>  
    </schemeSettings>  
  </uri>  
</configuration>  
```  
  
## <a name="element-information"></a><span data-ttu-id="8481a-137">Сведения об элементе</span><span class="sxs-lookup"><span data-stu-id="8481a-137">Element Information</span></span>  
  
|||
|-|-|  
|<span data-ttu-id="8481a-138">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="8481a-138">Namespace</span></span>|<span data-ttu-id="8481a-139">System</span><span class="sxs-lookup"><span data-stu-id="8481a-139">System</span></span>|  
|<span data-ttu-id="8481a-140">Имя схемы</span><span class="sxs-lookup"><span data-stu-id="8481a-140">Schema Name</span></span>||  
|<span data-ttu-id="8481a-141">Файл проверки</span><span class="sxs-lookup"><span data-stu-id="8481a-141">Validation File</span></span>||  
|<span data-ttu-id="8481a-142">Может быть пустым</span><span class="sxs-lookup"><span data-stu-id="8481a-142">Can be Empty</span></span>||  
  
## <a name="see-also"></a><span data-ttu-id="8481a-143">См. также:</span><span class="sxs-lookup"><span data-stu-id="8481a-143">See also</span></span>

- <xref:System.Configuration.SchemeSettingElement?displayProperty=nameWithType>
- <xref:System.Configuration.SchemeSettingElementCollection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection.SchemeSettings%2A?displayProperty=nameWithType>
- <xref:System.GenericUriParserOptions?displayProperty=nameWithType>
- <xref:System.Uri?displayProperty=nameWithType>
- [<span data-ttu-id="8481a-144">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="8481a-144">Network Settings Schema</span></span>](index.md)
