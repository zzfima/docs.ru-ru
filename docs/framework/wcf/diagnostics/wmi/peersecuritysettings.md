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
ms.openlocfilehash: 02cd483f2f7ec5e599b286b672d051a0e8d57940
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="peersecuritysettings"></a><span data-ttu-id="898b0-102">PeerSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="898b0-102">PeerSecuritySettings</span></span>
<span data-ttu-id="898b0-103">PeerSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="898b0-103">PeerSecuritySettings</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="898b0-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="898b0-104">Syntax</span></span>  
  
```  
class PeerSecuritySettings  
{  
  string Mode;  
  PeerTransportSecuritySettings Transport;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="898b0-105">Методы</span><span class="sxs-lookup"><span data-stu-id="898b0-105">Methods</span></span>  
 <span data-ttu-id="898b0-106">Класс PeerSecuritySettings не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="898b0-106">The PeerSecuritySettings class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="898b0-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="898b0-107">Properties</span></span>  
 <span data-ttu-id="898b0-108">Класс PeerSecuritySettings имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="898b0-108">The PeerSecuritySettings class has the following properties:</span></span>  
  
### <a name="mode"></a><span data-ttu-id="898b0-109">Mode</span><span class="sxs-lookup"><span data-stu-id="898b0-109">Mode</span></span>  
 <span data-ttu-id="898b0-110">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="898b0-110">Data type: string</span></span>  
  
 <span data-ttu-id="898b0-111">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="898b0-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="898b0-112">Определяет, использует ли настроенная с помощью привязки конечная точка безопасность на уровне сообщений и на транспортном уровне.</span><span class="sxs-lookup"><span data-stu-id="898b0-112">Whether message-level and transport-level security are used by an endpoint configured with the binding.</span></span>  
  
### <a name="transport"></a><span data-ttu-id="898b0-113">Transport</span><span class="sxs-lookup"><span data-stu-id="898b0-113">Transport</span></span>  
 <span data-ttu-id="898b0-114">Тип данных: PeerTransportSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="898b0-114">Data type: PeerTransportSecuritySettings</span></span>  
  
 <span data-ttu-id="898b0-115">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="898b0-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="898b0-116">Параметры безопасности транспорта.</span><span class="sxs-lookup"><span data-stu-id="898b0-116">Transport security settings.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="898b0-117">Требования</span><span class="sxs-lookup"><span data-stu-id="898b0-117">Requirements</span></span>  
  
|<span data-ttu-id="898b0-118">MOF</span><span class="sxs-lookup"><span data-stu-id="898b0-118">MOF</span></span>|<span data-ttu-id="898b0-119">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="898b0-119">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="898b0-120">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="898b0-120">Namespace</span></span>|<span data-ttu-id="898b0-121">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="898b0-121">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="898b0-122">См. также</span><span class="sxs-lookup"><span data-stu-id="898b0-122">See Also</span></span>  
 <xref:System.ServiceModel.PeerSecuritySettings>
