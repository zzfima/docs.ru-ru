---
title: PeerSecuritySettings
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 24ae0d35-f3a3-419b-afd6-686e22aae27b
caps.latest.revision: "7"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: 48a9cc5a7a05b47a5589d1bf9a730184fb7f0543
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="peersecuritysettings"></a><span data-ttu-id="aef0d-102">PeerSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="aef0d-102">PeerSecuritySettings</span></span>
<span data-ttu-id="aef0d-103">PeerSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="aef0d-103">PeerSecuritySettings</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aef0d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="aef0d-104">Syntax</span></span>  
  
```  
class PeerSecuritySettings  
{  
  string Mode;  
  PeerTransportSecuritySettings Transport;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="aef0d-105">Методы</span><span class="sxs-lookup"><span data-stu-id="aef0d-105">Methods</span></span>  
 <span data-ttu-id="aef0d-106">Класс PeerSecuritySettings не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="aef0d-106">The PeerSecuritySettings class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="aef0d-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="aef0d-107">Properties</span></span>  
 <span data-ttu-id="aef0d-108">Класс PeerSecuritySettings имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="aef0d-108">The PeerSecuritySettings class has the following properties:</span></span>  
  
### <a name="mode"></a><span data-ttu-id="aef0d-109">Режим</span><span class="sxs-lookup"><span data-stu-id="aef0d-109">Mode</span></span>  
 <span data-ttu-id="aef0d-110">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="aef0d-110">Data type: string</span></span>  
  
 <span data-ttu-id="aef0d-111">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="aef0d-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="aef0d-112">Определяет, использует ли настроенная с помощью привязки конечная точка безопасность на уровне сообщений и на транспортном уровне.</span><span class="sxs-lookup"><span data-stu-id="aef0d-112">Whether message-level and transport-level security are used by an endpoint configured with the binding.</span></span>  
  
### <a name="transport"></a><span data-ttu-id="aef0d-113">Transport</span><span class="sxs-lookup"><span data-stu-id="aef0d-113">Transport</span></span>  
 <span data-ttu-id="aef0d-114">Тип данных: PeerTransportSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="aef0d-114">Data type: PeerTransportSecuritySettings</span></span>  
  
 <span data-ttu-id="aef0d-115">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="aef0d-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="aef0d-116">Параметры безопасности транспорта.</span><span class="sxs-lookup"><span data-stu-id="aef0d-116">Transport security settings.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aef0d-117">Требования</span><span class="sxs-lookup"><span data-stu-id="aef0d-117">Requirements</span></span>  
  
|<span data-ttu-id="aef0d-118">MOF</span><span class="sxs-lookup"><span data-stu-id="aef0d-118">MOF</span></span>|<span data-ttu-id="aef0d-119">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="aef0d-119">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="aef0d-120">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="aef0d-120">Namespace</span></span>|<span data-ttu-id="aef0d-121">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="aef0d-121">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="aef0d-122">См. также</span><span class="sxs-lookup"><span data-stu-id="aef0d-122">See Also</span></span>  
 <xref:System.ServiceModel.PeerSecuritySettings>
