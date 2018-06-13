---
title: ActivityTransfer
ms.date: 03/30/2017
ms.assetid: fc40ef17-2a92-4ce2-853c-6ba8e5d571f3
ms.openlocfilehash: 480670f19407321eb0928d07752936b2ece1f7e9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33484192"
---
# <a name="activitytransfer"></a><span data-ttu-id="14026-102">ActivityTransfer</span><span class="sxs-lookup"><span data-stu-id="14026-102">ActivityTransfer</span></span>
<span data-ttu-id="14026-103">Событие перенаправления действия</span><span class="sxs-lookup"><span data-stu-id="14026-103">Activity Transfer Event</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="14026-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="14026-104">Syntax</span></span>  
  
```  
class ActivityTransfer : WSAT_TraceEvent  
{  
  object ActivityID;  
  object RelatedActivityID;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="14026-105">Методы</span><span class="sxs-lookup"><span data-stu-id="14026-105">Methods</span></span>  
 <span data-ttu-id="14026-106">Класс ActivityTransfer не определяет никакие методы.</span><span class="sxs-lookup"><span data-stu-id="14026-106">The ActivityTransfer class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="14026-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="14026-107">Properties</span></span>  
 <span data-ttu-id="14026-108">Класс ActivityTransfer имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="14026-108">The ActivityTransfer class has the following properties:</span></span>  
  
### <a name="activityid"></a><span data-ttu-id="14026-109">ActivityID</span><span class="sxs-lookup"><span data-stu-id="14026-109">ActivityID</span></span>  
  
-   <span data-ttu-id="14026-110">Тип данных: объект</span><span class="sxs-lookup"><span data-stu-id="14026-110">Data type: object</span></span>  
    <span data-ttu-id="14026-111">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="14026-111">Access type: Read-only</span></span>  
  
-   <span data-ttu-id="14026-112">Идентификатор действия</span><span class="sxs-lookup"><span data-stu-id="14026-112">Activity ID</span></span>  
  
### <a name="relatedactivityid"></a><span data-ttu-id="14026-113">RelatedActivityID</span><span class="sxs-lookup"><span data-stu-id="14026-113">RelatedActivityID</span></span>  
  
-   <span data-ttu-id="14026-114">Тип данных: объект</span><span class="sxs-lookup"><span data-stu-id="14026-114">Data type: object</span></span>  
    <span data-ttu-id="14026-115">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="14026-115">Access type: Read-only</span></span>  
  
-   <span data-ttu-id="14026-116">Связанный идентификатор действия</span><span class="sxs-lookup"><span data-stu-id="14026-116">Related Activity ID</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="14026-117">Требования</span><span class="sxs-lookup"><span data-stu-id="14026-117">Requirements</span></span>  
  
|<span data-ttu-id="14026-118">MOF</span><span class="sxs-lookup"><span data-stu-id="14026-118">MOF</span></span>|<span data-ttu-id="14026-119">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="14026-119">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="14026-120">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="14026-120">Namespace</span></span>|<span data-ttu-id="14026-121">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="14026-121">Defined in root\ServiceModel.</span></span>|
