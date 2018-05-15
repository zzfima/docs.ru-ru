---
title: PeerSecuritySettings
ms.date: 03/30/2017
ms.assetid: 24ae0d35-f3a3-419b-afd6-686e22aae27b
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 58b372f26fee7dc180d75731fd4855db569c87c7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="peersecuritysettings"></a><span data-ttu-id="dac65-102">PeerSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="dac65-102">PeerSecuritySettings</span></span>
<span data-ttu-id="dac65-103">PeerSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="dac65-103">PeerSecuritySettings</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dac65-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="dac65-104">Syntax</span></span>  
  
```  
class PeerSecuritySettings  
{  
  string Mode;  
  PeerTransportSecuritySettings Transport;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="dac65-105">Методы</span><span class="sxs-lookup"><span data-stu-id="dac65-105">Methods</span></span>  
 <span data-ttu-id="dac65-106">Класс PeerSecuritySettings не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="dac65-106">The PeerSecuritySettings class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="dac65-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="dac65-107">Properties</span></span>  
 <span data-ttu-id="dac65-108">Класс PeerSecuritySettings имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="dac65-108">The PeerSecuritySettings class has the following properties:</span></span>  
  
### <a name="mode"></a><span data-ttu-id="dac65-109">Режим</span><span class="sxs-lookup"><span data-stu-id="dac65-109">Mode</span></span>  
 <span data-ttu-id="dac65-110">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="dac65-110">Data type: string</span></span>  
  
 <span data-ttu-id="dac65-111">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="dac65-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="dac65-112">Определяет, использует ли настроенная с помощью привязки конечная точка безопасность на уровне сообщений и на транспортном уровне.</span><span class="sxs-lookup"><span data-stu-id="dac65-112">Whether message-level and transport-level security are used by an endpoint configured with the binding.</span></span>  
  
### <a name="transport"></a><span data-ttu-id="dac65-113">Transport</span><span class="sxs-lookup"><span data-stu-id="dac65-113">Transport</span></span>  
 <span data-ttu-id="dac65-114">Тип данных: PeerTransportSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="dac65-114">Data type: PeerTransportSecuritySettings</span></span>  
  
 <span data-ttu-id="dac65-115">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="dac65-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="dac65-116">Параметры безопасности транспорта.</span><span class="sxs-lookup"><span data-stu-id="dac65-116">Transport security settings.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dac65-117">Требования</span><span class="sxs-lookup"><span data-stu-id="dac65-117">Requirements</span></span>  
  
|<span data-ttu-id="dac65-118">MOF</span><span class="sxs-lookup"><span data-stu-id="dac65-118">MOF</span></span>|<span data-ttu-id="dac65-119">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="dac65-119">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="dac65-120">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="dac65-120">Namespace</span></span>|<span data-ttu-id="dac65-121">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="dac65-121">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="dac65-122">См. также</span><span class="sxs-lookup"><span data-stu-id="dac65-122">See Also</span></span>  
 <xref:System.ServiceModel.PeerSecuritySettings>
