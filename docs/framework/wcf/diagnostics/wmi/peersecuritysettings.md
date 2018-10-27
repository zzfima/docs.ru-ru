---
title: PeerSecuritySettings
ms.date: 03/30/2017
ms.assetid: 24ae0d35-f3a3-419b-afd6-686e22aae27b
ms.openlocfilehash: 92aca4c790607de91314aacf6414d0dfacea9a9f
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2018
ms.locfileid: "50193166"
---
# <a name="peersecuritysettings"></a><span data-ttu-id="e0fcd-102">PeerSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="e0fcd-102">PeerSecuritySettings</span></span>
<span data-ttu-id="e0fcd-103">PeerSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="e0fcd-103">PeerSecuritySettings</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e0fcd-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e0fcd-104">Syntax</span></span>  
  
```csharp
class PeerSecuritySettings  
{  
  string Mode;  
  PeerTransportSecuritySettings Transport;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="e0fcd-105">Методы</span><span class="sxs-lookup"><span data-stu-id="e0fcd-105">Methods</span></span>  
 <span data-ttu-id="e0fcd-106">Класс PeerSecuritySettings не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="e0fcd-106">The PeerSecuritySettings class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="e0fcd-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="e0fcd-107">Properties</span></span>  
 <span data-ttu-id="e0fcd-108">Класс PeerSecuritySettings имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="e0fcd-108">The PeerSecuritySettings class has the following properties:</span></span>  
  
### <a name="mode"></a><span data-ttu-id="e0fcd-109">Режим</span><span class="sxs-lookup"><span data-stu-id="e0fcd-109">Mode</span></span>  
 <span data-ttu-id="e0fcd-110">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="e0fcd-110">Data type: string</span></span>  
  
 <span data-ttu-id="e0fcd-111">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="e0fcd-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e0fcd-112">Определяет, использует ли настроенная с помощью привязки конечная точка безопасность на уровне сообщений и на транспортном уровне.</span><span class="sxs-lookup"><span data-stu-id="e0fcd-112">Whether message-level and transport-level security are used by an endpoint configured with the binding.</span></span>  
  
### <a name="transport"></a><span data-ttu-id="e0fcd-113">Transport</span><span class="sxs-lookup"><span data-stu-id="e0fcd-113">Transport</span></span>  
 <span data-ttu-id="e0fcd-114">Тип данных: PeerTransportSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="e0fcd-114">Data type: PeerTransportSecuritySettings</span></span>  
  
 <span data-ttu-id="e0fcd-115">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="e0fcd-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e0fcd-116">Параметры безопасности транспорта.</span><span class="sxs-lookup"><span data-stu-id="e0fcd-116">Transport security settings.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e0fcd-117">Требования</span><span class="sxs-lookup"><span data-stu-id="e0fcd-117">Requirements</span></span>  
  
|<span data-ttu-id="e0fcd-118">MOF</span><span class="sxs-lookup"><span data-stu-id="e0fcd-118">MOF</span></span>|<span data-ttu-id="e0fcd-119">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="e0fcd-119">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="e0fcd-120">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="e0fcd-120">Namespace</span></span>|<span data-ttu-id="e0fcd-121">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="e0fcd-121">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e0fcd-122">См. также</span><span class="sxs-lookup"><span data-stu-id="e0fcd-122">See Also</span></span>  
 <xref:System.ServiceModel.PeerSecuritySettings>
