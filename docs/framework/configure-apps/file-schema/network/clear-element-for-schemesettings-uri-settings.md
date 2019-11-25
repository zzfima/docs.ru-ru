---
title: Элемент <clear> для schemeSettings (параметры URI)
ms.date: 03/30/2017
ms.assetid: 65098332-ce61-4542-ab8d-e7dc0257d31f
ms.openlocfilehash: 90035c1c9ccdb8ac888aec84e506ccde41748c9f
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/14/2019
ms.locfileid: "74087442"
---
# <a name="clear-element-for-schemesettings-uri-settings"></a><span data-ttu-id="a1312-102">\<очистить элемент > для schemeSettings (Параметры URI)</span><span class="sxs-lookup"><span data-stu-id="a1312-102">\<clear> Element for schemeSettings (Uri Settings)</span></span>
<span data-ttu-id="a1312-103">Удаляет все существующие параметры схемы.</span><span class="sxs-lookup"><span data-stu-id="a1312-103">Clears all existing scheme settings.</span></span>  

<span data-ttu-id="a1312-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="a1312-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="a1312-105">&nbsp;&nbsp;[ **\<> uri**](uri-element-uri-settings.md)</span><span class="sxs-lookup"><span data-stu-id="a1312-105">&nbsp;&nbsp;[**\<uri>**](uri-element-uri-settings.md)</span></span>\
<span data-ttu-id="a1312-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<schemeSettings >** ](schemesettings-element-uri-settings.md)</span><span class="sxs-lookup"><span data-stu-id="a1312-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<schemeSettings>**](schemesettings-element-uri-settings.md)</span></span>\
<span data-ttu-id="a1312-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<clear >**</span><span class="sxs-lookup"><span data-stu-id="a1312-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>

## <a name="syntax"></a><span data-ttu-id="a1312-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a1312-108">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a1312-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="a1312-109">Attributes and Elements</span></span>  
 <span data-ttu-id="a1312-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="a1312-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a1312-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="a1312-111">Attributes</span></span>  
 <span data-ttu-id="a1312-112">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="a1312-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="a1312-113">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="a1312-113">Child Elements</span></span>  
 <span data-ttu-id="a1312-114">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="a1312-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a1312-115">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="a1312-115">Parent Elements</span></span>  
  
|<span data-ttu-id="a1312-116">Элемент</span><span class="sxs-lookup"><span data-stu-id="a1312-116">Element</span></span>|<span data-ttu-id="a1312-117">Описание</span><span class="sxs-lookup"><span data-stu-id="a1312-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a1312-118">Элемент \<schemeSettings> (параметры URI)</span><span class="sxs-lookup"><span data-stu-id="a1312-118">\<schemeSettings> Element (Uri Settings)</span></span>](schemesettings-element-uri-settings.md)|<span data-ttu-id="a1312-119">Определяет, как <xref:System.Uri> анализируется для определенных схем.</span><span class="sxs-lookup"><span data-stu-id="a1312-119">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a1312-120">Заметки</span><span class="sxs-lookup"><span data-stu-id="a1312-120">Remarks</span></span>  
 <span data-ttu-id="a1312-121">По умолчанию класс <xref:System.Uri?displayProperty=nameWithType> отменяет escape-символы в процентах от разделителей закодированного пути перед выполнением сжатия пути.</span><span class="sxs-lookup"><span data-stu-id="a1312-121">By default, the <xref:System.Uri?displayProperty=nameWithType> class un-escapes percent encoded path delimiters before executing path compression.</span></span> <span data-ttu-id="a1312-122">Это было реализовано в качестве механизма безопасности для атак, подобных следующим:</span><span class="sxs-lookup"><span data-stu-id="a1312-122">This was implemented as a security mechanism against attacks like the following:</span></span>  
  
 `http://www.contoso.com/..%2F..%2F/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="a1312-123">Если этот URI передается в модули, которые неправильно обрабатывают закодированные символы процента, это может привести к выполнению следующей команды на сервере:</span><span class="sxs-lookup"><span data-stu-id="a1312-123">If this URI gets passed down to modules not handling percent encoded characters correctly, it could result in the following command being executed by the server:</span></span>  
  
 `c:\Windows\System32\cmd.exe /c dir c:\`  
  
 <span data-ttu-id="a1312-124">По этой причине <xref:System.Uri?displayProperty=nameWithType> класс сначала отменяет escape-разделители путей, а затем применяет сжатие пути.</span><span class="sxs-lookup"><span data-stu-id="a1312-124">For this reason, <xref:System.Uri?displayProperty=nameWithType> class first un-escapes path delimiters and then applies path compression.</span></span> <span data-ttu-id="a1312-125">Результат передачи вредоносного URL-адреса выше в <xref:System.Uri?displayProperty=nameWithType> конструктор класса приводит к следующему URI:</span><span class="sxs-lookup"><span data-stu-id="a1312-125">The result of passing the malicious URL above to <xref:System.Uri?displayProperty=nameWithType> class constructor results in the following URI:</span></span>  
  
 `http://www.microsoft.com/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="a1312-126">Это поведение по умолчанию можно изменить, чтобы не отменять escape-символы в процентах с помощью параметра конфигурации schemeSettings для определенной схемы.</span><span class="sxs-lookup"><span data-stu-id="a1312-126">This default behavior can be modified to not un-escape percent encoded path delimiters using the schemeSettings configuration option for a specific scheme.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="a1312-127">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="a1312-127">Configuration Files</span></span>  
 <span data-ttu-id="a1312-128">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="a1312-128">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a1312-129">Пример</span><span class="sxs-lookup"><span data-stu-id="a1312-129">Example</span></span>  
 <span data-ttu-id="a1312-130">В следующем примере показана конфигурация, используемая классом <xref:System.Uri>, который очищает все параметры схемы, а затем добавляет поддержку для разделителей пути, не экранированных в процентах, для схемы HTTP.</span><span class="sxs-lookup"><span data-stu-id="a1312-130">The following example shows a configuration used by the <xref:System.Uri> class that clears all scheme settings and then adds support for not escaping percent-encoded path delimiters for the http scheme.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="a1312-131">См. также</span><span class="sxs-lookup"><span data-stu-id="a1312-131">See also</span></span>

- <xref:System.Configuration.SchemeSettingElement?displayProperty=nameWithType>
- <xref:System.Configuration.SchemeSettingElementCollection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection.SchemeSettings%2A?displayProperty=nameWithType>
- <xref:System.GenericUriParserOptions?displayProperty=nameWithType>
- <xref:System.Uri?displayProperty=nameWithType>
- [<span data-ttu-id="a1312-132">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="a1312-132">Network Settings Schema</span></span>](index.md)
