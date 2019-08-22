---
title: Элемент <remove> для schemeSettings (параметры URI)
ms.date: 03/30/2017
ms.assetid: 4095ba51-de20-4f87-b562-018abe422c91
ms.openlocfilehash: 4a891eb8a2fd2d66b6435e2ae774ecd4a157c0f9
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/21/2019
ms.locfileid: "69659222"
---
# <a name="remove-element-for-schemesettings-uri-settings"></a><span data-ttu-id="d66a7-102">\<Удаление элемента > для schemeSettings (Параметры URI)</span><span class="sxs-lookup"><span data-stu-id="d66a7-102">\<remove> Element for schemeSettings (Uri Settings)</span></span>
<span data-ttu-id="d66a7-103">Удаляет параметр схемы для имени схемы.</span><span class="sxs-lookup"><span data-stu-id="d66a7-103">Removes a scheme setting for a scheme name.</span></span>  
  
 <span data-ttu-id="d66a7-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="d66a7-104">\<configuration></span></span>  
<span data-ttu-id="d66a7-105">\<> URI</span><span class="sxs-lookup"><span data-stu-id="d66a7-105">\<uri></span></span>  
<span data-ttu-id="d66a7-106">\<schemeSettings ></span><span class="sxs-lookup"><span data-stu-id="d66a7-106">\<schemeSettings></span></span>  
<span data-ttu-id="d66a7-107">\<Удалить ></span><span class="sxs-lookup"><span data-stu-id="d66a7-107">\<remove></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d66a7-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d66a7-108">Syntax</span></span>  
  
```xml  
<remove
  name="http|https"
/>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d66a7-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="d66a7-109">Attributes and Elements</span></span>  
 <span data-ttu-id="d66a7-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="d66a7-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d66a7-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="d66a7-111">Attributes</span></span>  
  
|<span data-ttu-id="d66a7-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="d66a7-112">Attribute</span></span>|<span data-ttu-id="d66a7-113">Описание</span><span class="sxs-lookup"><span data-stu-id="d66a7-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d66a7-114">имя</span><span class="sxs-lookup"><span data-stu-id="d66a7-114">name</span></span>|<span data-ttu-id="d66a7-115">Имя схемы, к которой применяется этот параметр.</span><span class="sxs-lookup"><span data-stu-id="d66a7-115">The scheme name for which this setting applies.</span></span> <span data-ttu-id="d66a7-116">Поддерживаются только значения Name = "http" и Name = "HTTPS".</span><span class="sxs-lookup"><span data-stu-id="d66a7-116">The only supported values are name="http" and name="https".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d66a7-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="d66a7-117">Child Elements</span></span>  
 <span data-ttu-id="d66a7-118">Нет.</span><span class="sxs-lookup"><span data-stu-id="d66a7-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d66a7-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="d66a7-119">Parent Elements</span></span>  
  
|<span data-ttu-id="d66a7-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="d66a7-120">Element</span></span>|<span data-ttu-id="d66a7-121">Описание</span><span class="sxs-lookup"><span data-stu-id="d66a7-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d66a7-122">Элемент \<schemeSettings> (параметры URI)</span><span class="sxs-lookup"><span data-stu-id="d66a7-122">\<schemeSettings> Element (Uri Settings)</span></span>](schemesettings-element-uri-settings.md)|<span data-ttu-id="d66a7-123">Определяет, как <xref:System.Uri> анализируется для определенных схем.</span><span class="sxs-lookup"><span data-stu-id="d66a7-123">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d66a7-124">Примечания</span><span class="sxs-lookup"><span data-stu-id="d66a7-124">Remarks</span></span>  
 <span data-ttu-id="d66a7-125">По умолчанию класс <xref:System.Uri?displayProperty=nameWithType> отменяет escape-символы в процентах, закодированные разделителями, перед выполнением сжатия пути.</span><span class="sxs-lookup"><span data-stu-id="d66a7-125">By default, the <xref:System.Uri?displayProperty=nameWithType> class un-escapes percent encoded path delimiters before executing path compression.</span></span> <span data-ttu-id="d66a7-126">Это было реализовано в качестве механизма безопасности для атак, подобных следующим:</span><span class="sxs-lookup"><span data-stu-id="d66a7-126">This was implemented as a security mechanism against attacks like the following:</span></span>  
  
 `http://www.contoso.com/..%2F..%2F/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="d66a7-127">Если этот URI передается в модули, которые неправильно обрабатывают закодированные символы процента, это может привести к выполнению следующей команды на сервере:</span><span class="sxs-lookup"><span data-stu-id="d66a7-127">If this URI gets passed down to modules not handling percent encoded characters correctly, it could result in the following command being executed by the server:</span></span>  
  
 `c:\Windows\System32\cmd.exe /c dir c:\`  
  
 <span data-ttu-id="d66a7-128">По этой причине <xref:System.Uri?displayProperty=nameWithType> класс сначала отменяет escape-разделители путей, а затем применяет сжатие пути.</span><span class="sxs-lookup"><span data-stu-id="d66a7-128">For this reason, <xref:System.Uri?displayProperty=nameWithType> class first un-escapes path delimiters and then applies path compression.</span></span> <span data-ttu-id="d66a7-129">Результат передачи вредоносного URL-адреса выше в <xref:System.Uri?displayProperty=nameWithType> конструктор класса приводит к следующему URI:</span><span class="sxs-lookup"><span data-stu-id="d66a7-129">The result of passing the malicious URL above to <xref:System.Uri?displayProperty=nameWithType> class constructor results in the following URI:</span></span>  
  
 `http://www.microsoft.com/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="d66a7-130">Это поведение по умолчанию можно изменить, чтобы не отменять escape-символы в процентах с помощью параметра конфигурации schemeSettings для определенной схемы.</span><span class="sxs-lookup"><span data-stu-id="d66a7-130">This default behavior can be modified to not un-escape percent encoded path delimiters using the schemeSettings configuration option for a specific scheme.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="d66a7-131">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="d66a7-131">Configuration Files</span></span>  
 <span data-ttu-id="d66a7-132">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="d66a7-132">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d66a7-133">Пример</span><span class="sxs-lookup"><span data-stu-id="d66a7-133">Example</span></span>  
 <span data-ttu-id="d66a7-134">В следующем примере показана конфигурация, используемая <xref:System.Uri> классом, который удаляет все параметры схемы для схемы HTTP.</span><span class="sxs-lookup"><span data-stu-id="d66a7-134">The following example shows a configuration used by the <xref:System.Uri> class that removes any scheme settings for the http scheme.</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <schemeSettings>  
      <remove name="http"/>  
    </schemeSettings>  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d66a7-135">См. также</span><span class="sxs-lookup"><span data-stu-id="d66a7-135">See also</span></span>

- <xref:System.Configuration.SchemeSettingElement?displayProperty=nameWithType>
- <xref:System.Configuration.SchemeSettingElementCollection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection.SchemeSettings%2A?displayProperty=nameWithType>
- <xref:System.GenericUriParserOptions?displayProperty=nameWithType>
- <xref:System.Uri?displayProperty=nameWithType>
- [<span data-ttu-id="d66a7-136">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="d66a7-136">Network Settings Schema</span></span>](index.md)
