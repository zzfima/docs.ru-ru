---
title: <certificateValidator>
ms.date: 03/30/2017
ms.assetid: 86161897-c20f-4ad8-9d7f-050c247251bf
author: BrucePerlerMS
ms.openlocfilehash: df52212305e0865b8c03fdd49068cb7c7da4fa38
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55277459"
---
# <a name="certificatevalidator"></a><span data-ttu-id="1f8ba-101">\<certificateValidator ></span><span class="sxs-lookup"><span data-stu-id="1f8ba-101">\<certificateValidator></span></span>
<span data-ttu-id="1f8ba-102">Задает пользовательский тип для проверки сертификата.</span><span class="sxs-lookup"><span data-stu-id="1f8ba-102">Specifies a custom type for certificate validation.</span></span> <span data-ttu-id="1f8ba-103">Этот тип используется только в том случае, если `certificateValidationMode` атрибут [ \<certificateValidation >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md) имеет значение «Custom».</span><span class="sxs-lookup"><span data-stu-id="1f8ba-103">This type is used only if the `certificateValidationMode` attribute of the [\<certificateValidation>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md) element is set to "Custom".</span></span>  
  
 <span data-ttu-id="1f8ba-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="1f8ba-104">\<system.identityModel></span></span>  
<span data-ttu-id="1f8ba-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="1f8ba-105">\<identityConfiguration></span></span>  
<span data-ttu-id="1f8ba-106">\<certificateValidation ></span><span class="sxs-lookup"><span data-stu-id="1f8ba-106">\<certificateValidation></span></span>  
<span data-ttu-id="1f8ba-107">\<certificateValidator ></span><span class="sxs-lookup"><span data-stu-id="1f8ba-107">\<certificateValidator></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1f8ba-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1f8ba-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1f8ba-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="1f8ba-109">Attributes and Elements</span></span>  
 <span data-ttu-id="1f8ba-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="1f8ba-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1f8ba-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="1f8ba-111">Attributes</span></span>  
  
|<span data-ttu-id="1f8ba-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="1f8ba-112">Attribute</span></span>|<span data-ttu-id="1f8ba-113">Описание</span><span class="sxs-lookup"><span data-stu-id="1f8ba-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1f8ba-114">type</span><span class="sxs-lookup"><span data-stu-id="1f8ba-114">type</span></span>|<span data-ttu-id="1f8ba-115">Задает пользовательский тип, производный от <xref:System.IdentityModel.Selectors.X509CertificateValidator> класса.</span><span class="sxs-lookup"><span data-stu-id="1f8ba-115">Specifies a custom type that derives from the <xref:System.IdentityModel.Selectors.X509CertificateValidator> class.</span></span> <span data-ttu-id="1f8ba-116">Задайте `certificateValidationMode` атрибут [ \<certificateValidation >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md) элемент на «Пользовательский», чтобы использовать этот тип.</span><span class="sxs-lookup"><span data-stu-id="1f8ba-116">Set the `certificateValidationMode` attribute of the [\<certificateValidation>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md) element to "Custom" to use this type.</span></span> <span data-ttu-id="1f8ba-117">Дополнительные сведения о способах указания `type` атрибут, см. в разделе [ссылок на пользовательские типы](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).</span><span class="sxs-lookup"><span data-stu-id="1f8ba-117">For more information about how to specify the `type` attribute, see [Custom Type References](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).</span></span> <span data-ttu-id="1f8ba-118">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="1f8ba-118">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1f8ba-119">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="1f8ba-119">Child Elements</span></span>  
 <span data-ttu-id="1f8ba-120">Нет</span><span class="sxs-lookup"><span data-stu-id="1f8ba-120">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1f8ba-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="1f8ba-121">Parent Elements</span></span>  
  
|<span data-ttu-id="1f8ba-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="1f8ba-122">Element</span></span>|<span data-ttu-id="1f8ba-123">Описание:</span><span class="sxs-lookup"><span data-stu-id="1f8ba-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1f8ba-124">\<certificateValidation ></span><span class="sxs-lookup"><span data-stu-id="1f8ba-124">\<certificateValidation></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md)|<span data-ttu-id="1f8ba-125">Управляет параметрами, используемых обработчиками токена для проверки сертификатов.</span><span class="sxs-lookup"><span data-stu-id="1f8ba-125">Controls the settings that token handlers use to validate certificates.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="1f8ba-126">Пример</span><span class="sxs-lookup"><span data-stu-id="1f8ba-126">Example</span></span>  
  
```xml  
<certificateValidation certificateValidationMode="Custom"  
                       revocationMode="Online"  
                       trustedStoreLocation="LocalMachine">  
    <certificateValidator type="MyNamespace.CustomValidator, MyAssembly" />    
</certificateValidation>        
```
