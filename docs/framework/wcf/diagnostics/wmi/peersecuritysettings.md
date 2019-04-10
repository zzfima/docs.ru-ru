---
title: PeerSecuritySettings
ms.date: 03/30/2017
ms.assetid: 24ae0d35-f3a3-419b-afd6-686e22aae27b
ms.openlocfilehash: 1c33e1ce710fea3b1698a6dab47a199e40388f5a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59217891"
---
# <a name="peersecuritysettings"></a><span data-ttu-id="43df7-102">PeerSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="43df7-102">PeerSecuritySettings</span></span>
<span data-ttu-id="43df7-103">PeerSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="43df7-103">PeerSecuritySettings</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43df7-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="43df7-104">Syntax</span></span>  
  
```csharp
class PeerSecuritySettings  
{  
  string Mode;  
  PeerTransportSecuritySettings Transport;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="43df7-105">Методы</span><span class="sxs-lookup"><span data-stu-id="43df7-105">Methods</span></span>  
 <span data-ttu-id="43df7-106">Класс PeerSecuritySettings не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="43df7-106">The PeerSecuritySettings class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="43df7-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="43df7-107">Properties</span></span>  
 <span data-ttu-id="43df7-108">Класс PeerSecuritySettings имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="43df7-108">The PeerSecuritySettings class has the following properties:</span></span>  
  
### <a name="mode"></a><span data-ttu-id="43df7-109">Mode</span><span class="sxs-lookup"><span data-stu-id="43df7-109">Mode</span></span>  
 <span data-ttu-id="43df7-110">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="43df7-110">Data type: string</span></span>  
  
 <span data-ttu-id="43df7-111">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="43df7-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="43df7-112">Определяет, использует ли настроенная с помощью привязки конечная точка безопасность на уровне сообщений и на транспортном уровне.</span><span class="sxs-lookup"><span data-stu-id="43df7-112">Whether message-level and transport-level security are used by an endpoint configured with the binding.</span></span>  
  
### <a name="transport"></a><span data-ttu-id="43df7-113">Transport</span><span class="sxs-lookup"><span data-stu-id="43df7-113">Transport</span></span>  
 <span data-ttu-id="43df7-114">Тип данных: PeerTransportSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="43df7-114">Data type: PeerTransportSecuritySettings</span></span>  
  
 <span data-ttu-id="43df7-115">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="43df7-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="43df7-116">Параметры безопасности транспорта.</span><span class="sxs-lookup"><span data-stu-id="43df7-116">Transport security settings.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="43df7-117">Требования</span><span class="sxs-lookup"><span data-stu-id="43df7-117">Requirements</span></span>  
  
|<span data-ttu-id="43df7-118">MOF</span><span class="sxs-lookup"><span data-stu-id="43df7-118">MOF</span></span>|<span data-ttu-id="43df7-119">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="43df7-119">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="43df7-120">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="43df7-120">Namespace</span></span>|<span data-ttu-id="43df7-121">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="43df7-121">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="43df7-122">См. также</span><span class="sxs-lookup"><span data-stu-id="43df7-122">See also</span></span>

- <xref:System.ServiceModel.PeerSecuritySettings>
