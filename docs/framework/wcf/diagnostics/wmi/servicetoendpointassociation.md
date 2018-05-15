---
title: ServiceToEndpointAssociation
ms.date: 03/30/2017
ms.assetid: 03c3cd15-e1b2-4dc2-bdc2-59fdccdae110
ms.openlocfilehash: b1e5b87b053e947432cba9f6e716f7d1ea8f013f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="servicetoendpointassociation"></a><span data-ttu-id="5856f-102">ServiceToEndpointAssociation</span><span class="sxs-lookup"><span data-stu-id="5856f-102">ServiceToEndpointAssociation</span></span>
<span data-ttu-id="5856f-103">Сопоставляет службу конечной точке.</span><span class="sxs-lookup"><span data-stu-id="5856f-103">Maps a service to an endpoint.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5856f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5856f-104">Syntax</span></span>  
  
```  
class ServiceToEndpointAssociation  
{  
  Service ref;  
  Endpoint ref;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="5856f-105">Методы</span><span class="sxs-lookup"><span data-stu-id="5856f-105">Methods</span></span>  
 <span data-ttu-id="5856f-106">Класс ServiceToEndpointAssociation не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="5856f-106">The ServiceToEndpointAssociation class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="5856f-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="5856f-107">Properties</span></span>  
 <span data-ttu-id="5856f-108">Класс ServiceToEndpointAssociation имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="5856f-108">The ServiceToEndpointAssociation class has the following properties:</span></span>  
  
### <a name="ref"></a><span data-ttu-id="5856f-109">ref</span><span class="sxs-lookup"><span data-stu-id="5856f-109">ref</span></span>  
 <span data-ttu-id="5856f-110">Тип данных: Service</span><span class="sxs-lookup"><span data-stu-id="5856f-110">Data type: Service</span></span>  
  
 <span data-ttu-id="5856f-111">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="5856f-111">Access type: Read-only</span></span>  
<span data-ttu-id="5856f-112">Квалификаторы: ключ</span><span class="sxs-lookup"><span data-stu-id="5856f-112">Qualifiers: Key</span></span>  
  
 <span data-ttu-id="5856f-113">Служба, связанная с конечной точкой.</span><span class="sxs-lookup"><span data-stu-id="5856f-113">The service associated with the endpoint.</span></span>  
  
### <a name="ref"></a><span data-ttu-id="5856f-114">ref</span><span class="sxs-lookup"><span data-stu-id="5856f-114">ref</span></span>  
 <span data-ttu-id="5856f-115">Тип данных: Endpoint</span><span class="sxs-lookup"><span data-stu-id="5856f-115">Data type: Endpoint</span></span>  
  
 <span data-ttu-id="5856f-116">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="5856f-116">Access type: Read-only</span></span>  
<span data-ttu-id="5856f-117">Квалификаторы: ключ</span><span class="sxs-lookup"><span data-stu-id="5856f-117">Qualifiers: Key</span></span>  
  
 <span data-ttu-id="5856f-118">Конечная точка, связанная со службой.</span><span class="sxs-lookup"><span data-stu-id="5856f-118">The endpoint associated with the service.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5856f-119">Требования</span><span class="sxs-lookup"><span data-stu-id="5856f-119">Requirements</span></span>  
  
|<span data-ttu-id="5856f-120">MOF</span><span class="sxs-lookup"><span data-stu-id="5856f-120">MOF</span></span>|<span data-ttu-id="5856f-121">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="5856f-121">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="5856f-122">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="5856f-122">Namespace</span></span>|<span data-ttu-id="5856f-123">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="5856f-123">Defined in root\ServiceModel</span></span>|
