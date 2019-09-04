---
title: <certificateValidator>
ms.date: 03/30/2017
ms.assetid: 86161897-c20f-4ad8-9d7f-050c247251bf
author: BrucePerlerMS
ms.openlocfilehash: 30f81dd5948a7d366c1116cffd347c85a396f5ae
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252116"
---
# <a name="certificatevalidator"></a><span data-ttu-id="46041-101">\<Цертификатевалидатор ></span><span class="sxs-lookup"><span data-stu-id="46041-101">\<certificateValidator></span></span>
<span data-ttu-id="46041-102">Указывает пользовательский тип для проверки сертификата.</span><span class="sxs-lookup"><span data-stu-id="46041-102">Specifies a custom type for certificate validation.</span></span> <span data-ttu-id="46041-103">Этот тип используется только в том случае `certificateValidationMode` , если атрибуту [ \<элемента цертификатевалидатион >](certificatevalidation.md) присвоено значение Custom.</span><span class="sxs-lookup"><span data-stu-id="46041-103">This type is used only if the `certificateValidationMode` attribute of the [\<certificateValidation>](certificatevalidation.md) element is set to "Custom".</span></span>  
  
<span data-ttu-id="46041-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="46041-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="46041-105">&nbsp;&nbsp;[ **\<> System. identityModel**](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="46041-105">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="46041-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<identityConfiguration >** ](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="46041-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="46041-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Цертификатевалидатион >** ](certificatevalidation.md)</span><span class="sxs-lookup"><span data-stu-id="46041-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<certificateValidation>**](certificatevalidation.md)</span></span>\
<span data-ttu-id="46041-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Цертификатевалидатор >**</span><span class="sxs-lookup"><span data-stu-id="46041-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<certificateValidator>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46041-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="46041-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="46041-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="46041-110">Attributes and Elements</span></span>  
 <span data-ttu-id="46041-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="46041-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="46041-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="46041-112">Attributes</span></span>  
  
|<span data-ttu-id="46041-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="46041-113">Attribute</span></span>|<span data-ttu-id="46041-114">Описание</span><span class="sxs-lookup"><span data-stu-id="46041-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="46041-115">type</span><span class="sxs-lookup"><span data-stu-id="46041-115">type</span></span>|<span data-ttu-id="46041-116">Указывает пользовательский тип, производный от <xref:System.IdentityModel.Selectors.X509CertificateValidator> класса.</span><span class="sxs-lookup"><span data-stu-id="46041-116">Specifies a custom type that derives from the <xref:System.IdentityModel.Selectors.X509CertificateValidator> class.</span></span> <span data-ttu-id="46041-117">Задайте для `certificateValidationMode` [ атрибута\<элемента > цертификатевалидатион](certificatevalidation.md) значение Custom, чтобы использовать этот тип.</span><span class="sxs-lookup"><span data-stu-id="46041-117">Set the `certificateValidationMode` attribute of the [\<certificateValidation>](certificatevalidation.md) element to "Custom" to use this type.</span></span> <span data-ttu-id="46041-118">Дополнительные сведения об указании `type` атрибута см. в разделе [ссылки на пользовательские типы](../windows-workflow-foundation/index.md).</span><span class="sxs-lookup"><span data-stu-id="46041-118">For more information about how to specify the `type` attribute, see [Custom Type References](../windows-workflow-foundation/index.md).</span></span> <span data-ttu-id="46041-119">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="46041-119">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="46041-120">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="46041-120">Child Elements</span></span>  
 <span data-ttu-id="46041-121">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="46041-121">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="46041-122">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="46041-122">Parent Elements</span></span>  
  
|<span data-ttu-id="46041-123">Элемент</span><span class="sxs-lookup"><span data-stu-id="46041-123">Element</span></span>|<span data-ttu-id="46041-124">Описание</span><span class="sxs-lookup"><span data-stu-id="46041-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="46041-125">\<Цертификатевалидатион ></span><span class="sxs-lookup"><span data-stu-id="46041-125">\<certificateValidation></span></span>](certificatevalidation.md)|<span data-ttu-id="46041-126">Управляет параметрами, которые обработчики маркеров используют для проверки сертификатов.</span><span class="sxs-lookup"><span data-stu-id="46041-126">Controls the settings that token handlers use to validate certificates.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="46041-127">Пример</span><span class="sxs-lookup"><span data-stu-id="46041-127">Example</span></span>  
  
```xml  
<certificateValidation certificateValidationMode="Custom"  
                       revocationMode="Online"  
                       trustedStoreLocation="LocalMachine">  
    <certificateValidator type="MyNamespace.CustomValidator, MyAssembly" />    
</certificateValidation>        
```
