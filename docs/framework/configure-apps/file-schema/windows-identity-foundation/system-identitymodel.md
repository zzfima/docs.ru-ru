---
title: '&lt;system.identityModel&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 210ce7e9-d07b-400c-800f-5f525dcf95e8
caps.latest.revision: "5"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 356dd1531f093282a1a8463b7d697400f8b45862
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="ltsystemidentitymodelgt"></a><span data-ttu-id="826d3-102">&lt;system.identityModel&gt;</span><span class="sxs-lookup"><span data-stu-id="826d3-102">&lt;system.identityModel&gt;</span></span>
<span data-ttu-id="826d3-103">Обеспечивает настройку для включения параметров Windows Identity Foundation (WIF) в приложениях.</span><span class="sxs-lookup"><span data-stu-id="826d3-103">Provides configuration for enabling Windows Identity Foundation (WIF) options in applications.</span></span>  
  
 <span data-ttu-id="826d3-104">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="826d3-104">\<system.identityModel></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="826d3-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="826d3-105">Syntax</span></span>  
  
```xml  
<system.identityModel>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="826d3-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="826d3-106">Attributes and Elements</span></span>  
 <span data-ttu-id="826d3-107">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="826d3-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="826d3-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="826d3-108">Attributes</span></span>  
 <span data-ttu-id="826d3-109">Нет</span><span class="sxs-lookup"><span data-stu-id="826d3-109">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="826d3-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="826d3-110">Child Elements</span></span>  
  
|<span data-ttu-id="826d3-111">Элемент</span><span class="sxs-lookup"><span data-stu-id="826d3-111">Element</span></span>|<span data-ttu-id="826d3-112">Описание</span><span class="sxs-lookup"><span data-stu-id="826d3-112">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="826d3-113">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="826d3-113">\<identityConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|<span data-ttu-id="826d3-114">Указывает параметры уровня службы удостоверений.</span><span class="sxs-lookup"><span data-stu-id="826d3-114">Specifies service-level identity settings.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="826d3-115">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="826d3-115">Parent Elements</span></span>  
  
|<span data-ttu-id="826d3-116">Элемент</span><span class="sxs-lookup"><span data-stu-id="826d3-116">Element</span></span>|<span data-ttu-id="826d3-117">Описание</span><span class="sxs-lookup"><span data-stu-id="826d3-117">Description</span></span>|  
|-------------|-----------------|  
|`<configuration>`|<span data-ttu-id="826d3-118">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="826d3-118">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="826d3-119">Примечания</span><span class="sxs-lookup"><span data-stu-id="826d3-119">Remarks</span></span>  
 <span data-ttu-id="826d3-120">Добавить `<system.identityModel>` раздел в файл конфигурации для настройки службы или приложения для использования Windows Identity Foundation (WIF).</span><span class="sxs-lookup"><span data-stu-id="826d3-120">Add a `<system.identityModel>` section to the configuration file to configure a service or application to use Windows Identity Foundation (WIF).</span></span> <span data-ttu-id="826d3-121">`<system.identityModel>` Представлен <xref:System.IdentityModel.Configuration.SystemIdentityModelSection> класса.</span><span class="sxs-lookup"><span data-stu-id="826d3-121">The `<system.identityModel>` element is represented by the <xref:System.IdentityModel.Configuration.SystemIdentityModelSection> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="826d3-122">Пример</span><span class="sxs-lookup"><span data-stu-id="826d3-122">Example</span></span>  
 <span data-ttu-id="826d3-123">Следующий пример демонстрирует добавление `<system.identityModel>` раздела в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="826d3-123">The following example shows how to add a `<system.identityModel>` section to a configuration file.</span></span> <span data-ttu-id="826d3-124">Сначала необходимо добавить объявление раздела и пространство имен конфигурации в разделе `<configSections>` элемента.</span><span class="sxs-lookup"><span data-stu-id="826d3-124">You must first add the configuration section and namespace declaration under the `<configSections>` element.</span></span> <span data-ttu-id="826d3-125">Затем можно добавить `<system.IdentityModel>` элемент в файл конфигурации, чтобы указать одну или несколько конфигураций удостоверения.</span><span class="sxs-lookup"><span data-stu-id="826d3-125">Then you can add the `<system.IdentityModel>` element to your configuration file to specify one or more identity configurations.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="826d3-126">См. также</span><span class="sxs-lookup"><span data-stu-id="826d3-126">See Also</span></span>  
 <xref:System.IdentityModel.Configuration.SystemIdentityModelSection>
