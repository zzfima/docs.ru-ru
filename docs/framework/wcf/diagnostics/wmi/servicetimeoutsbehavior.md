---
title: ServiceTimeoutsBehavior
ms.date: 03/30/2017
ms.assetid: 4412525d-a3cc-4eae-b3e8-a50ce766d09d
ms.openlocfilehash: 58e872f2b15776d65bccdcc47c353ce566cd9d2f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59116016"
---
# <a name="servicetimeoutsbehavior"></a><span data-ttu-id="fe602-102">ServiceTimeoutsBehavior</span><span class="sxs-lookup"><span data-stu-id="fe602-102">ServiceTimeoutsBehavior</span></span>
<span data-ttu-id="fe602-103">ServiceTimeoutsBehavior</span><span class="sxs-lookup"><span data-stu-id="fe602-103">ServiceTimeoutsBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fe602-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fe602-104">Syntax</span></span>  
  
```csharp
class ServiceTimeoutsBehavior : Behavior  
{  
  datetime TransactionTimeout;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="fe602-105">Методы</span><span class="sxs-lookup"><span data-stu-id="fe602-105">Methods</span></span>  
 <span data-ttu-id="fe602-106">Класс ServiceTimeoutsBehavior не определяет никакие методы.</span><span class="sxs-lookup"><span data-stu-id="fe602-106">The ServiceTimeoutsBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="fe602-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="fe602-107">Properties</span></span>  
 <span data-ttu-id="fe602-108">Класс ServiceTimeoutsBehavior имеет следующее свойство.</span><span class="sxs-lookup"><span data-stu-id="fe602-108">The ServiceTimeoutsBehavior class has the following property:</span></span>  
  
### <a name="transactiontimeout"></a><span data-ttu-id="fe602-109">TransactionTimeout</span><span class="sxs-lookup"><span data-stu-id="fe602-109">TransactionTimeout</span></span>  
 <span data-ttu-id="fe602-110">Тип данных: datetime</span><span class="sxs-lookup"><span data-stu-id="fe602-110">Data type: datetime</span></span>  
  
 <span data-ttu-id="fe602-111">Тип доступа: Только чтение</span><span class="sxs-lookup"><span data-stu-id="fe602-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="fe602-112">Период времени, в течение которого транзакция должна быть завершена.</span><span class="sxs-lookup"><span data-stu-id="fe602-112">The period within which a transaction must complete.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fe602-113">Требования</span><span class="sxs-lookup"><span data-stu-id="fe602-113">Requirements</span></span>  
  
|<span data-ttu-id="fe602-114">MOF</span><span class="sxs-lookup"><span data-stu-id="fe602-114">MOF</span></span>|<span data-ttu-id="fe602-115">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="fe602-115">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="fe602-116">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="fe602-116">Namespace</span></span>|<span data-ttu-id="fe602-117">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="fe602-117">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fe602-118">См. также</span><span class="sxs-lookup"><span data-stu-id="fe602-118">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceTimeoutsElement>
