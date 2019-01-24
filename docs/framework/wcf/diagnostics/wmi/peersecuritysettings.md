---
title: PeerSecuritySettings
ms.date: 03/30/2017
ms.assetid: 24ae0d35-f3a3-419b-afd6-686e22aae27b
ms.openlocfilehash: 761ed0e30c6acca8c910c5dc97dfbae46c1f89bb
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54564842"
---
# <a name="peersecuritysettings"></a><span data-ttu-id="60e92-102">PeerSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="60e92-102">PeerSecuritySettings</span></span>
<span data-ttu-id="60e92-103">PeerSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="60e92-103">PeerSecuritySettings</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="60e92-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="60e92-104">Syntax</span></span>  
  
```csharp
class PeerSecuritySettings  
{  
  string Mode;  
  PeerTransportSecuritySettings Transport;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="60e92-105">Методы</span><span class="sxs-lookup"><span data-stu-id="60e92-105">Methods</span></span>  
 <span data-ttu-id="60e92-106">Класс PeerSecuritySettings не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="60e92-106">The PeerSecuritySettings class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="60e92-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="60e92-107">Properties</span></span>  
 <span data-ttu-id="60e92-108">Класс PeerSecuritySettings имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="60e92-108">The PeerSecuritySettings class has the following properties:</span></span>  
  
### <a name="mode"></a><span data-ttu-id="60e92-109">Режим</span><span class="sxs-lookup"><span data-stu-id="60e92-109">Mode</span></span>  
 <span data-ttu-id="60e92-110">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="60e92-110">Data type: string</span></span>  
  
 <span data-ttu-id="60e92-111">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="60e92-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="60e92-112">Определяет, использует ли настроенная с помощью привязки конечная точка безопасность на уровне сообщений и на транспортном уровне.</span><span class="sxs-lookup"><span data-stu-id="60e92-112">Whether message-level and transport-level security are used by an endpoint configured with the binding.</span></span>  
  
### <a name="transport"></a><span data-ttu-id="60e92-113">Transport</span><span class="sxs-lookup"><span data-stu-id="60e92-113">Transport</span></span>  
 <span data-ttu-id="60e92-114">Тип данных: PeerTransportSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="60e92-114">Data type: PeerTransportSecuritySettings</span></span>  
  
 <span data-ttu-id="60e92-115">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="60e92-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="60e92-116">Параметры безопасности транспорта.</span><span class="sxs-lookup"><span data-stu-id="60e92-116">Transport security settings.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="60e92-117">Требования</span><span class="sxs-lookup"><span data-stu-id="60e92-117">Requirements</span></span>  
  
|<span data-ttu-id="60e92-118">MOF</span><span class="sxs-lookup"><span data-stu-id="60e92-118">MOF</span></span>|<span data-ttu-id="60e92-119">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="60e92-119">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="60e92-120">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="60e92-120">Namespace</span></span>|<span data-ttu-id="60e92-121">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="60e92-121">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="60e92-122">См. также</span><span class="sxs-lookup"><span data-stu-id="60e92-122">See also</span></span>
- <xref:System.ServiceModel.PeerSecuritySettings>
