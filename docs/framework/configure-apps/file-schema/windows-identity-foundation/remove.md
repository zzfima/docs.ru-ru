---
title: <remove>
ms.date: 03/30/2017
ms.assetid: 4058e2f1-7db4-4d1a-84dd-1b52836f2ae6
author: BrucePerlerMS
ms.openlocfilehash: cfdfbb3aabde253ad17b221801b20c1ac9a45c2d
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251925"
---
# <a name="remove"></a><span data-ttu-id="a8a92-101">\<Удалить ></span><span class="sxs-lookup"><span data-stu-id="a8a92-101">\<remove></span></span>
<span data-ttu-id="a8a92-102">Удаляет указанный обработчик маркеров безопасности из коллекции обработчиков маркеров.</span><span class="sxs-lookup"><span data-stu-id="a8a92-102">Removes the specified security token handler from the token handler collection.</span></span>  
  
<span data-ttu-id="a8a92-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="a8a92-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="a8a92-104">&nbsp;&nbsp;[ **\<> System. identityModel**](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="a8a92-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="a8a92-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<identityConfiguration >** ](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="a8a92-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="a8a92-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<securityTokenHandlers >** ](securitytokenhandlers.md)</span><span class="sxs-lookup"><span data-stu-id="a8a92-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span></span>\
<span data-ttu-id="a8a92-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Удалить >**</span><span class="sxs-lookup"><span data-stu-id="a8a92-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a8a92-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a8a92-108">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <remove type=xs:string >  
      </remove>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a8a92-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="a8a92-109">Attributes and Elements</span></span>  
 <span data-ttu-id="a8a92-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="a8a92-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a8a92-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="a8a92-111">Attributes</span></span>  
  
|<span data-ttu-id="a8a92-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="a8a92-112">Attribute</span></span>|<span data-ttu-id="a8a92-113">Описание</span><span class="sxs-lookup"><span data-stu-id="a8a92-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a8a92-114">type</span><span class="sxs-lookup"><span data-stu-id="a8a92-114">type</span></span>|<span data-ttu-id="a8a92-115">Имя типа CLR удаляемого обработчика токенов.</span><span class="sxs-lookup"><span data-stu-id="a8a92-115">The CLR type name of the token handler to be removed.</span></span> <span data-ttu-id="a8a92-116">Дополнительные сведения об указании `type` атрибута см. в разделе [ссылки на пользовательские типы](https://docs.microsoft.com/previous-versions/windows-identity-foundation/gg638728(v=msdn.10)#custom-type-references).</span><span class="sxs-lookup"><span data-stu-id="a8a92-116">For more information about how to specify the `type` attribute, see [Custom Type References](https://docs.microsoft.com/previous-versions/windows-identity-foundation/gg638728(v=msdn.10)#custom-type-references).</span></span> <span data-ttu-id="a8a92-117">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="a8a92-117">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a8a92-118">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="a8a92-118">Child Elements</span></span>  
 <span data-ttu-id="a8a92-119">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="a8a92-119">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a8a92-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="a8a92-120">Parent Elements</span></span>  
  
|<span data-ttu-id="a8a92-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="a8a92-121">Element</span></span>|<span data-ttu-id="a8a92-122">Описание</span><span class="sxs-lookup"><span data-stu-id="a8a92-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a8a92-123">\<securityTokenHandlers ></span><span class="sxs-lookup"><span data-stu-id="a8a92-123">\<securityTokenHandlers></span></span>](securitytokenhandlers.md)|<span data-ttu-id="a8a92-124">Указывает коллекцию обработчиков маркеров безопасности, зарегистрированных в конечной точке.</span><span class="sxs-lookup"><span data-stu-id="a8a92-124">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="a8a92-125">Пример</span><span class="sxs-lookup"><span data-stu-id="a8a92-125">Example</span></span>  
 <span data-ttu-id="a8a92-126">В следующем коде XML показано использование `<add>` элементов и `<remove>` для замены обработчика токена сеанса по умолчанию обработчиком пользовательского маркера сеанса.</span><span class="sxs-lookup"><span data-stu-id="a8a92-126">The following XML shows the use of the `<add>` and `<remove>` elements to replace the default session token handler with a custom session token handler.</span></span> <span data-ttu-id="a8a92-127">XML взят из `ClaimsAwareWebFarm` примера.</span><span class="sxs-lookup"><span data-stu-id="a8a92-127">The XML is taken from the `ClaimsAwareWebFarm` sample.</span></span>  
  
```xml  
<securityTokenHandlers>  
  <remove type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
  <add type="System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
</securityTokenHandlers>  
```
