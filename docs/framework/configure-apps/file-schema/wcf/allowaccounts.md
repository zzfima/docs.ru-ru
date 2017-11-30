---
title: '&lt;allowAccounts&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 166923a9-a8ac-478f-92f9-529d9667f3a6
caps.latest.revision: "9"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 8e1cf4c4428814361a56b5fd06dcce9e1512c836
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ltallowaccountsgt"></a><span data-ttu-id="8ec37-102">&lt;allowAccounts&gt;</span><span class="sxs-lookup"><span data-stu-id="8ec37-102">&lt;allowAccounts&gt;</span></span>
<span data-ttu-id="8ec37-103">Содержит коллекцию элементов конфигурации, которые задают учетные записи пользователей для процессов служб [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)], которые имеют доступ к совместно используемым службам.</span><span class="sxs-lookup"><span data-stu-id="8ec37-103">Contains a collection of configuration elements that specify user accounts for processes that host [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] services, and are granted connection access to the sharing service.</span></span>  
  
 <span data-ttu-id="8ec37-104">\<system.serviceModel.activation ></span><span class="sxs-lookup"><span data-stu-id="8ec37-104">\<system.serviceModel.activation></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8ec37-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8ec37-105">Syntax</span></span>  
  
```xml  
<allowAccounts>  
   <add securityIdentifier="String"/>  
</allowAccounts>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8ec37-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="8ec37-106">Attributes and Elements</span></span>  
 <span data-ttu-id="8ec37-107">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="8ec37-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8ec37-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="8ec37-108">Attributes</span></span>  
 <span data-ttu-id="8ec37-109">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="8ec37-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="8ec37-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="8ec37-110">Child Elements</span></span>  
  
|<span data-ttu-id="8ec37-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="8ec37-111">Attribute</span></span>|<span data-ttu-id="8ec37-112">Описание</span><span class="sxs-lookup"><span data-stu-id="8ec37-112">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="8ec37-113">\<add></span><span class="sxs-lookup"><span data-stu-id="8ec37-113">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-allowaccounts.md)|<span data-ttu-id="8ec37-114">Добавляет учетную запись пользователя для процессов служб [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)], которые имеют доступ к совместно используемым службам.</span><span class="sxs-lookup"><span data-stu-id="8ec37-114">Adds a user account for processes that host [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] services, and are granted connection access to the sharing service</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8ec37-115">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="8ec37-115">Parent Elements</span></span>  
  
|<span data-ttu-id="8ec37-116">Элемент</span><span class="sxs-lookup"><span data-stu-id="8ec37-116">Element</span></span>|<span data-ttu-id="8ec37-117">Описание</span><span class="sxs-lookup"><span data-stu-id="8ec37-117">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8ec37-118">[\<NET.pipe >](../../../../../docs/framework/configure-apps/file-schema/wcf/net-pipe.md) или [ \<net.tcp >](../../../../../docs/framework/configure-apps/file-schema/wcf/net-tcp.md)</span><span class="sxs-lookup"><span data-stu-id="8ec37-118">[\<net.pipe>](../../../../../docs/framework/configure-apps/file-schema/wcf/net-pipe.md) or [\<net.tcp>](../../../../../docs/framework/configure-apps/file-schema/wcf/net-tcp.md)</span></span>|<span data-ttu-id="8ec37-119">Задает параметры конфигурации для совместно используемых служб Net Pipe или TCP.</span><span class="sxs-lookup"><span data-stu-id="8ec37-119">Specifies configuration settings for the Net Pipe or TCP sharing services.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8ec37-120">См. также</span><span class="sxs-lookup"><span data-stu-id="8ec37-120">See Also</span></span>  
 <xref:System.ServiceModel.Activation.Configuration.NetTcpSection.AllowAccounts%2A>  
 <xref:System.ServiceModel.Activation.Configuration.NetPipeSection.AllowAccounts%2A>  
 <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElementCollection>  
 <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElement>
