---
title: <system.identityModel>
ms.date: 03/30/2017
ms.assetid: 210ce7e9-d07b-400c-800f-5f525dcf95e8
author: BrucePerlerMS
ms.openlocfilehash: 286ae88946692e6894ca3c7ee9e1348415c84ade
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69943599"
---
# <a name="systemidentitymodel"></a><span data-ttu-id="f737e-102">\<> System. identityModel</span><span class="sxs-lookup"><span data-stu-id="f737e-102">\<system.identityModel></span></span>
<span data-ttu-id="f737e-103">Предоставляет конфигурацию для включения параметров Windows Identity Foundation (WIF) в приложениях.</span><span class="sxs-lookup"><span data-stu-id="f737e-103">Provides configuration for enabling Windows Identity Foundation (WIF) options in applications.</span></span>  
  
 <span data-ttu-id="f737e-104">\<> System. identityModel</span><span class="sxs-lookup"><span data-stu-id="f737e-104">\<system.identityModel></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f737e-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f737e-105">Syntax</span></span>  
  
```xml  
<system.identityModel>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f737e-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="f737e-106">Attributes and Elements</span></span>  
 <span data-ttu-id="f737e-107">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="f737e-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f737e-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="f737e-108">Attributes</span></span>  
 <span data-ttu-id="f737e-109">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="f737e-109">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="f737e-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="f737e-110">Child Elements</span></span>  
  
|<span data-ttu-id="f737e-111">Элемент</span><span class="sxs-lookup"><span data-stu-id="f737e-111">Element</span></span>|<span data-ttu-id="f737e-112">Описание</span><span class="sxs-lookup"><span data-stu-id="f737e-112">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f737e-113">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="f737e-113">\<identityConfiguration></span></span>](identityconfiguration.md)|<span data-ttu-id="f737e-114">Задает параметры удостоверений уровня службы.</span><span class="sxs-lookup"><span data-stu-id="f737e-114">Specifies service-level identity settings.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f737e-115">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="f737e-115">Parent Elements</span></span>  
  
|<span data-ttu-id="f737e-116">Элемент</span><span class="sxs-lookup"><span data-stu-id="f737e-116">Element</span></span>|<span data-ttu-id="f737e-117">Описание</span><span class="sxs-lookup"><span data-stu-id="f737e-117">Description</span></span>|  
|-------------|-----------------|  
|`<configuration>`|<span data-ttu-id="f737e-118">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f737e-118">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f737e-119">Примечания</span><span class="sxs-lookup"><span data-stu-id="f737e-119">Remarks</span></span>  
 <span data-ttu-id="f737e-120">`<system.identityModel>` Добавьте раздел в файл конфигурации, чтобы настроить службу или приложение для использования Windows Identity Foundation (WIF).</span><span class="sxs-lookup"><span data-stu-id="f737e-120">Add a `<system.identityModel>` section to the configuration file to configure a service or application to use Windows Identity Foundation (WIF).</span></span> <span data-ttu-id="f737e-121">`<system.identityModel>` Элемент представлен<xref:System.IdentityModel.Configuration.SystemIdentityModelSection> классом.</span><span class="sxs-lookup"><span data-stu-id="f737e-121">The `<system.identityModel>` element is represented by the <xref:System.IdentityModel.Configuration.SystemIdentityModelSection> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f737e-122">Пример</span><span class="sxs-lookup"><span data-stu-id="f737e-122">Example</span></span>  
 <span data-ttu-id="f737e-123">В следующем примере показано, как добавить `<system.identityModel>` раздел в файл конфигурации.</span><span class="sxs-lookup"><span data-stu-id="f737e-123">The following example shows how to add a `<system.identityModel>` section to a configuration file.</span></span> <span data-ttu-id="f737e-124">Сначала необходимо добавить раздел конфигурации и объявление пространства имен в `<configSections>` элемент.</span><span class="sxs-lookup"><span data-stu-id="f737e-124">You must first add the configuration section and namespace declaration under the `<configSections>` element.</span></span> <span data-ttu-id="f737e-125">Затем можно добавить `<system.IdentityModel>` элемент в файл конфигурации, чтобы указать одну или несколько конфигураций удостоверений.</span><span class="sxs-lookup"><span data-stu-id="f737e-125">Then you can add the `<system.IdentityModel>` element to your configuration file to specify one or more identity configurations.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="f737e-126">См. также</span><span class="sxs-lookup"><span data-stu-id="f737e-126">See also</span></span>

- <xref:System.IdentityModel.Configuration.SystemIdentityModelSection>
