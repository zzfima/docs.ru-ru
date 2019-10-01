---
title: Элемент <remove> для schemeSettings (параметры URI)
ms.date: 03/30/2017
ms.assetid: 4095ba51-de20-4f87-b562-018abe422c91
ms.openlocfilehash: 0dc8c6111157ba1f23d4a0449bee8f6626027e23
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2019
ms.locfileid: "71697852"
---
# <a name="remove-element-for-schemesettings-uri-settings"></a><span data-ttu-id="449df-102">Элемент > @no__t 0remove для schemeSettings (Параметры URI)</span><span class="sxs-lookup"><span data-stu-id="449df-102">\<remove> Element for schemeSettings (Uri Settings)</span></span>
<span data-ttu-id="449df-103">Удаляет параметр схемы для имени схемы.</span><span class="sxs-lookup"><span data-stu-id="449df-103">Removes a scheme setting for a scheme name.</span></span>  
  
[<span data-ttu-id="449df-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="449df-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="449df-105">&nbsp; @ no__t-1[ **\<uri >** ](uri-element-uri-settings.md)</span><span class="sxs-lookup"><span data-stu-id="449df-105">&nbsp;&nbsp;[**\<uri>**](uri-element-uri-settings.md)</span></span>  
<span data-ttu-id="449df-106">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3[ **\<schemeSettings >** ](schemesettings-element-uri-settings.md)</span><span class="sxs-lookup"><span data-stu-id="449df-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<schemeSettings>**](schemesettings-element-uri-settings.md)</span></span>  
<span data-ttu-id="449df-107">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5 **\<remove >**</span><span class="sxs-lookup"><span data-stu-id="449df-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="449df-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="449df-108">Syntax</span></span>  
  
```xml  
<remove
  name="http|https"
/>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="449df-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="449df-109">Attributes and Elements</span></span>  
 <span data-ttu-id="449df-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="449df-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="449df-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="449df-111">Attributes</span></span>  
  
|<span data-ttu-id="449df-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="449df-112">Attribute</span></span>|<span data-ttu-id="449df-113">Описание</span><span class="sxs-lookup"><span data-stu-id="449df-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="449df-114">имя</span><span class="sxs-lookup"><span data-stu-id="449df-114">name</span></span>|<span data-ttu-id="449df-115">Имя схемы, к которой применяется этот параметр.</span><span class="sxs-lookup"><span data-stu-id="449df-115">The scheme name for which this setting applies.</span></span> <span data-ttu-id="449df-116">Поддерживаются только значения Name = "http" и Name = "HTTPS".</span><span class="sxs-lookup"><span data-stu-id="449df-116">The only supported values are name="http" and name="https".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="449df-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="449df-117">Child Elements</span></span>  
 <span data-ttu-id="449df-118">Нет.</span><span class="sxs-lookup"><span data-stu-id="449df-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="449df-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="449df-119">Parent Elements</span></span>  
  
|<span data-ttu-id="449df-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="449df-120">Element</span></span>|<span data-ttu-id="449df-121">Описание</span><span class="sxs-lookup"><span data-stu-id="449df-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="449df-122">Элемент \<schemeSettings> (параметры URI)</span><span class="sxs-lookup"><span data-stu-id="449df-122">\<schemeSettings> Element (Uri Settings)</span></span>](schemesettings-element-uri-settings.md)|<span data-ttu-id="449df-123">Определяет, как <xref:System.Uri> анализируется для определенных схем.</span><span class="sxs-lookup"><span data-stu-id="449df-123">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="449df-124">Примечания</span><span class="sxs-lookup"><span data-stu-id="449df-124">Remarks</span></span>  
 <span data-ttu-id="449df-125">По умолчанию класс <xref:System.Uri?displayProperty=nameWithType> отменяет escape-символы в процентах, закодированные разделителями, перед выполнением сжатия пути.</span><span class="sxs-lookup"><span data-stu-id="449df-125">By default, the <xref:System.Uri?displayProperty=nameWithType> class un-escapes percent encoded path delimiters before executing path compression.</span></span> <span data-ttu-id="449df-126">Это было реализовано в качестве механизма безопасности для атак, подобных следующим:</span><span class="sxs-lookup"><span data-stu-id="449df-126">This was implemented as a security mechanism against attacks like the following:</span></span>  
  
 `http://www.contoso.com/..%2F..%2F/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="449df-127">Если этот URI передается в модули, которые неправильно обрабатывают закодированные символы процента, это может привести к выполнению следующей команды на сервере:</span><span class="sxs-lookup"><span data-stu-id="449df-127">If this URI gets passed down to modules not handling percent encoded characters correctly, it could result in the following command being executed by the server:</span></span>  
  
 `c:\Windows\System32\cmd.exe /c dir c:\`  
  
 <span data-ttu-id="449df-128">По этой причине класс <xref:System.Uri?displayProperty=nameWithType> сначала отменяет escape-разделители путей, а затем применяет сжатие пути.</span><span class="sxs-lookup"><span data-stu-id="449df-128">For this reason, <xref:System.Uri?displayProperty=nameWithType> class first un-escapes path delimiters and then applies path compression.</span></span> <span data-ttu-id="449df-129">Результат передачи вредоносного URL-адреса выше в конструктор класса <xref:System.Uri?displayProperty=nameWithType> приводит к следующему URI:</span><span class="sxs-lookup"><span data-stu-id="449df-129">The result of passing the malicious URL above to <xref:System.Uri?displayProperty=nameWithType> class constructor results in the following URI:</span></span>  
  
 `http://www.microsoft.com/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="449df-130">Это поведение по умолчанию можно изменить, чтобы не отменять escape-символы в процентах с помощью параметра конфигурации schemeSettings для определенной схемы.</span><span class="sxs-lookup"><span data-stu-id="449df-130">This default behavior can be modified to not un-escape percent encoded path delimiters using the schemeSettings configuration option for a specific scheme.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="449df-131">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="449df-131">Configuration Files</span></span>  
 <span data-ttu-id="449df-132">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="449df-132">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="449df-133">Пример</span><span class="sxs-lookup"><span data-stu-id="449df-133">Example</span></span>  
 <span data-ttu-id="449df-134">В следующем примере показана конфигурация, используемая классом <xref:System.Uri>, которая удаляет все параметры схемы для схемы HTTP.</span><span class="sxs-lookup"><span data-stu-id="449df-134">The following example shows a configuration used by the <xref:System.Uri> class that removes any scheme settings for the http scheme.</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <schemeSettings>  
      <remove name="http"/>  
    </schemeSettings>  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="449df-135">См. также</span><span class="sxs-lookup"><span data-stu-id="449df-135">See also</span></span>

- <xref:System.Configuration.SchemeSettingElement?displayProperty=nameWithType>
- <xref:System.Configuration.SchemeSettingElementCollection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection.SchemeSettings%2A?displayProperty=nameWithType>
- <xref:System.GenericUriParserOptions?displayProperty=nameWithType>
- <xref:System.Uri?displayProperty=nameWithType>
- [<span data-ttu-id="449df-136">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="449df-136">Network Settings Schema</span></span>](index.md)
