---
title: <allowAccounts>
ms.date: 03/30/2017
ms.assetid: 166923a9-a8ac-478f-92f9-529d9667f3a6
ms.openlocfilehash: 74b9d51b7400469c96fc9c8b36e4b0fb1d46969b
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398407"
---
# <a name="allowaccounts"></a><span data-ttu-id="e29a0-101">\<Алловаккаунтс ></span><span class="sxs-lookup"><span data-stu-id="e29a0-101">\<allowAccounts></span></span>
<span data-ttu-id="e29a0-102">Содержит коллекцию элементов конфигурации, указывающих учетные записи пользователей для процессов, на которых размещены службы Windows Communication Foundation (WCF) и которым предоставляется доступ к службе общего доступа.</span><span class="sxs-lookup"><span data-stu-id="e29a0-102">Contains a collection of configuration elements that specify user accounts for processes that host Windows Communication Foundation (WCF) services, and are granted connection access to the sharing service.</span></span>  
  
<span data-ttu-id="e29a0-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="e29a0-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="e29a0-104">&nbsp;&nbsp;[ **\<> System. serviceModel. Activation**](system-servicemodel-activation.md)</span><span class="sxs-lookup"><span data-stu-id="e29a0-104">&nbsp;&nbsp;[**\<system.serviceModel.activation>**](system-servicemodel-activation.md)</span></span>\
<span data-ttu-id="e29a0-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> NET. pipe**](net-pipe.md)</span><span class="sxs-lookup"><span data-stu-id="e29a0-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<net.pipe>**](net-pipe.md)</span></span>\
<span data-ttu-id="e29a0-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Алловаккаунтс >**</span><span class="sxs-lookup"><span data-stu-id="e29a0-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<allowAccounts>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e29a0-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e29a0-107">Syntax</span></span>  
  
```xml  
<allowAccounts>
  <add securityIdentifier="String" />
</allowAccounts>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e29a0-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="e29a0-108">Attributes and Elements</span></span>  
 <span data-ttu-id="e29a0-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="e29a0-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e29a0-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="e29a0-110">Attributes</span></span>  
 <span data-ttu-id="e29a0-111">Нет.</span><span class="sxs-lookup"><span data-stu-id="e29a0-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e29a0-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="e29a0-112">Child Elements</span></span>  
  
|<span data-ttu-id="e29a0-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="e29a0-113">Attribute</span></span>|<span data-ttu-id="e29a0-114">Описание</span><span class="sxs-lookup"><span data-stu-id="e29a0-114">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="e29a0-115">\<add></span><span class="sxs-lookup"><span data-stu-id="e29a0-115">\<add></span></span>](add-of-allowaccounts.md)|<span data-ttu-id="e29a0-116">Добавляет учетную запись пользователя для процессов, на которых размещаются службы WCF, и предоставляет доступ к подключению к службе общего доступа.</span><span class="sxs-lookup"><span data-stu-id="e29a0-116">Adds a user account for processes that host WCF services, and are granted connection access to the sharing service</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e29a0-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="e29a0-117">Parent Elements</span></span>  
  
|<span data-ttu-id="e29a0-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="e29a0-118">Element</span></span>|<span data-ttu-id="e29a0-119">Описание</span><span class="sxs-lookup"><span data-stu-id="e29a0-119">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e29a0-120">NET. pipe > или [ \<](net-pipe.md) [ \<NET. TCP >](net-tcp.md)</span><span class="sxs-lookup"><span data-stu-id="e29a0-120">[\<net.pipe>](net-pipe.md) or [\<net.tcp>](net-tcp.md)</span></span>|<span data-ttu-id="e29a0-121">Задает параметры конфигурации для совместно используемых служб Net Pipe или TCP.</span><span class="sxs-lookup"><span data-stu-id="e29a0-121">Specifies configuration settings for the Net Pipe or TCP sharing services.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e29a0-122">См. также</span><span class="sxs-lookup"><span data-stu-id="e29a0-122">See also</span></span>

- <xref:System.ServiceModel.Activation.Configuration.NetTcpSection.AllowAccounts%2A>
- <xref:System.ServiceModel.Activation.Configuration.NetPipeSection.AllowAccounts%2A>
- <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElementCollection>
- <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElement>
