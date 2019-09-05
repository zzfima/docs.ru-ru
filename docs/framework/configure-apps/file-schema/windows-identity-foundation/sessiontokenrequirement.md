---
title: <sessionTokenRequirement>
ms.date: 03/30/2017
ms.assetid: 496a1735-cbb7-49d5-a6aa-dd5550462073
author: BrucePerlerMS
ms.openlocfilehash: 968c48df9e92a1dfbfb6e248b06cf4f97cece8b4
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251820"
---
# <a name="sessiontokenrequirement"></a><span data-ttu-id="cd7ca-101">\<Сессионтокенрекуиремент ></span><span class="sxs-lookup"><span data-stu-id="cd7ca-101">\<sessionTokenRequirement></span></span>
<span data-ttu-id="cd7ca-102">Предоставляет конфигурацию для <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> класса или производных классов.</span><span class="sxs-lookup"><span data-stu-id="cd7ca-102">Provides configuration for the <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> class or derived classes.</span></span>  
  
<span data-ttu-id="cd7ca-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="cd7ca-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="cd7ca-104">&nbsp;&nbsp;[ **\<> System. identityModel**](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="cd7ca-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="cd7ca-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<identityConfiguration >** ](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="cd7ca-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="cd7ca-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<securityTokenHandlers >** ](securitytokenhandlers.md)</span><span class="sxs-lookup"><span data-stu-id="cd7ca-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span></span>\
<span data-ttu-id="cd7ca-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Добавить >** ](add.md)</span><span class="sxs-lookup"><span data-stu-id="cd7ca-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add.md)</span></span>\
<span data-ttu-id="cd7ca-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Сессионтокенрекуиремент >**</span><span class="sxs-lookup"><span data-stu-id="cd7ca-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<sessionTokenRequirement>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cd7ca-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cd7ca-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cd7ca-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="cd7ca-110">Attributes and Elements</span></span>  
 <span data-ttu-id="cd7ca-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="cd7ca-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cd7ca-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="cd7ca-112">Attributes</span></span>  
  
|<span data-ttu-id="cd7ca-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="cd7ca-113">Attribute</span></span>|<span data-ttu-id="cd7ca-114">Описание</span><span class="sxs-lookup"><span data-stu-id="cd7ca-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="cd7ca-115">время существования</span><span class="sxs-lookup"><span data-stu-id="cd7ca-115">lifetime</span></span>|<span data-ttu-id="cd7ca-116">Указывает время существования маркеров сеанса.</span><span class="sxs-lookup"><span data-stu-id="cd7ca-116">Specifies the lifetime of session tokens.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="cd7ca-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="cd7ca-117">Child Elements</span></span>  
 <span data-ttu-id="cd7ca-118">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="cd7ca-118">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="cd7ca-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="cd7ca-119">Parent Elements</span></span>  
  
|<span data-ttu-id="cd7ca-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="cd7ca-120">Element</span></span>|<span data-ttu-id="cd7ca-121">Описание</span><span class="sxs-lookup"><span data-stu-id="cd7ca-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cd7ca-122">\<add></span><span class="sxs-lookup"><span data-stu-id="cd7ca-122">\<add></span></span>](add.md)|<span data-ttu-id="cd7ca-123">Добавляет указанный обработчик маркеров безопасности в коллекцию обработчиков маркеров.</span><span class="sxs-lookup"><span data-stu-id="cd7ca-123">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="cd7ca-124">Пример</span><span class="sxs-lookup"><span data-stu-id="cd7ca-124">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel">           
    <sessionTokenRequirement lifetime="10:00" />  
</add>  
```
