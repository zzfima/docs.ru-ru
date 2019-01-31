---
title: <allowAccounts>
ms.date: 03/30/2017
ms.assetid: 166923a9-a8ac-478f-92f9-529d9667f3a6
ms.openlocfilehash: fd3121146577122446ba82528fc6e46dadbf5033
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55255553"
---
# <a name="allowaccounts"></a><span data-ttu-id="0c637-101">\<allowAccounts ></span><span class="sxs-lookup"><span data-stu-id="0c637-101">\<allowAccounts></span></span>
<span data-ttu-id="0c637-102">Содержит коллекцию элементов конфигурации, задающих учетные записи пользователей для процессов, на которых размещены службы Windows Communication Foundation (WCF) и предоставляется доступ на подключение к общей службы.</span><span class="sxs-lookup"><span data-stu-id="0c637-102">Contains a collection of configuration elements that specify user accounts for processes that host Windows Communication Foundation (WCF) services, and are granted connection access to the sharing service.</span></span>  
  
 <span data-ttu-id="0c637-103">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="0c637-103">\<system.serviceModel.activation></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c637-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0c637-104">Syntax</span></span>  
  
```xml  
<allowAccounts>
  <add securityIdentifier="String" />
</allowAccounts>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0c637-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="0c637-105">Attributes and Elements</span></span>  
 <span data-ttu-id="0c637-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="0c637-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0c637-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="0c637-107">Attributes</span></span>  
 <span data-ttu-id="0c637-108">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="0c637-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="0c637-109">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="0c637-109">Child Elements</span></span>  
  
|<span data-ttu-id="0c637-110">Атрибут</span><span class="sxs-lookup"><span data-stu-id="0c637-110">Attribute</span></span>|<span data-ttu-id="0c637-111">Описание:</span><span class="sxs-lookup"><span data-stu-id="0c637-111">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="0c637-112">\<add></span><span class="sxs-lookup"><span data-stu-id="0c637-112">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-allowaccounts.md)|<span data-ttu-id="0c637-113">Добавляет учетную запись пользователя для процессов размещения служб WCF, которые предоставляются доступ при подключении к службе управления доступом</span><span class="sxs-lookup"><span data-stu-id="0c637-113">Adds a user account for processes that host WCF services, and are granted connection access to the sharing service</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0c637-114">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="0c637-114">Parent Elements</span></span>  
  
|<span data-ttu-id="0c637-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="0c637-115">Element</span></span>|<span data-ttu-id="0c637-116">Описание:</span><span class="sxs-lookup"><span data-stu-id="0c637-116">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0c637-117">[\<NET.pipe >](../../../../../docs/framework/configure-apps/file-schema/wcf/net-pipe.md) или [ \<net.tcp >](../../../../../docs/framework/configure-apps/file-schema/wcf/net-tcp.md)</span><span class="sxs-lookup"><span data-stu-id="0c637-117">[\<net.pipe>](../../../../../docs/framework/configure-apps/file-schema/wcf/net-pipe.md) or [\<net.tcp>](../../../../../docs/framework/configure-apps/file-schema/wcf/net-tcp.md)</span></span>|<span data-ttu-id="0c637-118">Задает параметры конфигурации для совместно используемых служб Net Pipe или TCP.</span><span class="sxs-lookup"><span data-stu-id="0c637-118">Specifies configuration settings for the Net Pipe or TCP sharing services.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0c637-119">См. также</span><span class="sxs-lookup"><span data-stu-id="0c637-119">See also</span></span>
- <xref:System.ServiceModel.Activation.Configuration.NetTcpSection.AllowAccounts%2A>
- <xref:System.ServiceModel.Activation.Configuration.NetPipeSection.AllowAccounts%2A>
- <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElementCollection>
- <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElement>
