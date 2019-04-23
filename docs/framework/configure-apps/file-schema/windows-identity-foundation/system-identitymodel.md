---
title: <system.identityModel>
ms.date: 03/30/2017
ms.assetid: 210ce7e9-d07b-400c-800f-5f525dcf95e8
author: BrucePerlerMS
ms.openlocfilehash: 2f0040fb7084b9d53adbd1a114f1cfc62d58e5a1
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59110010"
---
# <a name="systemidentitymodel"></a><span data-ttu-id="2cf8b-102">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="2cf8b-102">\<system.identityModel></span></span>
<span data-ttu-id="2cf8b-103">Предоставляет конфигурацию для включения параметров Windows Identity Foundation (WIF) в приложениях.</span><span class="sxs-lookup"><span data-stu-id="2cf8b-103">Provides configuration for enabling Windows Identity Foundation (WIF) options in applications.</span></span>  
  
 <span data-ttu-id="2cf8b-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="2cf8b-104">\<system.identityModel></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2cf8b-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2cf8b-105">Syntax</span></span>  
  
```xml  
<system.identityModel>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2cf8b-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="2cf8b-106">Attributes and Elements</span></span>  
 <span data-ttu-id="2cf8b-107">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="2cf8b-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2cf8b-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="2cf8b-108">Attributes</span></span>  
 <span data-ttu-id="2cf8b-109">Нет</span><span class="sxs-lookup"><span data-stu-id="2cf8b-109">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="2cf8b-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="2cf8b-110">Child Elements</span></span>  
  
|<span data-ttu-id="2cf8b-111">Элемент</span><span class="sxs-lookup"><span data-stu-id="2cf8b-111">Element</span></span>|<span data-ttu-id="2cf8b-112">Описание</span><span class="sxs-lookup"><span data-stu-id="2cf8b-112">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2cf8b-113">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="2cf8b-113">\<identityConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|<span data-ttu-id="2cf8b-114">Указывает параметры уровня службы идентификации.</span><span class="sxs-lookup"><span data-stu-id="2cf8b-114">Specifies service-level identity settings.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2cf8b-115">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="2cf8b-115">Parent Elements</span></span>  
  
|<span data-ttu-id="2cf8b-116">Элемент</span><span class="sxs-lookup"><span data-stu-id="2cf8b-116">Element</span></span>|<span data-ttu-id="2cf8b-117">Описание</span><span class="sxs-lookup"><span data-stu-id="2cf8b-117">Description</span></span>|  
|-------------|-----------------|  
|`<configuration>`|<span data-ttu-id="2cf8b-118">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="2cf8b-118">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2cf8b-119">Примечания</span><span class="sxs-lookup"><span data-stu-id="2cf8b-119">Remarks</span></span>  
 <span data-ttu-id="2cf8b-120">Добавить `<system.identityModel>` раздел в файл конфигурации для настройки службы или приложения для использования Windows Identity Foundation (WIF).</span><span class="sxs-lookup"><span data-stu-id="2cf8b-120">Add a `<system.identityModel>` section to the configuration file to configure a service or application to use Windows Identity Foundation (WIF).</span></span> <span data-ttu-id="2cf8b-121">`<system.identityModel>` Элемент, представленный объектом <xref:System.IdentityModel.Configuration.SystemIdentityModelSection> класса.</span><span class="sxs-lookup"><span data-stu-id="2cf8b-121">The `<system.identityModel>` element is represented by the <xref:System.IdentityModel.Configuration.SystemIdentityModelSection> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2cf8b-122">Пример</span><span class="sxs-lookup"><span data-stu-id="2cf8b-122">Example</span></span>  
 <span data-ttu-id="2cf8b-123">В следующем примере показано, как добавить `<system.identityModel>` раздел в файл конфигурации.</span><span class="sxs-lookup"><span data-stu-id="2cf8b-123">The following example shows how to add a `<system.identityModel>` section to a configuration file.</span></span> <span data-ttu-id="2cf8b-124">Необходимо сначала добавить объявление раздела и пространства имен конфигурации в разделе `<configSections>` элемент.</span><span class="sxs-lookup"><span data-stu-id="2cf8b-124">You must first add the configuration section and namespace declaration under the `<configSections>` element.</span></span> <span data-ttu-id="2cf8b-125">Затем можно добавить `<system.IdentityModel>` элемент в файл конфигурации, чтобы указать одну или несколько конфигураций удостоверений.</span><span class="sxs-lookup"><span data-stu-id="2cf8b-125">Then you can add the `<system.IdentityModel>` element to your configuration file to specify one or more identity configurations.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="2cf8b-126">См. также</span><span class="sxs-lookup"><span data-stu-id="2cf8b-126">See also</span></span>

- <xref:System.IdentityModel.Configuration.SystemIdentityModelSection>
