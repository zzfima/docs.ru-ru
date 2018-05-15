---
title: WSAT_TraceRecord
ms.date: 03/30/2017
ms.assetid: 99bc7f66-1335-40d8-aa68-e754d569dc0d
ms.openlocfilehash: 1136647ce668dbb69bdb8acf8ed62343831464b3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="wsattracerecord"></a><span data-ttu-id="c90c0-102">WSAT_TraceRecord</span><span class="sxs-lookup"><span data-stu-id="c90c0-102">WSAT_TraceRecord</span></span>
<span data-ttu-id="c90c0-103">WSAT_TraceRecord</span><span class="sxs-lookup"><span data-stu-id="c90c0-103">WSAT_TraceRecord</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c90c0-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c90c0-104">Syntax</span></span>  
  
```  
class WSAT_TraceRecord : WSAT_TraceEvent  
{  
  object ActivityID;  
  sint32 EventID;  
  string TraceRecord;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="c90c0-105">Методы</span><span class="sxs-lookup"><span data-stu-id="c90c0-105">Methods</span></span>  
 <span data-ttu-id="c90c0-106">Класс WSAT_TraceRecord не определяет никаких методов.</span><span class="sxs-lookup"><span data-stu-id="c90c0-106">The WSAT_TraceRecord class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="c90c0-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="c90c0-107">Properties</span></span>  
 <span data-ttu-id="c90c0-108">Класс WSAT_TraceRecord имеет следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="c90c0-108">The WSAT_TraceRecord class has the following properties:</span></span>  
  
### <a name="activityid"></a><span data-ttu-id="c90c0-109">ActivityID</span><span class="sxs-lookup"><span data-stu-id="c90c0-109">ActivityID</span></span>  
 <span data-ttu-id="c90c0-110">Тип данных: объект</span><span class="sxs-lookup"><span data-stu-id="c90c0-110">Data type: object</span></span>  
<span data-ttu-id="c90c0-111">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="c90c0-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c90c0-112">ИД активности записи трассировки.</span><span class="sxs-lookup"><span data-stu-id="c90c0-112">The activity ID of the trace record.</span></span>  
  
### <a name="eventid"></a><span data-ttu-id="c90c0-113">EventID</span><span class="sxs-lookup"><span data-stu-id="c90c0-113">EventID</span></span>  
 <span data-ttu-id="c90c0-114">Тип данных: sint32</span><span class="sxs-lookup"><span data-stu-id="c90c0-114">Data type: sint32</span></span>  
<span data-ttu-id="c90c0-115">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="c90c0-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c90c0-116">ИД события записи трассировки.</span><span class="sxs-lookup"><span data-stu-id="c90c0-116">The event ID of the trace record.</span></span>  
  
### <a name="tracerecord"></a><span data-ttu-id="c90c0-117">TraceRecord</span><span class="sxs-lookup"><span data-stu-id="c90c0-117">TraceRecord</span></span>  
 <span data-ttu-id="c90c0-118">Тип данных: string</span><span class="sxs-lookup"><span data-stu-id="c90c0-118">Data type: string</span></span>  
<span data-ttu-id="c90c0-119">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="c90c0-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c90c0-120">Запись трассировки</span><span class="sxs-lookup"><span data-stu-id="c90c0-120">Trace Record</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c90c0-121">Требования</span><span class="sxs-lookup"><span data-stu-id="c90c0-121">Requirements</span></span>  
  
|<span data-ttu-id="c90c0-122">MOF</span><span class="sxs-lookup"><span data-stu-id="c90c0-122">MOF</span></span>|<span data-ttu-id="c90c0-123">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="c90c0-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="c90c0-124">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="c90c0-124">Namespace</span></span>|<span data-ttu-id="c90c0-125">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="c90c0-125">Defined in root\ServiceModel</span></span>|
