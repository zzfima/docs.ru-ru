---
title: '&lt;certificateValidator&gt;'
ms.date: 03/30/2017
ms.assetid: 86161897-c20f-4ad8-9d7f-050c247251bf
author: BrucePerlerMS
ms.openlocfilehash: 65b8aa6fa4422579ce0d1c5e33d3418ea051612a
ms.sourcegitcommit: 69229651598b427c550223d3c58aba82e47b3f82
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/04/2018
ms.locfileid: "48776887"
---
# <a name="ltcertificatevalidatorgt"></a><span data-ttu-id="5738b-102">&lt;certificateValidator&gt;</span><span class="sxs-lookup"><span data-stu-id="5738b-102">&lt;certificateValidator&gt;</span></span>
<span data-ttu-id="5738b-103">Задает пользовательский тип для проверки сертификата.</span><span class="sxs-lookup"><span data-stu-id="5738b-103">Specifies a custom type for certificate validation.</span></span> <span data-ttu-id="5738b-104">Этот тип используется только в том случае, если `certificateValidationMode` атрибут [ \<certificateValidation >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md) имеет значение «Custom».</span><span class="sxs-lookup"><span data-stu-id="5738b-104">This type is used only if the `certificateValidationMode` attribute of the [\<certificateValidation>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md) element is set to "Custom".</span></span>  
  
 <span data-ttu-id="5738b-105">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="5738b-105">\<system.identityModel></span></span>  
<span data-ttu-id="5738b-106">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="5738b-106">\<identityConfiguration></span></span>  
<span data-ttu-id="5738b-107">\<certificateValidation ></span><span class="sxs-lookup"><span data-stu-id="5738b-107">\<certificateValidation></span></span>  
<span data-ttu-id="5738b-108">\<certificateValidator ></span><span class="sxs-lookup"><span data-stu-id="5738b-108">\<certificateValidator></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5738b-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5738b-109">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <certificateValidation>  
      <certificateValidator type=xs:string>  
      </certificateValidator>  
    </certificateValidation>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5738b-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="5738b-110">Attributes and Elements</span></span>  
 <span data-ttu-id="5738b-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="5738b-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5738b-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="5738b-112">Attributes</span></span>  
  
|<span data-ttu-id="5738b-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="5738b-113">Attribute</span></span>|<span data-ttu-id="5738b-114">Описание</span><span class="sxs-lookup"><span data-stu-id="5738b-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5738b-115">type</span><span class="sxs-lookup"><span data-stu-id="5738b-115">type</span></span>|<span data-ttu-id="5738b-116">Задает пользовательский тип, производный от <xref:System.IdentityModel.Selectors.X509CertificateValidator> класса.</span><span class="sxs-lookup"><span data-stu-id="5738b-116">Specifies a custom type that derives from the <xref:System.IdentityModel.Selectors.X509CertificateValidator> class.</span></span> <span data-ttu-id="5738b-117">Задайте `certificateValidationMode` атрибут [ \<certificateValidation >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md) элемент на «Пользовательский», чтобы использовать этот тип.</span><span class="sxs-lookup"><span data-stu-id="5738b-117">Set the `certificateValidationMode` attribute of the [\<certificateValidation>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md) element to "Custom" to use this type.</span></span> <span data-ttu-id="5738b-118">Дополнительные сведения о способах указания `type` атрибут, см. в разделе [ссылок на пользовательские типы](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).</span><span class="sxs-lookup"><span data-stu-id="5738b-118">For more information about how to specify the `type` attribute, see [Custom Type References](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).</span></span> <span data-ttu-id="5738b-119">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="5738b-119">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5738b-120">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="5738b-120">Child Elements</span></span>  
 <span data-ttu-id="5738b-121">Нет</span><span class="sxs-lookup"><span data-stu-id="5738b-121">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5738b-122">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="5738b-122">Parent Elements</span></span>  
  
|<span data-ttu-id="5738b-123">Элемент</span><span class="sxs-lookup"><span data-stu-id="5738b-123">Element</span></span>|<span data-ttu-id="5738b-124">Описание</span><span class="sxs-lookup"><span data-stu-id="5738b-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5738b-125">\<certificateValidation ></span><span class="sxs-lookup"><span data-stu-id="5738b-125">\<certificateValidation></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md)|<span data-ttu-id="5738b-126">Управляет параметрами, используемых обработчиками токена для проверки сертификатов.</span><span class="sxs-lookup"><span data-stu-id="5738b-126">Controls the settings that token handlers use to validate certificates.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="5738b-127">Пример</span><span class="sxs-lookup"><span data-stu-id="5738b-127">Example</span></span>  
  
```xml  
<certificateValidation certificateValidationMode="Custom"  
                       revocationMode="Online"  
                       trustedStoreLocation="LocalMachine">  
    <certificateValidator type="MyNamespace.CustomValidator, MyAssembly" />    
</certificateValidation>        
```
