---
title: ActivityTransfer
ms.date: 03/30/2017
ms.assetid: fc40ef17-2a92-4ce2-853c-6ba8e5d571f3
ms.openlocfilehash: 936e870c1ec991e2e33acf8a08ccc93975989679
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61964299"
---
# <a name="activitytransfer"></a><span data-ttu-id="baab9-102">ActivityTransfer</span><span class="sxs-lookup"><span data-stu-id="baab9-102">ActivityTransfer</span></span>
<span data-ttu-id="baab9-103">Событие перенаправления действия</span><span class="sxs-lookup"><span data-stu-id="baab9-103">Activity Transfer Event</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="baab9-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="baab9-104">Syntax</span></span>  
  
```csharp
class ActivityTransfer : WSAT_TraceEvent  
{  
  object ActivityID;  
  object RelatedActivityID;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="baab9-105">Методы</span><span class="sxs-lookup"><span data-stu-id="baab9-105">Methods</span></span>  
 <span data-ttu-id="baab9-106">Класс ActivityTransfer не определяет никакие методы.</span><span class="sxs-lookup"><span data-stu-id="baab9-106">The ActivityTransfer class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="baab9-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="baab9-107">Properties</span></span>  
 <span data-ttu-id="baab9-108">Класс ActivityTransfer имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="baab9-108">The ActivityTransfer class has the following properties:</span></span>  
  
### <a name="activityid"></a><span data-ttu-id="baab9-109">ActivityID</span><span class="sxs-lookup"><span data-stu-id="baab9-109">ActivityID</span></span>  
  
- <span data-ttu-id="baab9-110">Тип данных: объект</span><span class="sxs-lookup"><span data-stu-id="baab9-110">Data type: object</span></span>  
    <span data-ttu-id="baab9-111">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="baab9-111">Access type: Read-only</span></span>  
  
- <span data-ttu-id="baab9-112">ИД действия</span><span class="sxs-lookup"><span data-stu-id="baab9-112">Activity ID</span></span>  
  
### <a name="relatedactivityid"></a><span data-ttu-id="baab9-113">RelatedActivityID</span><span class="sxs-lookup"><span data-stu-id="baab9-113">RelatedActivityID</span></span>  
  
- <span data-ttu-id="baab9-114">Тип данных: объект</span><span class="sxs-lookup"><span data-stu-id="baab9-114">Data type: object</span></span>  
    <span data-ttu-id="baab9-115">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="baab9-115">Access type: Read-only</span></span>  
  
- <span data-ttu-id="baab9-116">Связанный идентификатор действия</span><span class="sxs-lookup"><span data-stu-id="baab9-116">Related Activity ID</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="baab9-117">Требования</span><span class="sxs-lookup"><span data-stu-id="baab9-117">Requirements</span></span>  
  
|<span data-ttu-id="baab9-118">MOF</span><span class="sxs-lookup"><span data-stu-id="baab9-118">MOF</span></span>|<span data-ttu-id="baab9-119">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="baab9-119">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="baab9-120">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="baab9-120">Namespace</span></span>|<span data-ttu-id="baab9-121">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="baab9-121">Defined in root\ServiceModel.</span></span>|
