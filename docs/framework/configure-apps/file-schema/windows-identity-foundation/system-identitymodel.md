---
title: '&lt;system.identityModel&gt;'
ms.date: 03/30/2017
ms.assetid: 210ce7e9-d07b-400c-800f-5f525dcf95e8
author: BrucePerlerMS
ms.openlocfilehash: d0a29b572b71cd714f41eafe35096450e27ea33f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54491276"
---
# <a name="ltsystemidentitymodelgt"></a><span data-ttu-id="3e869-102">&lt;system.identityModel&gt;</span><span class="sxs-lookup"><span data-stu-id="3e869-102">&lt;system.identityModel&gt;</span></span>
<span data-ttu-id="3e869-103">Предоставляет конфигурацию для включения параметров Windows Identity Foundation (WIF) в приложениях.</span><span class="sxs-lookup"><span data-stu-id="3e869-103">Provides configuration for enabling Windows Identity Foundation (WIF) options in applications.</span></span>  
  
 <span data-ttu-id="3e869-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="3e869-104">\<system.identityModel></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3e869-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3e869-105">Syntax</span></span>  
  
```xml  
<system.identityModel>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3e869-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="3e869-106">Attributes and Elements</span></span>  
 <span data-ttu-id="3e869-107">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="3e869-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3e869-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="3e869-108">Attributes</span></span>  
 <span data-ttu-id="3e869-109">Нет</span><span class="sxs-lookup"><span data-stu-id="3e869-109">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="3e869-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="3e869-110">Child Elements</span></span>  
  
|<span data-ttu-id="3e869-111">Элемент</span><span class="sxs-lookup"><span data-stu-id="3e869-111">Element</span></span>|<span data-ttu-id="3e869-112">Описание</span><span class="sxs-lookup"><span data-stu-id="3e869-112">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3e869-113">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="3e869-113">\<identityConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|<span data-ttu-id="3e869-114">Указывает параметры уровня службы идентификации.</span><span class="sxs-lookup"><span data-stu-id="3e869-114">Specifies service-level identity settings.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="3e869-115">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="3e869-115">Parent Elements</span></span>  
  
|<span data-ttu-id="3e869-116">Элемент</span><span class="sxs-lookup"><span data-stu-id="3e869-116">Element</span></span>|<span data-ttu-id="3e869-117">Описание:</span><span class="sxs-lookup"><span data-stu-id="3e869-117">Description</span></span>|  
|-------------|-----------------|  
|`<configuration>`|<span data-ttu-id="3e869-118">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="3e869-118">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3e869-119">Примечания</span><span class="sxs-lookup"><span data-stu-id="3e869-119">Remarks</span></span>  
 <span data-ttu-id="3e869-120">Добавить `<system.identityModel>` раздел в файл конфигурации для настройки службы или приложения для использования Windows Identity Foundation (WIF).</span><span class="sxs-lookup"><span data-stu-id="3e869-120">Add a `<system.identityModel>` section to the configuration file to configure a service or application to use Windows Identity Foundation (WIF).</span></span> <span data-ttu-id="3e869-121">`<system.identityModel>` Элемент, представленный объектом <xref:System.IdentityModel.Configuration.SystemIdentityModelSection> класса.</span><span class="sxs-lookup"><span data-stu-id="3e869-121">The `<system.identityModel>` element is represented by the <xref:System.IdentityModel.Configuration.SystemIdentityModelSection> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3e869-122">Пример</span><span class="sxs-lookup"><span data-stu-id="3e869-122">Example</span></span>  
 <span data-ttu-id="3e869-123">В следующем примере показано, как добавить `<system.identityModel>` раздел в файл конфигурации.</span><span class="sxs-lookup"><span data-stu-id="3e869-123">The following example shows how to add a `<system.identityModel>` section to a configuration file.</span></span> <span data-ttu-id="3e869-124">Необходимо сначала добавить объявление раздела и пространства имен конфигурации в разделе `<configSections>` элемент.</span><span class="sxs-lookup"><span data-stu-id="3e869-124">You must first add the configuration section and namespace declaration under the `<configSections>` element.</span></span> <span data-ttu-id="3e869-125">Затем можно добавить `<system.IdentityModel>` элемент в файл конфигурации, чтобы указать одну или несколько конфигураций удостоверений.</span><span class="sxs-lookup"><span data-stu-id="3e869-125">Then you can add the `<system.IdentityModel>` element to your configuration file to specify one or more identity configurations.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="3e869-126">См. также</span><span class="sxs-lookup"><span data-stu-id="3e869-126">See also</span></span>
- <xref:System.IdentityModel.Configuration.SystemIdentityModelSection>
