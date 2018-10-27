---
title: ServiceToEndpointAssociation
ms.date: 03/30/2017
ms.assetid: 03c3cd15-e1b2-4dc2-bdc2-59fdccdae110
ms.openlocfilehash: 3d23a3ee10c47e04ea7bdba202ea5063c0d84fac
ms.sourcegitcommit: b22705f1540b237c566721018f974822d5cd8758
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/19/2018
ms.locfileid: "49452713"
---
# <a name="servicetoendpointassociation"></a><span data-ttu-id="6b944-102">ServiceToEndpointAssociation</span><span class="sxs-lookup"><span data-stu-id="6b944-102">ServiceToEndpointAssociation</span></span>
<span data-ttu-id="6b944-103">Сопоставляет службу конечной точке.</span><span class="sxs-lookup"><span data-stu-id="6b944-103">Maps a service to an endpoint.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6b944-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6b944-104">Syntax</span></span>  
  
```csharp
class ServiceToEndpointAssociation  
{  
  Service ref;  
  Endpoint ref;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="6b944-105">Методы</span><span class="sxs-lookup"><span data-stu-id="6b944-105">Methods</span></span>  
 <span data-ttu-id="6b944-106">Класс ServiceToEndpointAssociation не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="6b944-106">The ServiceToEndpointAssociation class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="6b944-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="6b944-107">Properties</span></span>  
 <span data-ttu-id="6b944-108">Класс ServiceToEndpointAssociation имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="6b944-108">The ServiceToEndpointAssociation class has the following properties:</span></span>  
  
### <a name="ref"></a><span data-ttu-id="6b944-109">ref</span><span class="sxs-lookup"><span data-stu-id="6b944-109">ref</span></span>  
 <span data-ttu-id="6b944-110">Тип данных: Service</span><span class="sxs-lookup"><span data-stu-id="6b944-110">Data type: Service</span></span>  
  
 <span data-ttu-id="6b944-111">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="6b944-111">Access type: Read-only</span></span>  
<span data-ttu-id="6b944-112">Квалификаторы: ключ</span><span class="sxs-lookup"><span data-stu-id="6b944-112">Qualifiers: Key</span></span>  
  
 <span data-ttu-id="6b944-113">Служба, связанная с конечной точкой.</span><span class="sxs-lookup"><span data-stu-id="6b944-113">The service associated with the endpoint.</span></span>  
  
### <a name="ref"></a><span data-ttu-id="6b944-114">ref</span><span class="sxs-lookup"><span data-stu-id="6b944-114">ref</span></span>  
 <span data-ttu-id="6b944-115">Тип данных: Endpoint</span><span class="sxs-lookup"><span data-stu-id="6b944-115">Data type: Endpoint</span></span>  
  
 <span data-ttu-id="6b944-116">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="6b944-116">Access type: Read-only</span></span>  
<span data-ttu-id="6b944-117">Квалификаторы: ключ</span><span class="sxs-lookup"><span data-stu-id="6b944-117">Qualifiers: Key</span></span>  
  
 <span data-ttu-id="6b944-118">Конечная точка, связанная со службой.</span><span class="sxs-lookup"><span data-stu-id="6b944-118">The endpoint associated with the service.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6b944-119">Требования</span><span class="sxs-lookup"><span data-stu-id="6b944-119">Requirements</span></span>  
  
|<span data-ttu-id="6b944-120">MOF</span><span class="sxs-lookup"><span data-stu-id="6b944-120">MOF</span></span>|<span data-ttu-id="6b944-121">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="6b944-121">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="6b944-122">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="6b944-122">Namespace</span></span>|<span data-ttu-id="6b944-123">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="6b944-123">Defined in root\ServiceModel</span></span>|
