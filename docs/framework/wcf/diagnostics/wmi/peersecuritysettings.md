---
title: PeerSecuritySettings
ms.date: 03/30/2017
ms.assetid: 24ae0d35-f3a3-419b-afd6-686e22aae27b
author: BrucePerlerMS
ms.openlocfilehash: 18caaf2750fa3a263c09176e975204258330752c
ms.sourcegitcommit: e42d09e5966dd9fd02847d3e7eeb4ec0877069f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2018
ms.locfileid: "49371632"
---
# <a name="peersecuritysettings"></a><span data-ttu-id="4c758-102">PeerSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="4c758-102">PeerSecuritySettings</span></span>
<span data-ttu-id="4c758-103">PeerSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="4c758-103">PeerSecuritySettings</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4c758-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4c758-104">Syntax</span></span>  
  
```csharp
class PeerSecuritySettings  
{  
  string Mode;  
  PeerTransportSecuritySettings Transport;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="4c758-105">Методы</span><span class="sxs-lookup"><span data-stu-id="4c758-105">Methods</span></span>  
 <span data-ttu-id="4c758-106">Класс PeerSecuritySettings не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="4c758-106">The PeerSecuritySettings class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="4c758-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="4c758-107">Properties</span></span>  
 <span data-ttu-id="4c758-108">Класс PeerSecuritySettings имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="4c758-108">The PeerSecuritySettings class has the following properties:</span></span>  
  
### <a name="mode"></a><span data-ttu-id="4c758-109">Режим</span><span class="sxs-lookup"><span data-stu-id="4c758-109">Mode</span></span>  
 <span data-ttu-id="4c758-110">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="4c758-110">Data type: string</span></span>  
  
 <span data-ttu-id="4c758-111">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="4c758-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4c758-112">Определяет, использует ли настроенная с помощью привязки конечная точка безопасность на уровне сообщений и на транспортном уровне.</span><span class="sxs-lookup"><span data-stu-id="4c758-112">Whether message-level and transport-level security are used by an endpoint configured with the binding.</span></span>  
  
### <a name="transport"></a><span data-ttu-id="4c758-113">Transport</span><span class="sxs-lookup"><span data-stu-id="4c758-113">Transport</span></span>  
 <span data-ttu-id="4c758-114">Тип данных: PeerTransportSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="4c758-114">Data type: PeerTransportSecuritySettings</span></span>  
  
 <span data-ttu-id="4c758-115">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="4c758-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4c758-116">Параметры безопасности транспорта.</span><span class="sxs-lookup"><span data-stu-id="4c758-116">Transport security settings.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4c758-117">Требования</span><span class="sxs-lookup"><span data-stu-id="4c758-117">Requirements</span></span>  
  
|<span data-ttu-id="4c758-118">MOF</span><span class="sxs-lookup"><span data-stu-id="4c758-118">MOF</span></span>|<span data-ttu-id="4c758-119">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="4c758-119">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="4c758-120">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="4c758-120">Namespace</span></span>|<span data-ttu-id="4c758-121">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="4c758-121">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4c758-122">См. также</span><span class="sxs-lookup"><span data-stu-id="4c758-122">See Also</span></span>  
 <xref:System.ServiceModel.PeerSecuritySettings>
