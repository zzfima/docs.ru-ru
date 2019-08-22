---
title: Элемент <schemeSettings> (параметры URI)
ms.date: 03/30/2017
ms.assetid: 0ae45c6e-8c4c-4c0d-8b9f-a93824648890
ms.openlocfilehash: 46012b15d41422fb3357e57438e320136809ef41
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/21/2019
ms.locfileid: "69664008"
---
# <a name="schemesettings-element-uri-settings"></a><span data-ttu-id="320dd-102">\<Элемент > schemeSettings (Параметры URI)</span><span class="sxs-lookup"><span data-stu-id="320dd-102">\<schemeSettings> Element (Uri Settings)</span></span>
<span data-ttu-id="320dd-103">Определяет, как <xref:System.Uri> анализируется для определенных схем.</span><span class="sxs-lookup"><span data-stu-id="320dd-103">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>  
  
 <span data-ttu-id="320dd-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="320dd-104">\<configuration></span></span>  
<span data-ttu-id="320dd-105">\<> URI</span><span class="sxs-lookup"><span data-stu-id="320dd-105">\<uri></span></span>  
<span data-ttu-id="320dd-106">\<schemeSettings ></span><span class="sxs-lookup"><span data-stu-id="320dd-106">\<schemeSettings></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="320dd-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="320dd-107">Syntax</span></span>  
  
```xml  
<schemeSettings>   
</schemeSettings>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="320dd-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="320dd-108">Attributes and Elements</span></span>  
 <span data-ttu-id="320dd-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="320dd-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="320dd-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="320dd-110">Attributes</span></span>  
 <span data-ttu-id="320dd-111">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="320dd-111">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="320dd-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="320dd-112">Child Elements</span></span>  
  
|<span data-ttu-id="320dd-113">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="320dd-113">**Element**</span></span>|<span data-ttu-id="320dd-114">**Описание**</span><span class="sxs-lookup"><span data-stu-id="320dd-114">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="320dd-115">add</span><span class="sxs-lookup"><span data-stu-id="320dd-115">add</span></span>](add-element-for-schemesettings-uri-settings.md)|<span data-ttu-id="320dd-116">Добавляет параметр схемы для имени схемы.</span><span class="sxs-lookup"><span data-stu-id="320dd-116">Adds a scheme setting for a scheme name.</span></span>|  
|[<span data-ttu-id="320dd-117">clear</span><span class="sxs-lookup"><span data-stu-id="320dd-117">clear</span></span>](clear-element-for-schemesettings-uri-settings.md)|<span data-ttu-id="320dd-118">Удаляет все существующие параметры схемы.</span><span class="sxs-lookup"><span data-stu-id="320dd-118">Clears all existing scheme settings.</span></span>|  
|[<span data-ttu-id="320dd-119">remove</span><span class="sxs-lookup"><span data-stu-id="320dd-119">remove</span></span>](remove-element-for-schemesettings-uri-settings.md)|<span data-ttu-id="320dd-120">Удаляет параметр схемы для имени схемы.</span><span class="sxs-lookup"><span data-stu-id="320dd-120">Removes a scheme setting for a scheme name.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="320dd-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="320dd-121">Parent Elements</span></span>  
  
|<span data-ttu-id="320dd-122">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="320dd-122">**Element**</span></span>|<span data-ttu-id="320dd-123">**Описание**</span><span class="sxs-lookup"><span data-stu-id="320dd-123">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="320dd-124">URI</span><span class="sxs-lookup"><span data-stu-id="320dd-124">uri</span></span>](uri-element-uri-settings.md)|<span data-ttu-id="320dd-125">Содержит параметры, определяющие, как .NET Framework обрабатывает веб-адреса, выраженные с помощью универсальных идентификаторов ресурсов (URI).</span><span class="sxs-lookup"><span data-stu-id="320dd-125">Contains settings that specify how the .NET Framework handles web addresses expressed using uniform resource identifiers (URIs).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="320dd-126">Примечания</span><span class="sxs-lookup"><span data-stu-id="320dd-126">Remarks</span></span>  
 <span data-ttu-id="320dd-127">По умолчанию класс <xref:System.Uri?displayProperty=nameWithType> отменяет escape-символы в процентах, закодированные разделителями, перед выполнением сжатия пути.</span><span class="sxs-lookup"><span data-stu-id="320dd-127">By default, the <xref:System.Uri?displayProperty=nameWithType> class un-escapes percent encoded path delimiters before executing path compression.</span></span> <span data-ttu-id="320dd-128">Это было реализовано в качестве механизма безопасности для атак, подобных следующим:</span><span class="sxs-lookup"><span data-stu-id="320dd-128">This was implemented as a security mechanism against attacks like the following:</span></span>  
  
 `http://www.contoso.com/..%2F..%2F/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="320dd-129">Если этот URI передается в модули, которые неправильно обрабатывают закодированные символы процента, это может привести к выполнению следующей команды на сервере:</span><span class="sxs-lookup"><span data-stu-id="320dd-129">If this URI gets passed down to modules not handling percent encoded characters correctly, it could result in the following command being executed by the server:</span></span>  
  
 `c:\Windows\System32\cmd.exe /c dir c:\`  
  
 <span data-ttu-id="320dd-130">По этой причине <xref:System.Uri?displayProperty=nameWithType> класс сначала отменяет escape-разделители путей, а затем применяет сжатие пути.</span><span class="sxs-lookup"><span data-stu-id="320dd-130">For this reason, <xref:System.Uri?displayProperty=nameWithType> class first un-escapes path delimiters and then applies path compression.</span></span> <span data-ttu-id="320dd-131">Результат передачи вредоносного URL-адреса выше в <xref:System.Uri?displayProperty=nameWithType> конструктор класса приводит к следующему URI:</span><span class="sxs-lookup"><span data-stu-id="320dd-131">The result of passing the malicious URL above to <xref:System.Uri?displayProperty=nameWithType> class constructor results in the following URI:</span></span>  
  
 `http://www.microsoft.com/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="320dd-132">Это поведение по умолчанию можно изменить, чтобы не отменять escape-символы в процентах с помощью параметра конфигурации schemeSettings для определенной схемы.</span><span class="sxs-lookup"><span data-stu-id="320dd-132">This default behavior can be modified to not un-escape percent encoded path delimiters using the schemeSettings configuration option for a specific scheme.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="320dd-133">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="320dd-133">Configuration Files</span></span>  
 <span data-ttu-id="320dd-134">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="320dd-134">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="320dd-135">Пример</span><span class="sxs-lookup"><span data-stu-id="320dd-135">Example</span></span>  
 <span data-ttu-id="320dd-136">В следующем примере показана конфигурация, используемая <xref:System.Uri> классом для поддержки неэкранированных разделителей пути в кодировке% для схемы HTTP.</span><span class="sxs-lookup"><span data-stu-id="320dd-136">The following example shows a configuration used by the <xref:System.Uri> class to support not escaping percent-encoded path delimiters for the http scheme.</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <schemeSettings>  
      <add name="http" genericUriParserOptions="DontUnescapePathDotsAndSlashes"/>  
    </schemeSettings>  
  </uri>  
</configuration>  
```  
  
## <a name="element-information"></a><span data-ttu-id="320dd-137">Сведения об элементе</span><span class="sxs-lookup"><span data-stu-id="320dd-137">Element Information</span></span>  
  
|||
|-|-|  
|<span data-ttu-id="320dd-138">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="320dd-138">Namespace</span></span>|<span data-ttu-id="320dd-139">Система</span><span class="sxs-lookup"><span data-stu-id="320dd-139">System</span></span>|  
|<span data-ttu-id="320dd-140">Имя схемы</span><span class="sxs-lookup"><span data-stu-id="320dd-140">Schema Name</span></span>||  
|<span data-ttu-id="320dd-141">Файл проверки</span><span class="sxs-lookup"><span data-stu-id="320dd-141">Validation File</span></span>||  
|<span data-ttu-id="320dd-142">Может быть пустым</span><span class="sxs-lookup"><span data-stu-id="320dd-142">Can be Empty</span></span>||  
  
## <a name="see-also"></a><span data-ttu-id="320dd-143">См. также</span><span class="sxs-lookup"><span data-stu-id="320dd-143">See also</span></span>

- <xref:System.Configuration.SchemeSettingElement?displayProperty=nameWithType>
- <xref:System.Configuration.SchemeSettingElementCollection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection.SchemeSettings%2A?displayProperty=nameWithType>
- <xref:System.GenericUriParserOptions?displayProperty=nameWithType>
- <xref:System.Uri?displayProperty=nameWithType>
- [<span data-ttu-id="320dd-144">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="320dd-144">Network Settings Schema</span></span>](index.md)
