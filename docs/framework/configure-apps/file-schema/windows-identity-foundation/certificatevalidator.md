---
title: <certificateValidator>
ms.date: 03/30/2017
ms.assetid: 86161897-c20f-4ad8-9d7f-050c247251bf
author: BrucePerlerMS
ms.openlocfilehash: 3f3d79d3567c1714a79423b7767ce3f454b9d52d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152792"
---
# <a name="certificatevalidator"></a><span data-ttu-id="40689-101">\<сертификатВалидатор></span><span class="sxs-lookup"><span data-stu-id="40689-101">\<certificateValidator></span></span>
<span data-ttu-id="40689-102">Определяет пользовательский тип для проверки сертификата.</span><span class="sxs-lookup"><span data-stu-id="40689-102">Specifies a custom type for certificate validation.</span></span> <span data-ttu-id="40689-103">Этот тип используется только `certificateValidationMode` в том случае, если атрибут [ \<сертификатаВалисация>](certificatevalidation.md) элемент установлен на "Custom".</span><span class="sxs-lookup"><span data-stu-id="40689-103">This type is used only if the `certificateValidationMode` attribute of the [\<certificateValidation>](certificatevalidation.md) element is set to "Custom".</span></span>  
  
<span data-ttu-id="40689-104">[**\<конфигурация>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="40689-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="40689-105">&nbsp;&nbsp;[**\<system.identityМодель>**](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="40689-105">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="40689-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<идентичностьНастройка>**](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="40689-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="40689-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<сертификатВалиста>**](certificatevalidation.md)</span><span class="sxs-lookup"><span data-stu-id="40689-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<certificateValidation>**](certificatevalidation.md)</span></span>\
<span data-ttu-id="40689-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<сертификатВалидатор>**</span><span class="sxs-lookup"><span data-stu-id="40689-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<certificateValidator>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="40689-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="40689-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="40689-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="40689-110">Attributes and Elements</span></span>  
 <span data-ttu-id="40689-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="40689-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="40689-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="40689-112">Attributes</span></span>  
  
|<span data-ttu-id="40689-113">attribute</span><span class="sxs-lookup"><span data-stu-id="40689-113">Attribute</span></span>|<span data-ttu-id="40689-114">Описание</span><span class="sxs-lookup"><span data-stu-id="40689-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="40689-115">type</span><span class="sxs-lookup"><span data-stu-id="40689-115">type</span></span>|<span data-ttu-id="40689-116">Определяет пользовательский тип, который вытекает <xref:System.IdentityModel.Selectors.X509CertificateValidator> из класса.</span><span class="sxs-lookup"><span data-stu-id="40689-116">Specifies a custom type that derives from the <xref:System.IdentityModel.Selectors.X509CertificateValidator> class.</span></span> <span data-ttu-id="40689-117">Установите `certificateValidationMode` атрибут [ \<сертификатаПроверка>](certificatevalidation.md) элементом "Custom" для использования этого типа.</span><span class="sxs-lookup"><span data-stu-id="40689-117">Set the `certificateValidationMode` attribute of the [\<certificateValidation>](certificatevalidation.md) element to "Custom" to use this type.</span></span> <span data-ttu-id="40689-118">Для получения дополнительной информации `type` о том, как указать атрибут, см. [Custom Type References](../windows-workflow-foundation/index.md)</span><span class="sxs-lookup"><span data-stu-id="40689-118">For more information about how to specify the `type` attribute, see [Custom Type References](../windows-workflow-foundation/index.md).</span></span> <span data-ttu-id="40689-119">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="40689-119">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="40689-120">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="40689-120">Child Elements</span></span>  
 <span data-ttu-id="40689-121">None</span><span class="sxs-lookup"><span data-stu-id="40689-121">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="40689-122">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="40689-122">Parent Elements</span></span>  
  
|<span data-ttu-id="40689-123">Элемент</span><span class="sxs-lookup"><span data-stu-id="40689-123">Element</span></span>|<span data-ttu-id="40689-124">Описание</span><span class="sxs-lookup"><span data-stu-id="40689-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="40689-125">\<сертификатВалиста></span><span class="sxs-lookup"><span data-stu-id="40689-125">\<certificateValidation></span></span>](certificatevalidation.md)|<span data-ttu-id="40689-126">Контролирует настройки, которые обработчики маркеров используют для проверки сертификатов.</span><span class="sxs-lookup"><span data-stu-id="40689-126">Controls the settings that token handlers use to validate certificates.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="40689-127">Пример</span><span class="sxs-lookup"><span data-stu-id="40689-127">Example</span></span>  
  
```xml  
<certificateValidation certificateValidationMode="Custom"  
                       revocationMode="Online"  
                       trustedStoreLocation="LocalMachine">  
    <certificateValidator type="MyNamespace.CustomValidator, MyAssembly" />
</certificateValidation>
```
