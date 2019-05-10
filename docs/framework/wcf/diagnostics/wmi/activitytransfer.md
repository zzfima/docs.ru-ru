---
title: ActivityTransfer
ms.date: 03/30/2017
ms.assetid: fc40ef17-2a92-4ce2-853c-6ba8e5d571f3
ms.openlocfilehash: 6237d65d6964a4ebca34af895158c83239641593
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64662814"
---
# <a name="activitytransfer"></a><span data-ttu-id="9d614-102">ActivityTransfer</span><span class="sxs-lookup"><span data-stu-id="9d614-102">ActivityTransfer</span></span>
<span data-ttu-id="9d614-103">Событие перенаправления действия</span><span class="sxs-lookup"><span data-stu-id="9d614-103">Activity Transfer Event</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9d614-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9d614-104">Syntax</span></span>  
  
```csharp
class ActivityTransfer : WSAT_TraceEvent  
{  
  object ActivityID;  
  object RelatedActivityID;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="9d614-105">Методы</span><span class="sxs-lookup"><span data-stu-id="9d614-105">Methods</span></span>  
 <span data-ttu-id="9d614-106">Класс ActivityTransfer не определяет никакие методы.</span><span class="sxs-lookup"><span data-stu-id="9d614-106">The ActivityTransfer class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="9d614-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="9d614-107">Properties</span></span>  
 <span data-ttu-id="9d614-108">Класс ActivityTransfer имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="9d614-108">The ActivityTransfer class has the following properties:</span></span>  
  
### <a name="activityid"></a><span data-ttu-id="9d614-109">ActivityID</span><span class="sxs-lookup"><span data-stu-id="9d614-109">ActivityID</span></span>  
  
- <span data-ttu-id="9d614-110">Тип данных: объект</span><span class="sxs-lookup"><span data-stu-id="9d614-110">Data type: object</span></span>  
    <span data-ttu-id="9d614-111">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="9d614-111">Access type: Read-only</span></span>  
  
- <span data-ttu-id="9d614-112">ИД действия</span><span class="sxs-lookup"><span data-stu-id="9d614-112">Activity ID</span></span>  
  
### <a name="relatedactivityid"></a><span data-ttu-id="9d614-113">RelatedActivityID</span><span class="sxs-lookup"><span data-stu-id="9d614-113">RelatedActivityID</span></span>  
  
- <span data-ttu-id="9d614-114">Тип данных: объект</span><span class="sxs-lookup"><span data-stu-id="9d614-114">Data type: object</span></span>  
    <span data-ttu-id="9d614-115">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="9d614-115">Access type: Read-only</span></span>  
  
- <span data-ttu-id="9d614-116">Связанный идентификатор действия</span><span class="sxs-lookup"><span data-stu-id="9d614-116">Related Activity ID</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9d614-117">Требования</span><span class="sxs-lookup"><span data-stu-id="9d614-117">Requirements</span></span>  
  
|<span data-ttu-id="9d614-118">MOF</span><span class="sxs-lookup"><span data-stu-id="9d614-118">MOF</span></span>|<span data-ttu-id="9d614-119">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="9d614-119">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="9d614-120">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="9d614-120">Namespace</span></span>|<span data-ttu-id="9d614-121">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="9d614-121">Defined in root\ServiceModel.</span></span>|
