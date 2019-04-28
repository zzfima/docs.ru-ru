---
title: <allowAccounts>
ms.date: 03/30/2017
ms.assetid: 166923a9-a8ac-478f-92f9-529d9667f3a6
ms.openlocfilehash: f9def3004b116afdc629de136cdfe0b0eb6e75c2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61673541"
---
# <a name="allowaccounts"></a><span data-ttu-id="3ca20-101">\<allowAccounts ></span><span class="sxs-lookup"><span data-stu-id="3ca20-101">\<allowAccounts></span></span>
<span data-ttu-id="3ca20-102">Содержит коллекцию элементов конфигурации, задающих учетные записи пользователей для процессов, на которых размещены службы Windows Communication Foundation (WCF) и предоставляется доступ на подключение к общей службы.</span><span class="sxs-lookup"><span data-stu-id="3ca20-102">Contains a collection of configuration elements that specify user accounts for processes that host Windows Communication Foundation (WCF) services, and are granted connection access to the sharing service.</span></span>  
  
 <span data-ttu-id="3ca20-103">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="3ca20-103">\<system.serviceModel.activation></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3ca20-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3ca20-104">Syntax</span></span>  
  
```xml  
<allowAccounts>
  <add securityIdentifier="String" />
</allowAccounts>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3ca20-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="3ca20-105">Attributes and Elements</span></span>  
 <span data-ttu-id="3ca20-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="3ca20-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3ca20-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="3ca20-107">Attributes</span></span>  
 <span data-ttu-id="3ca20-108">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="3ca20-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="3ca20-109">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="3ca20-109">Child Elements</span></span>  
  
|<span data-ttu-id="3ca20-110">Атрибут</span><span class="sxs-lookup"><span data-stu-id="3ca20-110">Attribute</span></span>|<span data-ttu-id="3ca20-111">Описание</span><span class="sxs-lookup"><span data-stu-id="3ca20-111">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="3ca20-112">\<add></span><span class="sxs-lookup"><span data-stu-id="3ca20-112">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-allowaccounts.md)|<span data-ttu-id="3ca20-113">Добавляет учетную запись пользователя для процессов размещения служб WCF, которые предоставляются доступ при подключении к службе управления доступом</span><span class="sxs-lookup"><span data-stu-id="3ca20-113">Adds a user account for processes that host WCF services, and are granted connection access to the sharing service</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="3ca20-114">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="3ca20-114">Parent Elements</span></span>  
  
|<span data-ttu-id="3ca20-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="3ca20-115">Element</span></span>|<span data-ttu-id="3ca20-116">Описание</span><span class="sxs-lookup"><span data-stu-id="3ca20-116">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3ca20-117">[\<NET.pipe >](../../../../../docs/framework/configure-apps/file-schema/wcf/net-pipe.md) или [ \<net.tcp >](../../../../../docs/framework/configure-apps/file-schema/wcf/net-tcp.md)</span><span class="sxs-lookup"><span data-stu-id="3ca20-117">[\<net.pipe>](../../../../../docs/framework/configure-apps/file-schema/wcf/net-pipe.md) or [\<net.tcp>](../../../../../docs/framework/configure-apps/file-schema/wcf/net-tcp.md)</span></span>|<span data-ttu-id="3ca20-118">Задает параметры конфигурации для совместно используемых служб Net Pipe или TCP.</span><span class="sxs-lookup"><span data-stu-id="3ca20-118">Specifies configuration settings for the Net Pipe or TCP sharing services.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3ca20-119">См. также</span><span class="sxs-lookup"><span data-stu-id="3ca20-119">See also</span></span>

- <xref:System.ServiceModel.Activation.Configuration.NetTcpSection.AllowAccounts%2A>
- <xref:System.ServiceModel.Activation.Configuration.NetPipeSection.AllowAccounts%2A>
- <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElementCollection>
- <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElement>
