---
title: <remove>
ms.date: 03/30/2017
ms.assetid: 4058e2f1-7db4-4d1a-84dd-1b52836f2ae6
author: BrucePerlerMS
ms.openlocfilehash: 17c4d4289cf90b66d52986c054d4807ecff2b3d8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61793891"
---
# <a name="remove"></a><span data-ttu-id="e9a2d-101">\<Удалить ></span><span class="sxs-lookup"><span data-stu-id="e9a2d-101">\<remove></span></span>
<span data-ttu-id="e9a2d-102">Удаляет обработчик токенов безопасности из коллекции обработчиков токенов.</span><span class="sxs-lookup"><span data-stu-id="e9a2d-102">Removes the specified security token handler from the token handler collection.</span></span>  
  
 <span data-ttu-id="e9a2d-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="e9a2d-103">\<system.identityModel></span></span>  
<span data-ttu-id="e9a2d-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="e9a2d-104">\<identityConfiguration></span></span>  
<span data-ttu-id="e9a2d-105">\<securityTokenHandlers ></span><span class="sxs-lookup"><span data-stu-id="e9a2d-105">\<securityTokenHandlers></span></span>  
<span data-ttu-id="e9a2d-106">\<Удалить ></span><span class="sxs-lookup"><span data-stu-id="e9a2d-106">\<remove></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9a2d-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e9a2d-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e9a2d-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="e9a2d-108">Attributes and Elements</span></span>  
 <span data-ttu-id="e9a2d-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="e9a2d-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e9a2d-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="e9a2d-110">Attributes</span></span>  
  
|<span data-ttu-id="e9a2d-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="e9a2d-111">Attribute</span></span>|<span data-ttu-id="e9a2d-112">Описание</span><span class="sxs-lookup"><span data-stu-id="e9a2d-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e9a2d-113">type</span><span class="sxs-lookup"><span data-stu-id="e9a2d-113">type</span></span>|<span data-ttu-id="e9a2d-114">Имя типа CLR обработчик токенов для удаления.</span><span class="sxs-lookup"><span data-stu-id="e9a2d-114">The CLR type name of the token handler to be removed.</span></span> <span data-ttu-id="e9a2d-115">Дополнительные сведения о способах указания `type` атрибут, см. в разделе [ссылок на пользовательские типы](https://docs.microsoft.com/previous-versions/windows-identity-foundation/gg638728(v=msdn.10)#custom-type-references).</span><span class="sxs-lookup"><span data-stu-id="e9a2d-115">For more information about how to specify the `type` attribute, see [Custom Type References](https://docs.microsoft.com/previous-versions/windows-identity-foundation/gg638728(v=msdn.10)#custom-type-references).</span></span> <span data-ttu-id="e9a2d-116">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="e9a2d-116">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e9a2d-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="e9a2d-117">Child Elements</span></span>  
 <span data-ttu-id="e9a2d-118">Нет</span><span class="sxs-lookup"><span data-stu-id="e9a2d-118">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e9a2d-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="e9a2d-119">Parent Elements</span></span>  
  
|<span data-ttu-id="e9a2d-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="e9a2d-120">Element</span></span>|<span data-ttu-id="e9a2d-121">Описание</span><span class="sxs-lookup"><span data-stu-id="e9a2d-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e9a2d-122">\<securityTokenHandlers ></span><span class="sxs-lookup"><span data-stu-id="e9a2d-122">\<securityTokenHandlers></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlers.md)|<span data-ttu-id="e9a2d-123">Задает коллекцию обработчиков токенов безопасности, которые зарегистрированы с конечной точкой.</span><span class="sxs-lookup"><span data-stu-id="e9a2d-123">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="e9a2d-124">Пример</span><span class="sxs-lookup"><span data-stu-id="e9a2d-124">Example</span></span>  
 <span data-ttu-id="e9a2d-125">Следующий код XML показывает использование `<add>` и `<remove>` элементов для замены маркера обработчик сеанса по умолчанию обработчик токенов пользовательского сеанса.</span><span class="sxs-lookup"><span data-stu-id="e9a2d-125">The following XML shows the use of the `<add>` and `<remove>` elements to replace the default session token handler with a custom session token handler.</span></span> <span data-ttu-id="e9a2d-126">XML-код взят из `ClaimsAwareWebFarm` образца.</span><span class="sxs-lookup"><span data-stu-id="e9a2d-126">The XML is taken from the `ClaimsAwareWebFarm` sample.</span></span>  
  
```xml  
<securityTokenHandlers>  
  <remove type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
  <add type="System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
</securityTokenHandlers>  
```
