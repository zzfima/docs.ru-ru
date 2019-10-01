---
title: Элемент <clear> для schemeSettings (параметры URI)
ms.date: 03/30/2017
ms.assetid: 65098332-ce61-4542-ab8d-e7dc0257d31f
ms.openlocfilehash: e954fef455d0279a945c33f2014913fea9d63064
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2019
ms.locfileid: "71699444"
---
# <a name="clear-element-for-schemesettings-uri-settings"></a><span data-ttu-id="3fba7-102">Элемент > @no__t 0clear для schemeSettings (Параметры URI)</span><span class="sxs-lookup"><span data-stu-id="3fba7-102">\<clear> Element for schemeSettings (Uri Settings)</span></span>
<span data-ttu-id="3fba7-103">Удаляет все существующие параметры схемы.</span><span class="sxs-lookup"><span data-stu-id="3fba7-103">Clears all existing scheme settings.</span></span>  
  
[<span data-ttu-id="3fba7-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="3fba7-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="3fba7-105">&nbsp; @ no__t-1[ **\<uri >** ](uri-element-uri-settings.md)</span><span class="sxs-lookup"><span data-stu-id="3fba7-105">&nbsp;&nbsp;[**\<uri>**](uri-element-uri-settings.md)</span></span>  
<span data-ttu-id="3fba7-106">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3[ **\<schemeSettings >** ](schemesettings-element-uri-settings.md)</span><span class="sxs-lookup"><span data-stu-id="3fba7-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<schemeSettings>**](schemesettings-element-uri-settings.md)</span></span>  
<span data-ttu-id="3fba7-107">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5 **\<clear >**</span><span class="sxs-lookup"><span data-stu-id="3fba7-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3fba7-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3fba7-108">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3fba7-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="3fba7-109">Attributes and Elements</span></span>  
 <span data-ttu-id="3fba7-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="3fba7-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3fba7-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="3fba7-111">Attributes</span></span>  
 <span data-ttu-id="3fba7-112">Нет.</span><span class="sxs-lookup"><span data-stu-id="3fba7-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="3fba7-113">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="3fba7-113">Child Elements</span></span>  
 <span data-ttu-id="3fba7-114">Нет.</span><span class="sxs-lookup"><span data-stu-id="3fba7-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3fba7-115">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="3fba7-115">Parent Elements</span></span>  
  
|<span data-ttu-id="3fba7-116">Элемент</span><span class="sxs-lookup"><span data-stu-id="3fba7-116">Element</span></span>|<span data-ttu-id="3fba7-117">Описание</span><span class="sxs-lookup"><span data-stu-id="3fba7-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3fba7-118">Элемент \<schemeSettings> (параметры URI)</span><span class="sxs-lookup"><span data-stu-id="3fba7-118">\<schemeSettings> Element (Uri Settings)</span></span>](schemesettings-element-uri-settings.md)|<span data-ttu-id="3fba7-119">Определяет, как <xref:System.Uri> анализируется для определенных схем.</span><span class="sxs-lookup"><span data-stu-id="3fba7-119">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3fba7-120">Примечания</span><span class="sxs-lookup"><span data-stu-id="3fba7-120">Remarks</span></span>  
 <span data-ttu-id="3fba7-121">По умолчанию класс <xref:System.Uri?displayProperty=nameWithType> отменяет escape-символы в процентах, закодированные разделителями, перед выполнением сжатия пути.</span><span class="sxs-lookup"><span data-stu-id="3fba7-121">By default, the <xref:System.Uri?displayProperty=nameWithType> class un-escapes percent encoded path delimiters before executing path compression.</span></span> <span data-ttu-id="3fba7-122">Это было реализовано в качестве механизма безопасности для атак, подобных следующим:</span><span class="sxs-lookup"><span data-stu-id="3fba7-122">This was implemented as a security mechanism against attacks like the following:</span></span>  
  
 `http://www.contoso.com/..%2F..%2F/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="3fba7-123">Если этот URI передается в модули, которые неправильно обрабатывают закодированные символы процента, это может привести к выполнению следующей команды на сервере:</span><span class="sxs-lookup"><span data-stu-id="3fba7-123">If this URI gets passed down to modules not handling percent encoded characters correctly, it could result in the following command being executed by the server:</span></span>  
  
 `c:\Windows\System32\cmd.exe /c dir c:\`  
  
 <span data-ttu-id="3fba7-124">По этой причине класс <xref:System.Uri?displayProperty=nameWithType> сначала отменяет escape-разделители путей, а затем применяет сжатие пути.</span><span class="sxs-lookup"><span data-stu-id="3fba7-124">For this reason, <xref:System.Uri?displayProperty=nameWithType> class first un-escapes path delimiters and then applies path compression.</span></span> <span data-ttu-id="3fba7-125">Результат передачи вредоносного URL-адреса выше в конструктор класса <xref:System.Uri?displayProperty=nameWithType> приводит к следующему URI:</span><span class="sxs-lookup"><span data-stu-id="3fba7-125">The result of passing the malicious URL above to <xref:System.Uri?displayProperty=nameWithType> class constructor results in the following URI:</span></span>  
  
 `http://www.microsoft.com/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="3fba7-126">Это поведение по умолчанию можно изменить, чтобы не отменять escape-символы в процентах с помощью параметра конфигурации schemeSettings для определенной схемы.</span><span class="sxs-lookup"><span data-stu-id="3fba7-126">This default behavior can be modified to not un-escape percent encoded path delimiters using the schemeSettings configuration option for a specific scheme.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="3fba7-127">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="3fba7-127">Configuration Files</span></span>  
 <span data-ttu-id="3fba7-128">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="3fba7-128">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3fba7-129">Пример</span><span class="sxs-lookup"><span data-stu-id="3fba7-129">Example</span></span>  
 <span data-ttu-id="3fba7-130">В следующем примере показана конфигурация, используемая классом <xref:System.Uri>, которая очищает все параметры схемы, а затем добавляет поддержку для разделителей пути, не экранированных в процентах, для схемы HTTP.</span><span class="sxs-lookup"><span data-stu-id="3fba7-130">The following example shows a configuration used by the <xref:System.Uri> class that clears all scheme settings and then adds support for not escaping percent-encoded path delimiters for the http scheme.</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <schemeSettings>  
      <clear/>  
      <add name="http" genericUriParserOptions="DontUnescapePathDotsAndSlashes"/>  
    </schemeSettings>  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="3fba7-131">См. также</span><span class="sxs-lookup"><span data-stu-id="3fba7-131">See also</span></span>

- <xref:System.Configuration.SchemeSettingElement?displayProperty=nameWithType>
- <xref:System.Configuration.SchemeSettingElementCollection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection.SchemeSettings%2A?displayProperty=nameWithType>
- <xref:System.GenericUriParserOptions?displayProperty=nameWithType>
- <xref:System.Uri?displayProperty=nameWithType>
- [<span data-ttu-id="3fba7-132">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="3fba7-132">Network Settings Schema</span></span>](index.md)
