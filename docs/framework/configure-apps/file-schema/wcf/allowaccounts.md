---
title: '&lt;allowAccounts&gt;'
ms.date: 03/30/2017
ms.assetid: 166923a9-a8ac-478f-92f9-529d9667f3a6
ms.openlocfilehash: 61310d530cfec2862fb64155777cd0e88132f748
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/09/2019
ms.locfileid: "54145943"
---
# <a name="ltallowaccountsgt"></a><span data-ttu-id="cfd60-102">&lt;allowAccounts&gt;</span><span class="sxs-lookup"><span data-stu-id="cfd60-102">&lt;allowAccounts&gt;</span></span>
<span data-ttu-id="cfd60-103">Содержит коллекцию элементов конфигурации, задающих учетные записи пользователей для процессов, на которых размещены службы Windows Communication Foundation (WCF) и предоставляется доступ на подключение к общей службы.</span><span class="sxs-lookup"><span data-stu-id="cfd60-103">Contains a collection of configuration elements that specify user accounts for processes that host Windows Communication Foundation (WCF) services, and are granted connection access to the sharing service.</span></span>  
  
 <span data-ttu-id="cfd60-104">\<system.serviceModel.activation ></span><span class="sxs-lookup"><span data-stu-id="cfd60-104">\<system.serviceModel.activation></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cfd60-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cfd60-105">Syntax</span></span>  
  
```xml  
<allowAccounts>
  <add securityIdentifier="String" />
</allowAccounts>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cfd60-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="cfd60-106">Attributes and Elements</span></span>  
 <span data-ttu-id="cfd60-107">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="cfd60-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cfd60-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="cfd60-108">Attributes</span></span>  
 <span data-ttu-id="cfd60-109">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="cfd60-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="cfd60-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="cfd60-110">Child Elements</span></span>  
  
|<span data-ttu-id="cfd60-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="cfd60-111">Attribute</span></span>|<span data-ttu-id="cfd60-112">Описание:</span><span class="sxs-lookup"><span data-stu-id="cfd60-112">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="cfd60-113">\<add></span><span class="sxs-lookup"><span data-stu-id="cfd60-113">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-allowaccounts.md)|<span data-ttu-id="cfd60-114">Добавляет учетную запись пользователя для процессов размещения служб WCF, которые предоставляются доступ при подключении к службе управления доступом</span><span class="sxs-lookup"><span data-stu-id="cfd60-114">Adds a user account for processes that host WCF services, and are granted connection access to the sharing service</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="cfd60-115">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="cfd60-115">Parent Elements</span></span>  
  
|<span data-ttu-id="cfd60-116">Элемент</span><span class="sxs-lookup"><span data-stu-id="cfd60-116">Element</span></span>|<span data-ttu-id="cfd60-117">Описание</span><span class="sxs-lookup"><span data-stu-id="cfd60-117">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="cfd60-118">[\<NET.pipe >](../../../../../docs/framework/configure-apps/file-schema/wcf/net-pipe.md) или [ \<net.tcp >](../../../../../docs/framework/configure-apps/file-schema/wcf/net-tcp.md)</span><span class="sxs-lookup"><span data-stu-id="cfd60-118">[\<net.pipe>](../../../../../docs/framework/configure-apps/file-schema/wcf/net-pipe.md) or [\<net.tcp>](../../../../../docs/framework/configure-apps/file-schema/wcf/net-tcp.md)</span></span>|<span data-ttu-id="cfd60-119">Задает параметры конфигурации для совместно используемых служб Net Pipe или TCP.</span><span class="sxs-lookup"><span data-stu-id="cfd60-119">Specifies configuration settings for the Net Pipe or TCP sharing services.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="cfd60-120">См. также</span><span class="sxs-lookup"><span data-stu-id="cfd60-120">See Also</span></span>  
 <xref:System.ServiceModel.Activation.Configuration.NetTcpSection.AllowAccounts%2A>  
 <xref:System.ServiceModel.Activation.Configuration.NetPipeSection.AllowAccounts%2A>  
 <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElementCollection>  
 <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElement>
