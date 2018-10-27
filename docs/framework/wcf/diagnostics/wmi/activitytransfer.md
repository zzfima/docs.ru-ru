---
title: ActivityTransfer
ms.date: 03/30/2017
ms.assetid: fc40ef17-2a92-4ce2-853c-6ba8e5d571f3
ms.openlocfilehash: 936e870c1ec991e2e33acf8a08ccc93975989679
ms.sourcegitcommit: 9bd8f213b50f0e1a73e03bd1e840c917fbd6d20a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2018
ms.locfileid: "50034435"
---
# <a name="activitytransfer"></a><span data-ttu-id="a647e-102">ActivityTransfer</span><span class="sxs-lookup"><span data-stu-id="a647e-102">ActivityTransfer</span></span>
<span data-ttu-id="a647e-103">Событие перенаправления действия</span><span class="sxs-lookup"><span data-stu-id="a647e-103">Activity Transfer Event</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a647e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a647e-104">Syntax</span></span>  
  
```csharp
class ActivityTransfer : WSAT_TraceEvent  
{  
  object ActivityID;  
  object RelatedActivityID;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="a647e-105">Методы</span><span class="sxs-lookup"><span data-stu-id="a647e-105">Methods</span></span>  
 <span data-ttu-id="a647e-106">Класс ActivityTransfer не определяет никакие методы.</span><span class="sxs-lookup"><span data-stu-id="a647e-106">The ActivityTransfer class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="a647e-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="a647e-107">Properties</span></span>  
 <span data-ttu-id="a647e-108">Класс ActivityTransfer имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="a647e-108">The ActivityTransfer class has the following properties:</span></span>  
  
### <a name="activityid"></a><span data-ttu-id="a647e-109">ActivityID</span><span class="sxs-lookup"><span data-stu-id="a647e-109">ActivityID</span></span>  
  
-   <span data-ttu-id="a647e-110">Тип данных: объект</span><span class="sxs-lookup"><span data-stu-id="a647e-110">Data type: object</span></span>  
    <span data-ttu-id="a647e-111">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="a647e-111">Access type: Read-only</span></span>  
  
-   <span data-ttu-id="a647e-112">Идентификатор действия</span><span class="sxs-lookup"><span data-stu-id="a647e-112">Activity ID</span></span>  
  
### <a name="relatedactivityid"></a><span data-ttu-id="a647e-113">RelatedActivityID</span><span class="sxs-lookup"><span data-stu-id="a647e-113">RelatedActivityID</span></span>  
  
-   <span data-ttu-id="a647e-114">Тип данных: объект</span><span class="sxs-lookup"><span data-stu-id="a647e-114">Data type: object</span></span>  
    <span data-ttu-id="a647e-115">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="a647e-115">Access type: Read-only</span></span>  
  
-   <span data-ttu-id="a647e-116">Связанный идентификатор действия</span><span class="sxs-lookup"><span data-stu-id="a647e-116">Related Activity ID</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a647e-117">Требования</span><span class="sxs-lookup"><span data-stu-id="a647e-117">Requirements</span></span>  
  
|<span data-ttu-id="a647e-118">MOF</span><span class="sxs-lookup"><span data-stu-id="a647e-118">MOF</span></span>|<span data-ttu-id="a647e-119">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="a647e-119">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="a647e-120">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="a647e-120">Namespace</span></span>|<span data-ttu-id="a647e-121">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="a647e-121">Defined in root\ServiceModel.</span></span>|
