---
title: <sessionTokenRequirement>
ms.date: 03/30/2017
ms.assetid: 496a1735-cbb7-49d5-a6aa-dd5550462073
author: BrucePerlerMS
ms.openlocfilehash: ade55a5b26826633faf2e7ef7598a4071d613bbc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152545"
---
# <a name="sessiontokenrequirement"></a><span data-ttu-id="0b0a2-101">\<sessionTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="0b0a2-101">\<sessionTokenRequirement></span></span>
<span data-ttu-id="0b0a2-102">Обеспечивает конфигурацию <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> для классов или производных классов.</span><span class="sxs-lookup"><span data-stu-id="0b0a2-102">Provides configuration for the <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> class or derived classes.</span></span>  
  
<span data-ttu-id="0b0a2-103">[**\<конфигурация>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="0b0a2-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="0b0a2-104">&nbsp;&nbsp;[**\<system.identityМодель>**](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="0b0a2-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="0b0a2-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<идентичностьНастройка>**](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="0b0a2-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="0b0a2-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span><span class="sxs-lookup"><span data-stu-id="0b0a2-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span></span>\
<span data-ttu-id="0b0a2-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<добавить>**](add.md)</span><span class="sxs-lookup"><span data-stu-id="0b0a2-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add.md)</span></span>\
<span data-ttu-id="0b0a2-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<>sessionTokenRequirement**</span><span class="sxs-lookup"><span data-stu-id="0b0a2-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<sessionTokenRequirement>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0b0a2-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0b0a2-109">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <add type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel">  
        <sessionTokenRequirement lifetime=TimeSpan >  
        </sessionTokenRequirement>  
      </add>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0b0a2-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="0b0a2-110">Attributes and Elements</span></span>  
 <span data-ttu-id="0b0a2-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="0b0a2-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0b0a2-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="0b0a2-112">Attributes</span></span>  
  
|<span data-ttu-id="0b0a2-113">attribute</span><span class="sxs-lookup"><span data-stu-id="0b0a2-113">Attribute</span></span>|<span data-ttu-id="0b0a2-114">Описание</span><span class="sxs-lookup"><span data-stu-id="0b0a2-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0b0a2-115">lifetime</span><span class="sxs-lookup"><span data-stu-id="0b0a2-115">lifetime</span></span>|<span data-ttu-id="0b0a2-116">Определяет срок службы токенов сеанса.</span><span class="sxs-lookup"><span data-stu-id="0b0a2-116">Specifies the lifetime of session tokens.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0b0a2-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="0b0a2-117">Child Elements</span></span>  
 <span data-ttu-id="0b0a2-118">None</span><span class="sxs-lookup"><span data-stu-id="0b0a2-118">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0b0a2-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="0b0a2-119">Parent Elements</span></span>  
  
|<span data-ttu-id="0b0a2-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="0b0a2-120">Element</span></span>|<span data-ttu-id="0b0a2-121">Описание</span><span class="sxs-lookup"><span data-stu-id="0b0a2-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0b0a2-122">\<добавить></span><span class="sxs-lookup"><span data-stu-id="0b0a2-122">\<add></span></span>](add.md)|<span data-ttu-id="0b0a2-123">Добавляет указанный обработчик маркеров безопасности в коллекцию обработчика маркеров.</span><span class="sxs-lookup"><span data-stu-id="0b0a2-123">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="0b0a2-124">Пример</span><span class="sxs-lookup"><span data-stu-id="0b0a2-124">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel">
    <sessionTokenRequirement lifetime="10:00" />  
</add>  
```
