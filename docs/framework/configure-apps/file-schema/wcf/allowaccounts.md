---
title: <allowAccounts>
ms.date: 03/30/2017
ms.assetid: 166923a9-a8ac-478f-92f9-529d9667f3a6
ms.openlocfilehash: c62f29c53d807cab397ff09c6163d924a71ea319
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69926603"
---
# <a name="allowaccounts"></a><span data-ttu-id="bfe40-101">\<Алловаккаунтс ></span><span class="sxs-lookup"><span data-stu-id="bfe40-101">\<allowAccounts></span></span>
<span data-ttu-id="bfe40-102">Содержит коллекцию элементов конфигурации, указывающих учетные записи пользователей для процессов, на которых размещены службы Windows Communication Foundation (WCF) и которым предоставляется доступ к службе общего доступа.</span><span class="sxs-lookup"><span data-stu-id="bfe40-102">Contains a collection of configuration elements that specify user accounts for processes that host Windows Communication Foundation (WCF) services, and are granted connection access to the sharing service.</span></span>  
  
 <span data-ttu-id="bfe40-103">\<> System. serviceModel. Activation</span><span class="sxs-lookup"><span data-stu-id="bfe40-103">\<system.serviceModel.activation></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bfe40-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bfe40-104">Syntax</span></span>  
  
```xml  
<allowAccounts>
  <add securityIdentifier="String" />
</allowAccounts>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bfe40-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="bfe40-105">Attributes and Elements</span></span>  
 <span data-ttu-id="bfe40-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="bfe40-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bfe40-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="bfe40-107">Attributes</span></span>  
 <span data-ttu-id="bfe40-108">Нет.</span><span class="sxs-lookup"><span data-stu-id="bfe40-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="bfe40-109">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="bfe40-109">Child Elements</span></span>  
  
|<span data-ttu-id="bfe40-110">Атрибут</span><span class="sxs-lookup"><span data-stu-id="bfe40-110">Attribute</span></span>|<span data-ttu-id="bfe40-111">Описание</span><span class="sxs-lookup"><span data-stu-id="bfe40-111">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="bfe40-112">\<add></span><span class="sxs-lookup"><span data-stu-id="bfe40-112">\<add></span></span>](add-of-allowaccounts.md)|<span data-ttu-id="bfe40-113">Добавляет учетную запись пользователя для процессов, на которых размещаются службы WCF, и предоставляет доступ к подключению к службе общего доступа.</span><span class="sxs-lookup"><span data-stu-id="bfe40-113">Adds a user account for processes that host WCF services, and are granted connection access to the sharing service</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="bfe40-114">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="bfe40-114">Parent Elements</span></span>  
  
|<span data-ttu-id="bfe40-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="bfe40-115">Element</span></span>|<span data-ttu-id="bfe40-116">Описание</span><span class="sxs-lookup"><span data-stu-id="bfe40-116">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="bfe40-117">NET. pipe > или [ \<](net-pipe.md) [ \<NET. TCP >](net-tcp.md)</span><span class="sxs-lookup"><span data-stu-id="bfe40-117">[\<net.pipe>](net-pipe.md) or [\<net.tcp>](net-tcp.md)</span></span>|<span data-ttu-id="bfe40-118">Задает параметры конфигурации для совместно используемых служб Net Pipe или TCP.</span><span class="sxs-lookup"><span data-stu-id="bfe40-118">Specifies configuration settings for the Net Pipe or TCP sharing services.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="bfe40-119">См. также</span><span class="sxs-lookup"><span data-stu-id="bfe40-119">See also</span></span>

- <xref:System.ServiceModel.Activation.Configuration.NetTcpSection.AllowAccounts%2A>
- <xref:System.ServiceModel.Activation.Configuration.NetPipeSection.AllowAccounts%2A>
- <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElementCollection>
- <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElement>
