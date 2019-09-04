---
title: <system.identityModel>
ms.date: 03/30/2017
ms.assetid: 210ce7e9-d07b-400c-800f-5f525dcf95e8
author: BrucePerlerMS
ms.openlocfilehash: a54f5ce86aee1a5e831c0b10aa1471d4a82f40a5
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251794"
---
# <a name="systemidentitymodel"></a><span data-ttu-id="0bda7-102">\<> System. identityModel</span><span class="sxs-lookup"><span data-stu-id="0bda7-102">\<system.identityModel></span></span>
<span data-ttu-id="0bda7-103">Предоставляет конфигурацию для включения параметров Windows Identity Foundation (WIF) в приложениях.</span><span class="sxs-lookup"><span data-stu-id="0bda7-103">Provides configuration for enabling Windows Identity Foundation (WIF) options in applications.</span></span>  
  
<span data-ttu-id="0bda7-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="0bda7-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="0bda7-105">&nbsp;&nbsp; **\<> System. identityModel**</span><span class="sxs-lookup"><span data-stu-id="0bda7-105">&nbsp;&nbsp;**\<system.identityModel>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0bda7-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0bda7-106">Syntax</span></span>  
  
```xml  
<system.identityModel>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0bda7-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="0bda7-107">Attributes and Elements</span></span>  
 <span data-ttu-id="0bda7-108">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="0bda7-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0bda7-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="0bda7-109">Attributes</span></span>  
 <span data-ttu-id="0bda7-110">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="0bda7-110">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="0bda7-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="0bda7-111">Child Elements</span></span>  
  
|<span data-ttu-id="0bda7-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="0bda7-112">Element</span></span>|<span data-ttu-id="0bda7-113">Описание</span><span class="sxs-lookup"><span data-stu-id="0bda7-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0bda7-114">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="0bda7-114">\<identityConfiguration></span></span>](identityconfiguration.md)|<span data-ttu-id="0bda7-115">Задает параметры удостоверений уровня службы.</span><span class="sxs-lookup"><span data-stu-id="0bda7-115">Specifies service-level identity settings.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0bda7-116">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="0bda7-116">Parent Elements</span></span>  
  
|<span data-ttu-id="0bda7-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="0bda7-117">Element</span></span>|<span data-ttu-id="0bda7-118">Описание</span><span class="sxs-lookup"><span data-stu-id="0bda7-118">Description</span></span>|  
|-------------|-----------------|  
|`<configuration>`|<span data-ttu-id="0bda7-119">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="0bda7-119">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0bda7-120">Примечания</span><span class="sxs-lookup"><span data-stu-id="0bda7-120">Remarks</span></span>  
 <span data-ttu-id="0bda7-121">`<system.identityModel>` Добавьте раздел в файл конфигурации, чтобы настроить службу или приложение для использования Windows Identity Foundation (WIF).</span><span class="sxs-lookup"><span data-stu-id="0bda7-121">Add a `<system.identityModel>` section to the configuration file to configure a service or application to use Windows Identity Foundation (WIF).</span></span> <span data-ttu-id="0bda7-122">`<system.identityModel>` Элемент представлен<xref:System.IdentityModel.Configuration.SystemIdentityModelSection> классом.</span><span class="sxs-lookup"><span data-stu-id="0bda7-122">The `<system.identityModel>` element is represented by the <xref:System.IdentityModel.Configuration.SystemIdentityModelSection> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0bda7-123">Пример</span><span class="sxs-lookup"><span data-stu-id="0bda7-123">Example</span></span>  
 <span data-ttu-id="0bda7-124">В следующем примере показано, как добавить `<system.identityModel>` раздел в файл конфигурации.</span><span class="sxs-lookup"><span data-stu-id="0bda7-124">The following example shows how to add a `<system.identityModel>` section to a configuration file.</span></span> <span data-ttu-id="0bda7-125">Сначала необходимо добавить раздел конфигурации и объявление пространства имен в `<configSections>` элемент.</span><span class="sxs-lookup"><span data-stu-id="0bda7-125">You must first add the configuration section and namespace declaration under the `<configSections>` element.</span></span> <span data-ttu-id="0bda7-126">Затем можно добавить `<system.IdentityModel>` элемент в файл конфигурации, чтобы указать одну или несколько конфигураций удостоверений.</span><span class="sxs-lookup"><span data-stu-id="0bda7-126">Then you can add the `<system.IdentityModel>` element to your configuration file to specify one or more identity configurations.</span></span>  
  
```xml  
<configuration>  
  <configSections>  
    <!--WIF 4.5 sections -->  
    <section name="system.identityModel" type="System.IdentityModel.Configuration.SystemIdentityModelSection, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089"/>  
    <section name="system.identityModel.services" type="System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089"/>  
  </configSections>  
  
  ...  
  
  <system.identityModel>  
    <identityConfiguration>  
      <audienceUris>  
        <add value="http://localhost/WebApplication1/" />  
      </audienceUris>  
      <issuerNameRegistry type="System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089">  
        <trustedIssuers>  
          <add thumbprint="313D3B … 9106A9EC" name="SelfSTS" />  
        </trustedIssuers>  
      </issuerNameRegistry>  
      <certificateValidation certificateValidationMode="None"/>  
    </identityConfiguration>  
  </system.identityModel>  
  
  ...  
  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="0bda7-127">См. также</span><span class="sxs-lookup"><span data-stu-id="0bda7-127">See also</span></span>

- <xref:System.IdentityModel.Configuration.SystemIdentityModelSection>
