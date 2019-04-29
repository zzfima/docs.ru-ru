---
title: <sessionTokenRequirement>
ms.date: 03/30/2017
ms.assetid: 496a1735-cbb7-49d5-a6aa-dd5550462073
author: BrucePerlerMS
ms.openlocfilehash: 0c575e02862884e8f7ecf062138c36fe731f8e19
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61793774"
---
# <a name="sessiontokenrequirement"></a><span data-ttu-id="0cf42-101">\<sessionTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="0cf42-101">\<sessionTokenRequirement></span></span>
<span data-ttu-id="0cf42-102">Предоставляет конфигурацию для <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> классом или производными классами.</span><span class="sxs-lookup"><span data-stu-id="0cf42-102">Provides configuration for the <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> class or derived classes.</span></span>  
  
 <span data-ttu-id="0cf42-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="0cf42-103">\<system.identityModel></span></span>  
<span data-ttu-id="0cf42-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="0cf42-104">\<identityConfiguration></span></span>  
<span data-ttu-id="0cf42-105">\<securityTokenHandlers ></span><span class="sxs-lookup"><span data-stu-id="0cf42-105">\<securityTokenHandlers></span></span>  
<span data-ttu-id="0cf42-106">\<add></span><span class="sxs-lookup"><span data-stu-id="0cf42-106">\<add></span></span>  
<span data-ttu-id="0cf42-107">\<sessionTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="0cf42-107">\<sessionTokenRequirement></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0cf42-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0cf42-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0cf42-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="0cf42-109">Attributes and Elements</span></span>  
 <span data-ttu-id="0cf42-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="0cf42-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0cf42-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="0cf42-111">Attributes</span></span>  
  
|<span data-ttu-id="0cf42-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="0cf42-112">Attribute</span></span>|<span data-ttu-id="0cf42-113">Описание</span><span class="sxs-lookup"><span data-stu-id="0cf42-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0cf42-114">время существования</span><span class="sxs-lookup"><span data-stu-id="0cf42-114">lifetime</span></span>|<span data-ttu-id="0cf42-115">Задает время существования токенов сеансов.</span><span class="sxs-lookup"><span data-stu-id="0cf42-115">Specifies the lifetime of session tokens.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0cf42-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="0cf42-116">Child Elements</span></span>  
 <span data-ttu-id="0cf42-117">Нет</span><span class="sxs-lookup"><span data-stu-id="0cf42-117">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0cf42-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="0cf42-118">Parent Elements</span></span>  
  
|<span data-ttu-id="0cf42-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="0cf42-119">Element</span></span>|<span data-ttu-id="0cf42-120">Описание</span><span class="sxs-lookup"><span data-stu-id="0cf42-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0cf42-121">\<add></span><span class="sxs-lookup"><span data-stu-id="0cf42-121">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/add.md)|<span data-ttu-id="0cf42-122">Добавляет обработчик токенов безопасности в коллекцию обработчиков токенов.</span><span class="sxs-lookup"><span data-stu-id="0cf42-122">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="0cf42-123">Пример</span><span class="sxs-lookup"><span data-stu-id="0cf42-123">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel">           
    <sessionTokenRequirement lifetime="10:00" />  
</add>  
```
