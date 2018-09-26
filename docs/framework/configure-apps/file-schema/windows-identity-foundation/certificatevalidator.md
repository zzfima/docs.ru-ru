---
title: '&lt;certificateValidator&gt;'
ms.date: 03/30/2017
ms.assetid: 86161897-c20f-4ad8-9d7f-050c247251bf
author: BrucePerlerMS
ms.openlocfilehash: 65b8aa6fa4422579ce0d1c5e33d3418ea051612a
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/25/2018
ms.locfileid: "47077659"
---
# <a name="ltcertificatevalidatorgt"></a><span data-ttu-id="9dd82-102">&lt;certificateValidator&gt;</span><span class="sxs-lookup"><span data-stu-id="9dd82-102">&lt;certificateValidator&gt;</span></span>
<span data-ttu-id="9dd82-103">Задает пользовательский тип для проверки сертификата.</span><span class="sxs-lookup"><span data-stu-id="9dd82-103">Specifies a custom type for certificate validation.</span></span> <span data-ttu-id="9dd82-104">Этот тип используется только в том случае, если `certificateValidationMode` атрибут [ \<certificateValidation >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md) имеет значение «Custom».</span><span class="sxs-lookup"><span data-stu-id="9dd82-104">This type is used only if the `certificateValidationMode` attribute of the [\<certificateValidation>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md) element is set to "Custom".</span></span>  
  
 <span data-ttu-id="9dd82-105">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="9dd82-105">\<system.identityModel></span></span>  
<span data-ttu-id="9dd82-106">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="9dd82-106">\<identityConfiguration></span></span>  
<span data-ttu-id="9dd82-107">\<certificateValidation ></span><span class="sxs-lookup"><span data-stu-id="9dd82-107">\<certificateValidation></span></span>  
<span data-ttu-id="9dd82-108">\<certificateValidator ></span><span class="sxs-lookup"><span data-stu-id="9dd82-108">\<certificateValidator></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9dd82-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9dd82-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9dd82-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="9dd82-110">Attributes and Elements</span></span>  
 <span data-ttu-id="9dd82-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="9dd82-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9dd82-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="9dd82-112">Attributes</span></span>  
  
|<span data-ttu-id="9dd82-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="9dd82-113">Attribute</span></span>|<span data-ttu-id="9dd82-114">Описание</span><span class="sxs-lookup"><span data-stu-id="9dd82-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9dd82-115">type</span><span class="sxs-lookup"><span data-stu-id="9dd82-115">type</span></span>|<span data-ttu-id="9dd82-116">Задает пользовательский тип, производный от <xref:System.IdentityModel.Selectors.X509CertificateValidator> класса.</span><span class="sxs-lookup"><span data-stu-id="9dd82-116">Specifies a custom type that derives from the <xref:System.IdentityModel.Selectors.X509CertificateValidator> class.</span></span> <span data-ttu-id="9dd82-117">Задайте `certificateValidationMode` атрибут [ \<certificateValidation >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md) элемент на «Пользовательский», чтобы использовать этот тип.</span><span class="sxs-lookup"><span data-stu-id="9dd82-117">Set the `certificateValidationMode` attribute of the [\<certificateValidation>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md) element to "Custom" to use this type.</span></span> <span data-ttu-id="9dd82-118">Дополнительные сведения о способах указания `type` атрибут, см. в разделе [ссылок на пользовательские типы](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).</span><span class="sxs-lookup"><span data-stu-id="9dd82-118">For more information about how to specify the `type` attribute, see [Custom Type References](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).</span></span> <span data-ttu-id="9dd82-119">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="9dd82-119">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9dd82-120">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="9dd82-120">Child Elements</span></span>  
 <span data-ttu-id="9dd82-121">Нет</span><span class="sxs-lookup"><span data-stu-id="9dd82-121">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9dd82-122">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="9dd82-122">Parent Elements</span></span>  
  
|<span data-ttu-id="9dd82-123">Элемент</span><span class="sxs-lookup"><span data-stu-id="9dd82-123">Element</span></span>|<span data-ttu-id="9dd82-124">Описание</span><span class="sxs-lookup"><span data-stu-id="9dd82-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9dd82-125">\<certificateValidation ></span><span class="sxs-lookup"><span data-stu-id="9dd82-125">\<certificateValidation></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md)|<span data-ttu-id="9dd82-126">Управляет параметрами, используемых обработчиками токена для проверки сертификатов.</span><span class="sxs-lookup"><span data-stu-id="9dd82-126">Controls the settings that token handlers use to validate certificates.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="9dd82-127">Пример</span><span class="sxs-lookup"><span data-stu-id="9dd82-127">Example</span></span>  
  
```xml  
<certificateValidation certificateValidationMode="Custom"  
                       revocationMode="Online"  
                       trustedStoreLocation="LocalMachine">  
    <certificateValidator type="MyNamespace.CustomValidator, MyAssembly" />    
</certificateValidation>        
```
