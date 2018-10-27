---
title: ServiceTimeoutsBehavior
ms.date: 03/30/2017
ms.assetid: 4412525d-a3cc-4eae-b3e8-a50ce766d09d
ms.openlocfilehash: 1a5284915de739e95325234318842a4d1ab607be
ms.sourcegitcommit: 9bd8f213b50f0e1a73e03bd1e840c917fbd6d20a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/26/2018
ms.locfileid: "50135249"
---
# <a name="servicetimeoutsbehavior"></a><span data-ttu-id="fbba2-102">ServiceTimeoutsBehavior</span><span class="sxs-lookup"><span data-stu-id="fbba2-102">ServiceTimeoutsBehavior</span></span>
<span data-ttu-id="fbba2-103">ServiceTimeoutsBehavior</span><span class="sxs-lookup"><span data-stu-id="fbba2-103">ServiceTimeoutsBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fbba2-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fbba2-104">Syntax</span></span>  
  
```csharp
class ServiceTimeoutsBehavior : Behavior  
{  
  datetime TransactionTimeout;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="fbba2-105">Методы</span><span class="sxs-lookup"><span data-stu-id="fbba2-105">Methods</span></span>  
 <span data-ttu-id="fbba2-106">Класс ServiceTimeoutsBehavior не определяет никакие методы.</span><span class="sxs-lookup"><span data-stu-id="fbba2-106">The ServiceTimeoutsBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="fbba2-107">Свойства</span><span class="sxs-lookup"><span data-stu-id="fbba2-107">Properties</span></span>  
 <span data-ttu-id="fbba2-108">Класс ServiceTimeoutsBehavior имеет следующее свойство.</span><span class="sxs-lookup"><span data-stu-id="fbba2-108">The ServiceTimeoutsBehavior class has the following property:</span></span>  
  
### <a name="transactiontimeout"></a><span data-ttu-id="fbba2-109">TransactionTimeout</span><span class="sxs-lookup"><span data-stu-id="fbba2-109">TransactionTimeout</span></span>  
 <span data-ttu-id="fbba2-110">Тип данных: datetime</span><span class="sxs-lookup"><span data-stu-id="fbba2-110">Data type: datetime</span></span>  
  
 <span data-ttu-id="fbba2-111">Тип доступа: только для чтения</span><span class="sxs-lookup"><span data-stu-id="fbba2-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="fbba2-112">Период времени, в течение которого транзакция должна быть завершена.</span><span class="sxs-lookup"><span data-stu-id="fbba2-112">The period within which a transaction must complete.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fbba2-113">Требования</span><span class="sxs-lookup"><span data-stu-id="fbba2-113">Requirements</span></span>  
  
|<span data-ttu-id="fbba2-114">MOF</span><span class="sxs-lookup"><span data-stu-id="fbba2-114">MOF</span></span>|<span data-ttu-id="fbba2-115">Объявлено в файле Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="fbba2-115">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="fbba2-116">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="fbba2-116">Namespace</span></span>|<span data-ttu-id="fbba2-117">Определено в root\ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="fbba2-117">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fbba2-118">См. также</span><span class="sxs-lookup"><span data-stu-id="fbba2-118">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ServiceTimeoutsElement>
